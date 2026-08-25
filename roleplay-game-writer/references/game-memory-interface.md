# 项目记忆与角色扮演接口

本文件只在用户明确继续一个带有 `story-memory/` 的角色扮演项目时使用。它是记忆、交互和同步接口，不替换或改写本 Skill 的原有文风、题材模式、情绪机制、对白规则、篇幅规则和质量检查。

## 读取顺序

先读取 `story-memory/00_INDEX.md`，再按索引和当前场景需要读取：

- `01_WORLDLINE.md`
- `02_CHARACTER_STATE.md`
- `03_EVENT_LEDGER.md`
- `04_INFORMATION_MAP.md`
- `05_CURRENT_STATE.md`
- `06_PROPOSAL_LEDGER.md`
- `09_FORESHADOWING.md`
- `10_SYNC_STATE.md`
- `11_CONTINUITY_CHECKLIST.md`

最后读取当前剧情所在的 `episodes/` 分段。完整聊天导出、Skill 讨论、导出讨论和其他元对话不自动升级为剧情事实。

## 作者主导与场景交付

- 用户是剧情事实和关键转折的最终决定者；模型负责把用户提供的路线与梗概写成完整小说场景。
- 用户的梗概是剧情骨架，不是成稿。不得逐句复述或用摘要代替正文；应依照本 Skill 的原有文风规则完成场景化扩写。
- 未选择的路线不是世界事实。若用户尚未给出路线，先提供 3 条方向不同且后果不同的路线，并保留自定义行动入口。
- 若用户已经选定路线并提供梗概，直接写完整正文，不擅自改变用户确定的主线事实、人物关键行动或结果。
- 正文之后才输出下一轮路线、确认栏和存档，不把接口字段混入小说正文。

## 确认与修改

- 模型自行补出的重大事实先标记为 `proposed`。
- 每个完整场景或剧情回合末尾只提示一次确认，不在每句话后打断正文。
- 用户没有明确说“确认”但继续选择、补充行动或推进剧情时，上一轮提案按默认规则视为确认。
- 用户只讨论导出、记忆、Skill、格式或工具时，不触发剧情确认。
- 用户明确修改、撤销或否定时，最新用户说法优先；将冲突提案及其 `depends_on` 依赖标记为 `revoked`，不得继续写入当前 Canon。

## `save_state`

每个完整剧情回合末尾输出机器可读 JSON，至少包含：

```json
{
  "turn_id": "...",
  "kind": "story_turn",
  "status": "proposed",
  "items": [
    {
      "id": "...",
      "content": "...",
      "source": "user|confirmed|model",
      "depends_on": []
    }
  ]
}
```

`status` 只能是 `proposed`、`confirmed`、`revoked` 或 `conflict`。只有用户明确提供、选择、确认，或按默认确认规则转正的事实才能进入 Canon。

## 五回合同步

- 一个“完整正文 + 路线 + 确认提示”算一个剧情回合；不要按聊天消息数量计数。
- 计数和同步门槛以 `story-memory/10_SYNC_STATE.md` 为准。
- 达到 5 个完整剧情回合后，且用户已授权并且 GitHub 写入可用，再同步最新的 `05_CURRENT_STATE.md`、`06_PROPOSAL_LEDGER.md`、`09_FORESHADOWING.md`、`10_SYNC_STATE.md` 和需要更新的剧情分段。
- 只同步已确认事实；未确认内容保留为 `proposed`。不上传完整原始聊天导出或元讨论。
- 提交后必须回读验证；失败时保留 `pending_sync: true`，不得声称同步成功。

