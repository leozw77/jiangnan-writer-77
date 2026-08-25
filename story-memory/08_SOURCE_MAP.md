# 证据分段索引

## 阶段文件

| 文件 | 回合 | 内容 |
|---|---:|---|
| `episodes/01-early-campus-ice-cellar.md` | 1-21 | 早期世界线、高架桥、调查组、夏弥洗脑、卡塞尔、自由一日、青铜线开端、第一次冰窖/爆炸 |
| `episodes/02-campus-politics-beijing-plan.md` | 22-42 | 新闻部、EVA/冰海、血统风波、加图索政治、庞贝、北京计划讨论 |
| `episodes/03-beijing-preparation.md` | 43-55 | 七宗罪测试、正式赴华、夏弥/奥丁试探、英雄救美女龙的隐藏计划 |
| `episodes/04-beijing-nibelungen-battle.md` | 56-89 | 赌博、荷官、楚子航/路明非/夏弥/芬里厄、海拉战、第二次灵魂交易、两茧收尾 |
| `episodes/05-aftermath-hidden-threads.md` | 94-105 | 记忆修正、庞贝与校长、副校长、夏弥沉睡、报告与芬格尔/EVA暗线 |
| `episodes/06-tokyo-dragon-abyss-entry.md` | 106-125 | 芬格尔改成绩、白王/日本气息、暝杀炎魔刀、正式赴日、绘梨衣目标、龙渊入口 |

## 读取建议

- 续写东京线：读取 `01_WORLDLINE`、`02_CHARACTER_STATE`、`04_INFORMATION_MAP`、`05_CURRENT_STATE`、`06_PROPOSAL_LEDGER` 和 `episodes/06...`。
- 复盘北京战：读取 `03_EVENT_LEDGER` 的第 9-10 节和 `episodes/04...`。
- 核对某条用户修正：以回合号定位 `source/plot-only-transcript.md`，再更新提案账本，不直接改写历史证据。

## 证据层与记忆层的区别

- `source/` 和 `episodes/` 保存“当时写了什么”。
- `story-memory/*.md` 保存“目前认定什么、谁知道什么、哪些已被撤销”。
- 两者冲突时，不删除证据；只在记忆账本中记录修订和依赖失效。

