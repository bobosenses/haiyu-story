# Short-Drama Factory

- 仓库：<https://github.com/lixiaoxiao9888-create/short-drama-factory>
- 上游说明：<https://github.com/lixiaoxiao9888-create/short-drama-factory#快速开始>
- 许可证：**MIT**（上游徽章与文末）。以仓库 `LICENSE` 为准。

## 适合谁

要**纯剧本**、并且要抖音 / 红果一类多集工业结构的人：一句创意或网文进，产出带钩子、反转和可选付费墙的分集剧本。上游写明不碰分镜、资产和视频。

不适合第一集还没立住、只想写 60–120 秒单集试水的情况。那种用 [short-drama](./short-drama.md) 或 [templates/episode-script.md](../../templates/episode-script.md) 即可。

## 上游自己的篇幅

以 README「篇幅三档」为准（2026-11-04）：

| 档 | 单集时长 | 全剧集数档（上游表） |
|---|---|---|
| 标准（默认） | 90–120 秒 | 60 / 80 / 100 |
| 长档 | 150–195 秒 | 30 / 40 / 50 |
| 漫剧 | 60–90 秒 | 60 / 80 / 100 |

本仓库模板默认的 60–120 秒是中性稿纸，**不要**拿去覆盖这个项目已选档位。选定档位后全程用它的模板和机检。

## 怎么开始

README「快速开始」只写：**安装到技能目录后直接对话**，例如「写短剧」「立项：……」以及 `/长档大纲`、`/连写` 等模式。它**没有**在该段给出固定的克隆目标路径，因此这里不编造安装目录。见上游 README 与仓库内 `SKILL.md`。

同一节给出的自测（在已克隆的仓库里，Windows 用 `python`，macOS / Linux 用 `python3`）：

- `scripts/validate_episode.py --self-test`
- `scripts/validate_series.py --self-test`

示例剧本文档路径也在该节，用来看格式，不是必须沿用的题材。

上游列出的对话模式包括：`/立项大纲`、`/全剧大纲`、`/长档大纲`、`/分集规划`、`/写剧本`、`/写长档`、`/剧本医生`、`/极速短剧`、`/合规审核`、`/连写`。参数以 `SKILL.md` 为准。

## 和本仓库的关系

工业稿走这个仓库的 `templates/` 与 `references/`。本仓库的 [多集大纲](../../templates/outline-multi-ep.md) 只适合先手排一条轻量地图；一旦进入本工厂的档位和机检，以工厂模板为交付格式。

## 注意

- 机检通过不等于平台会过审，也不等于可商用改编他人小说。
- 上游面向付费短剧生态，付费墙写法是可选创作结构，投放前核对平台规则。
