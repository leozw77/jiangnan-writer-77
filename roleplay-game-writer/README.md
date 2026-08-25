# roleplay-game-writer

> 想写出“青春、关系、幻想与代价”的重量，却不想只堆雨夜、孤独和漂亮句子。
>
> `roleplay-game-writer` 在可迁移的中文文学叙事机制之上增加游戏主持、剧情状态管理和连续续写协议。

[![Stars](https://img.shields.io/github/stars/tianyayu6/jiangnan-writer?style=flat-square&logo=github)](https://github.com/tianyayu6/jiangnan-writer/stargazers)
[![Forks](https://img.shields.io/github/forks/tianyayu6/jiangnan-writer?style=flat-square&logo=github)](https://github.com/tianyayu6/jiangnan-writer/network/members)
[![Issues](https://img.shields.io/github/issues/tianyayu6/jiangnan-writer?style=flat-square&logo=github)](https://github.com/tianyayu6/jiangnan-writer/issues)
[![Last commit](https://img.shields.io/github/last-commit/tianyayu6/jiangnan-writer?style=flat-square&logo=git)](https://github.com/tianyayu6/jiangnan-writer/commits/main)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)

```bash
npx skills add ./roleplay-game-writer
```

**中文** | [English](#english)

## 它解决什么问题

很多所谓“江南感”写作，只学到了表层：短句、雨夜、少年、牺牲和开放结尾。

这个 Skill 做的是另一件事：把可迁移的高层机制拆出来，再根据题材选择使用。

| 你的需求 | Skill 的处理方式 |
|---|---|
| 校园、友情、暗恋 | 用生活系统、群像关系和喜剧转痛感推进 |
| 都市幻想、少年成长 | 让现实处境、具体能力与异常规则互相作用 |
| 九州感、战争、王朝 | 用制度、职责、资源和关系构成史诗压力 |
| 武侠、江湖爱情 | 让武功决定“能不能”，关系决定“会不会” |
| 城市科幻、末日战争 | 用岗位、技术流程和协作承载英雄主义 |
| 序跋、后记、回忆散文 | 用具体触发物、记忆链和自我校正组织长句 |

它不会把六种题材都压成同一种腔调，也不会为了“像”而强行写死人。

## 你会得到

- 六种题材模式：校园群像、都市幻想、历史史诗、关系武侠、都市科幻、回望散文
- 九个可组合的叙事引擎，而不是一套固定公式
- 场景、对话、动作、抒情和结尾的可执行检查方法
- 长篇需要的角色知识、关系债务、能力限制与伏线台账
- 读取分层项目记忆并在每轮输出 `save_state`
- 保留玩家角色的行动权，区分已确认事实与待确认信息

## 使用示例

安装后，直接用自然语言调用：

> 用 `$roleplay-game-writer` 写一个 2500 字的校园短篇。两个即将毕业的室友因为一台坏掉的打印机，终于谈起四年前没有说完的事。不要奇幻，结尾温暖但不圆满。

> 用 `$roleplay-game-writer` 把这个王朝战争大纲改成三章。重点写职责、资源和朋友之间的分歧，不要百科式介绍设定。

> 用 `$roleplay-game-writer` 润色这段都市科幻。保留情节，让技术岗位可信，让感情通过工作和对话出现，别强加悲剧。

> 用 `$roleplay-game-writer` 写一篇后记式散文，从搬家时找到的一张饭卡写起，谈时间和旧朋友。不要冒充任何真实作者的经历。

## 安装

1. 确认已安装 Node.js：

   ```bash
   node --version
   npx --version
   ```

2. 安装本地 Skill：

   ```bash
   npx skills add ./roleplay-game-writer
   ```

3. 查看是否可发现：

   ```bash
   npx skills add ./roleplay-game-writer --list
   ```

## 前置条件

- [ ] 已安装 Node.js 18 或更高版本：[nodejs.org](https://nodejs.org/)
- [ ] 使用支持 Agent Skills 的工具，如 Codex、Claude Code、Cursor、OpenCode 或 Gemini CLI
- [ ] 创作请求应为原创设定，或允许转换成原创人物、关系和世界规则

## 研究基础

本 Skill 使用用户提供的 358 个文本文件进行全库统计，并对跨时期、跨题材代表文本做结构精读。仓库只保留统计结论、题材差异与可迁移叙事机制：

- 不包含作品全集或原文摘录库
- 不提供金句库、段落模板或声线克隆
- 不声称生成结果等同于江南本人作品

研究方法与局限见 [`references/corpus-study.md`](references/corpus-study.md)。

## 游戏使用边界

- `story-memory/` 中的项目资料是当前游戏的事实来源。
- 每轮不得替玩家决定玩家角色的关键行动。
- 导出、总结、修订等元对话不自动写入剧情事实。
- “高层机制”不等于固定模板；不同题材仍应服从当前游戏的世界规则。

## Troubleshooting

| 问题 | 原因 | 解决方法 |
|---|---|---|
| `No valid skills found` | `SKILL.md` 未被正确解析或安装源错误 | 运行 `npx skills add tianyayu6/jiangnan-writer --list`，并升级 `npx skills` |
| 输出总是雨夜、短句和牺牲 | 提示词只要求“江南感”，没有说明题材和目标 | 指定校园、史诗、武侠、科幻或散文模式，并明确结局倾向 |
| 续写与记忆不一致 | 当前状态没有及时回写 | 先更新 `story-memory/05_CURRENT_STATE.md` 和 `story-memory/06_PROPOSAL_LEDGER.md`，再继续游戏 |
| 玩家角色被替你行动 | 主持输出越过了玩家权限 | 重写该轮，只描述可见局面和 NPC 行动，留下玩家接管入口 |

## 致谢

- 使用 [OpenAI Agent Skills](https://github.com/openai/skills) 的目录约定
- 技能构建方法参考 [女娲 Skill 造人术](https://github.com/alchaincyf/nuwa-skill)
- 创作观研究参考公开访谈与评论，来源列于 `references/research/`

## License

[MIT](LICENSE)

---

<a name="english"></a>
## English

`roleplay-game-writer` is an agent skill for continuous Chinese role-playing games. It uses transferable narrative mechanisms together with project memory, player-agency rules, and save-state output.

It routes each request into one of six modes: campus ensemble, urban fantasy, historical epic, relationship-driven wuxia, urban science fiction, or reflective essay. It then selects a small set of narrative engines for character agency, institutional pressure, relationship debt, humor-to-pain transitions, and visible consequences.

Install:

```bash
npx skills add ./roleplay-game-writer
```

Try prompts such as:

- "Use `$roleplay-game-writer` to continue from `story-memory/05_CURRENT_STATE.md` and leave my player character's next action to me."
- "Use `$roleplay-game-writer` to update `story-memory/03_TIMELINE.md` and `story-memory/06_PROPOSAL_LEDGER.md` after this turn."

The repository contains writing guidance and game-continuity rules. Keep dynamic story memory outside the Skill folder.

