# 《龙族·血之哀》角色扮演项目

这是一个供 ChatGPT 聊天模式使用的 Skill + 分层记忆项目。

## 使用顺序

1. 上传或连接 `roleplay-game-writer/SKILL.md`。
2. 上传 `story-memory/00_INDEX.md`。
3. 按 `00_INDEX.md` 的读取顺序提供本轮需要的记忆文件。
4. 东京线续写时，额外提供 `story-memory/05_CURRENT_STATE.md`、`04_INFORMATION_MAP.md`、`06_PROPOSAL_LEDGER.md` 和 `story-memory/episodes/06-tokyo-dragon-abyss-entry.md`。
5. 需要查原文时，再读取 `source/` 中的文件；不要每次把完整导出全部塞进对话。

## 目录说明

- `roleplay-game-writer/`：作者主导、文学化表达、确认/撤销规则。
- `story-memory/`：当前 Canon、人物、事件链、信息差和详细回合分段。
- `source/`：完整原始导出、净化剧情档案和初始 DOCX 的文本来源；它们只保留在本地，不随本次公开记忆包上传。
- `archive/`：之前试做但已从活动项目中移出的工具和中间文件，不参与续写，也不随本次上传发布。

## 重要边界

普通 ChatGPT 不会自动读取本地文件，也不会自动把 `save_state` 写回文件。每轮的 `save_state` 需要由用户决定是否同步到记忆账本；用户继续推进则按项目规则默认确认，明确修改则撤销旧内容及其依赖。

