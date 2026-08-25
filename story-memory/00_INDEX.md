# 《龙族·血之哀》角色扮演记忆入口

这是一个“角色扮演类游戏小说”的项目记忆，不是对原聊天的几句摘要。原始证据保存在 `source/`；本目录保存可供续写读取的 Canon、人物状态、事件链、信息差、分支修订和当前入口。

## 每次续写的读取顺序

1. `roleplay-game-writer/SKILL.md`
2. 本文件
3. `01_WORLDLINE.md`：世界线、玩家权限、战力和不可误读原则
4. `02_CHARACTER_STATE.md`：主要人物的稳定状态
5. `03_EVENT_LEDGER.md`：按顺序的已发生事件与后果
6. `04_INFORMATION_MAP.md`：每个人知道什么、不能说出什么
7. `05_CURRENT_STATE.md`：当前场景和未决行动
8. `06_PROPOSAL_LEDGER.md`：提案、默认确认、修改和撤销
9. `09_FORESHADOWING.md`：伏笔、承诺和未解决问题
10. `10_SYNC_STATE.md`：5 回合同步计数和 GitHub 写入门槛
11. `11_CONTINUITY_CHECKLIST.md`：写作前后连续性检查
12. 只按当前场景读取 `episodes/` 中对应的详细回合

需要核对原句时，再读取 `source/plot-only-transcript.md`；不要把完整原始导出一次性当作当前记忆。

## 事实状态标签

- `confirmed`：用户明确说过、选择过，或继续推进而按项目规则默认确认。
- `stage`：当前阶段事实，后续仍可由用户修改。
- `proposed`：模型补写或路线建议，尚未被用户推进确认。
- `revoked`：曾经出现但被用户明确改掉的内容；不得继续沿用。
- `conflict`：来源冲突，必须停下来让用户裁定。
- `source-only`：原始 DOCX 或原文中的参考设定，不自动等于本条游戏线已经发生。

## 最高规则

- 用户是剧情总导演，77 是用户操控的玩家角色。
- 用户本轮最新修改高于旧记忆；修改一个事实时，依赖它的后续内容也必须失效。
- 模型提案不会因为写得很完整就自动成为事实；用户继续选择或推进才按默认规则确认。
- 原著未被用户改写的部分按原著大方向提醒，但不能擅自制造重大新转折。
- 元讨论（Skill、导出、GitHub、记忆整理、工具和安装）不进入剧情 Canon。
- 路鸣泽/小魔鬼的默认出场层级是精神空间、幻觉、心声或手机通讯；精神场景中的人形动作不等于现实实体。与奶妈/保姆三人组的交流默认是心声/通讯；借体必须有明确触发。

## 当前项目文件

- `../roleplay-game-writer/SKILL.md`：文学化表达、作者主导、确认/撤销和输出契约。
- `01_WORLDLINE.md`：世界与玩家核心设定。
- `02_CHARACTER_STATE.md`：人物档案和当前关系。
- `03_EVENT_LEDGER.md`：事件与因果链。
- `04_INFORMATION_MAP.md`：信息差和保密边界。
- `05_CURRENT_STATE.md`：东京龙渊当前入口。
- `06_PROPOSAL_LEDGER.md`：提案状态账本。
- `07_SOURCE_POLICY.md`：来源优先级与净化边界。
- `08_SOURCE_MAP.md`：证据文件和阶段分段索引。
- `09_FORESHADOWING.md`：伏笔和剧情债。
- `10_SYNC_STATE.md`：同步状态；当前 GitHub 写入关闭。
- `11_CONTINUITY_CHECKLIST.md`：每轮写作和交付检查。
- `episodes/`：按阶段切分的详细回合证据层。

