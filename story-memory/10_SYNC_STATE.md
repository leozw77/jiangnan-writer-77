# 同步状态与 GitHub 更新门槛

> 用户已授权上传 GitHub。后续每完成 5 个剧情回合，按本文件规则同步一次；强制同步条件仍然优先。

```yaml
sync_interval: 5
count_basis: completed_story_scene
story_turns_since_sync: 0
github_sync_enabled: true
initial_package_sync_required: false
pending_sync: false
last_synced_commit: 6e07161a4db311f4341b05a368030a252a606ec5
last_synced_at: 2026-08-26
```

## 计数规则

- 一次完整的“正文 + 选项 + 确认提示”算一个剧情回合。
- 用户只是在选择路线、补充一句行动或要求修改，不单独增加计数；它属于当前剧情回合的输入。
- Skill、导出、记忆、GitHub、文件和工具讨论不计数。
- 新聊天开始时，先读取本文件，不能根据当前窗口消息数量猜计数。

## 正常同步流程

当 `story_turns_since_sync` 达到 `sync_interval`，且 `github_sync_enabled: true` 时：

1. 读取最新 `05_CURRENT_STATE.md`、`06_PROPOSAL_LEDGER.md`、`09_FORESHADOWING.md`。
2. 将本周期已确认内容写入记忆；未确认内容保留为 `proposed`。
3. 更新本文件的计数、时间和 commit 标识。
4. 通过 GitHub 连接器提交到固定分支/目录。
5. 回读提交后的文件，确认内容和 commit 一致。
6. 只有回读成功后，才把计数归零并报告“同步完成”。

## 强制立即同步

即使没有达到 5 回合，也必须在以下情况同步：

- 用户修改或撤销重大世界线；
- 角色死亡、复活、身份揭露或关系重置；
- 战力体系发生不可逆跃迁；
- 关键伏笔被回收；
- 用户明确说“同步到 GitHub”；
- 准备切换长期项目或交接给新的聊天。

## 失败处理

- GitHub 未授权、连接器不可用或回读失败时，不能声称已同步。
- 将 `pending_sync: true`，保留 `save_state` 和待提交文件清单。
- 失败不归零计数；下次先处理待同步内容。
- 未获得新的明确授权时，不扩大同步范围；仅同步本项目 Skill 与分层记忆，不上传原始聊天全文。

