# 短剧剧本 / AI 短剧开源项目与工作流调研档案

> 调研时间：2026-11-04（Asia/Shanghai）  
> 范围：GitHub Search、X 公开检索、WebSearch/WebFetch（Gitee、掘金、知乎等）  
> 说明：星标与更新时间来自本次 GitHub `search_repositories` 工具结果快照（或文中标明的 WebFetch）；**未臆造**任何星标与 URL。第三方项目许可证以各仓库 `LICENSE` 文件为准。  
> 本档案仅作信息收集，**未向任何远程仓库推送**。

---

## 1. 概览

### 1.1 结论速览

2025–2026 年，开源社区已出现一批「**短剧/漫剧生产线**」项目，大致分成三类：

1. **一站式平台**（画布/工作台）：把剧本、角色圣经、场景道具、分镜、生图/生视频、配音与合成串在一个 App 里（代表：Toonflow、火宝短剧、ArcReel、LocalMiniDrama、AID Studio、融光等）。
2. **Agent Skill / 提示词工作流**：不绑死 UI，把「选题→大纲→分集剧本→资产→分镜→提示词→审查」写成可安装的技能包（代表：drama-skills、shuohao-skills、short-drama、short-drama-factory、山音编剧大师等）。**纯写剧本优先看这一类。**
3. **导航与周边**：Awesome 合集、营销短视频工厂、白模预演、出海本地化等。

### 1.2 对「短剧剧本创作」最有用的切入顺序

| 优先级 | 方向 | 推荐入口 |
|---|---|---|
| P0 | 先把剧本结构跑通 | `zenstory-ai/drama-skills`、`0xsline/short-drama`、`eternityspring/shuohao-skills`、`lixiaoxiao9888-create/short-drama-factory` |
| P1 | 剧本→分镜表/九列表 | `Shanyin-ai/shanyin-director-master`、`liangdabiao/Seedance2-Storyboard-Generator` |
| P2 | 需要本地一站式出片验证 | `HBAI-Ltd/Toonflow-app`、`xuanyustudio/LocalMiniDrama`、`ArcReel/ArcReel` |
| P3 | 持续跟踪生态 | `TWO-ICE/awesome-manyu`、`UnderleveledBuilder/awesome-short-drama-skills` |

### 1.3 数量统计（去重后）

- GitHub Search 合并去重后相关条目约 **70+**（含小仓、演示仓、技能仓）。
- 本档案重点收录并撰写条目约 **40** 个（平台 + Skill + 关键相关）。
- 另列出星标≥50 且未在正文展开的补充仓 **11** 个。
- 虚假相关已排除示例：`Bogdanp/dramatiq`（Python 任务队列）、红果短剧「播放客户端」发行仓等。

### 1.4 通用工作流（社区共识）

```text
选题/对标拆解
  → 故事引擎 & 分集地图（钩子、反转、付费点）
  → 分集可拍剧本（对白/动作/场景）
  → 角色圣经 + 场景/道具资产（连续性锁）
  → 分镜/关键帧 + 图/视频提示词
  → 生图/生视频（Seedance / 可灵 / Wan 等）
  → TTS 配音 + 字幕
  → FFmpeg / 剪映合成成片
```

常见编排层：ComfyUI、n8n/Dify、各开源短剧 App 内置 Agent、Claude Code / Codex + Skills。

---

## 2. GitHub 项目

### 2.1 一站式短剧 / 漫剧平台
### Toonflow-app
- **仓库**: [HBAI-Ltd/Toonflow-app](https://github.com/HBAI-Ltd/Toonflow-app)
- **星标/活跃**: 20363★ · 语言 `Vue` · 最近更新（Search 快照）`2026-11-04T06:21:38Z` · License `MIT`
- **摘要**: 无限画布 + AI Agent：剧本/分镜/角色场景资产/生图生视频，可本地部署、接 ComfyUI 与第三方模型。
- **为何有用**: 社区热度最高的一站式短剧/漫剧工作台，适合先跑通「创意→成片」全流程。
- **标签**: 一站式, 画布, Agent, MIT, 本地部署
### huobao-drama
- **仓库**: [chatfire-AI/huobao-drama](https://github.com/chatfire-AI/huobao-drama)
- **星标/活跃**: 16983★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-11-04T06:24:31Z` · License `NOASSERTION`
- **摘要**: TypeScript 全栈：一句话/小说 → 剧本改写 → 角色场景提取 → 分镜 → 视频 → FFmpeg 成片。
- **为何有用**: 自动化程度高，适合「少人成军」验证生产线；注意许可证可能非商业友好（社区常标注 CC BY-NC-SA，以仓库 LICENSE 为准）。
- **标签**: 一站式, 全自动, Docker, 许可证需核对
### Jellyfish
- **仓库**: [Forget-C/Jellyfish](https://github.com/Forget-C/Jellyfish)
- **星标/活跃**: 7118★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T03:17:10Z` · License `Apache-2.0`
- **摘要**: 端到端 AI 短剧生产工作台：强调从脚本到成片的一致性与工业化流水线。
- **为何有用**: 适合需要角色/场景/道具一致性管理的团队化生产。
- **标签**: 一站式, 一致性, Apache-2.0
### ArcReel
- **仓库**: [ArcReel/ArcReel](https://github.com/ArcReel/ArcReel)
- **星标/活跃**: 6123★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T06:23:45Z` · License `AGPL-3.0`
- **摘要**: Agent 驱动自托管工作台：小说/剧本 → 角色场景道具 → 分镜 → 视频 → 剪映草稿；费用追踪。
- **为何有用**: 网文改编链路完整，可导出剪映草稿继续精剪；AGPL-3.0 商用需注意开源义务。
- **标签**: 网文改编, Agent, 剪映, AGPL-3.0
### LocalMiniDrama
- **仓库**: [xuanyustudio/LocalMiniDrama](https://github.com/xuanyustudio/LocalMiniDrama)
- **星标/活跃**: 2336★ · 语言 `JavaScript` · 最近更新（Search 快照）`2026-11-04T02:33:19Z` · License `MIT`
- **摘要**: 本地优先（SQLite+本地文件）：故事→多集剧本→角色/场景/道具→分镜→视频合成，支持真人剧与漫剧。
- **为何有用**: 数据不出本机，对隐私与素材沉淀友好；Gitee 有镜像。
- **标签**: 本地优先, MIT, 真人剧, 漫剧
### dramaclaw
- **仓库**: [dramaclaw/dramaclaw](https://github.com/dramaclaw/dramaclaw)
- **星标/活跃**: 7080★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T04:38:04Z` · License `NOASSERTION`
- **摘要**: 通用 AIGC 视频引擎：声称剧本到成片一条流水线。
- **为何有用**: 可作为全流程引擎参考；许可证多为 Elastic-2.0 一类，商用前必读 LICENSE。
- **标签**: 引擎, 流水线, 许可证需核对
### printfilm
- **仓库**: [yi1108/printfilm](https://github.com/yi1108/printfilm)
- **星标/活跃**: 7415★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T05:11:42Z` · License `MIT`
- **摘要**: AI 短视频营销与短剧创作平台（含模板、管理后台等）。
- **为何有用**: 若目标含营销向短片/短剧批量生产可参考。
- **标签**: 短视频, 短剧, MIT
### moyin-creator
- **仓库**: [MemeCalculate/moyin-creator](https://github.com/MemeCalculate/moyin-creator)
- **星标/活跃**: 4823★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-11-04T05:14:06Z` · License `AGPL-3.0`
- **摘要**: AI 影视生产级工具，支持 Seedance 2.0，剧本到成片批量化。
- **为何有用**: 偏生产级批量；AGPL。
- **标签**: 批量化, Seedance, AGPL-3.0
### lumenx
- **仓库**: [alibaba/lumenx](https://github.com/alibaba/lumenx)
- **星标/活跃**: 1444★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-11-04T05:51:00Z` · License `MIT`
- **摘要**: LumenX Studio：小说文本 → 剧本分析 → 角色定制 → 分镜 → 动态漫剧视频。
- **为何有用**: 阿里开源短漫剧链路，适合小说改编漫剧。
- **标签**: 短漫剧, 小说改编, MIT, 阿里
### aid-studio
- **仓库**: [shijue-aid/aid-studio](https://github.com/shijue-aid/aid-studio)
- **星标/活跃**: 1293★ · 语言 `Java` · 最近更新（Search 快照）`2026-11-04T05:19:17Z` · License `MIT`
- **摘要**: AID Studio：剧本/角色场景/智能分镜/图视频/配音/成片预览，多模型可自部署。
- **为何有用**: X 上常被推荐的自托管漫剧/短剧工作室。
- **标签**: 自托管, MIT, 漫剧, 短剧
### ai-fusion-video
- **仓库**: [Stonewuu/ai-fusion-video](https://github.com/Stonewuu/ai-fusion-video)
- **星标/活跃**: 1691★ · 语言 `Java` · 最近更新（Search 快照）`2026-11-04T05:52:14Z` · License `MIT`
- **摘要**: 融光：Agent 全流程短剧/漫剧/视频创作（剧本、分镜、资产、生图生视频）。
- **为何有用**: 知乎有 NAS/Docker 部署实测文，适合折腾可控流水线。
- **标签**: Agent, NAS, MIT, 分镜
### BigBanana-AI-Director
- **仓库**: [shuyu-labs/BigBanana-AI-Director](https://github.com/shuyu-labs/BigBanana-AI-Director)
- **星标/活跃**: 2413★ · 语言 `-` · 最近更新（Search 快照）`2026-11-04T02:55:13Z` · License `NOASSERTION`
- **摘要**: 工业级一站式 AI 短剧/漫剧/导演平台，从灵感到成片。
- **为何有用**: 导演向一体化平台参考。
- **标签**: 导演台, 一站式
### LingGuo-Drama
- **仓库**: [LingGuoAI/LingGuo-Drama](https://github.com/LingGuoAI/LingGuo-Drama)
- **星标/活跃**: 1641★ · 语言 `Go` · 最近更新（Search 快照）`2026-11-04T04:20:00Z` · License `见仓库`
- **摘要**: 灵果短剧 AI：一句话到成片的短剧/漫剧平台。
- **为何有用**: 火宝类一站式替代参考。
- **标签**: 一站式, 短剧, 漫剧
### ai-short-drama
- **仓库**: [oiuv/ai-short-drama](https://github.com/oiuv/ai-short-drama)
- **星标/活跃**: 44★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-10-26T06:34:09Z` · License `见仓库`
- **摘要**: 雪风 AI 短剧工坊：六步（剧本→角色→场景→道具→分镜→剪辑）。
- **为何有用**: 流程文档清晰，适合学习「可逐步控制」的短剧生产步骤。
- **标签**: 六步流程, 本地优先, 单机
### TypeTale
- **仓库**: [TypeTale/TypeTale](https://github.com/TypeTale/TypeTale)
- **星标/活跃**: 904★ · 语言 `-` · 最近更新（Search 快照）`2026-11-04T05:17:11Z` · License `见仓库`
- **摘要**: 字字动画：免费 AIGC 视频软件，面向 AI 短剧/电影/小说推文。
- **为何有用**: 桌面向创作工具参考。
- **标签**: 桌面, 推文, 短剧
### novanova-studio
- **仓库**: [Swayingleaves/novanova-studio](https://github.com/Swayingleaves/novanova-studio)
- **星标/活跃**: 614★ · 语言 `Java` · 最近更新（Search 快照）`2026-11-04T05:36:36Z` · License `MIT`
- **摘要**: NovaNova：Agent 驱动，无限画布、小说解析剧本、漫剧/短剧。
- **为何有用**: 画布+Agent 路线的又一实现。
- **标签**: 画布, Agent, MIT
### reveric
- **仓库**: [looplj/reveric](https://github.com/looplj/reveric)
- **星标/活跃**: 595★ · 语言 `Dart` · 最近更新（Search 快照）`2026-11-04T06:15:04Z` · License `AGPL-3.0`
- **摘要**: Agent Native 一站式 AI 小说/短剧桌面创作工作台。
- **为何有用**: 小说与短剧同屏工作台。
- **标签**: 桌面, 小说, AGPL-3.0
### FastMovieAI
- **仓库**: [xhadmincn/FastMovieAI](https://github.com/xhadmincn/FastMovieAI)
- **星标/活跃**: 433★ · 语言 `PHP` · 最近更新（Search 快照）`2026-11-02T15:09:15Z` · License `Apache-2.0`
- **摘要**: 短剧/短视频创作平台（用户/支付/内容/视频生成模块）。
- **为何有用**: 偏 SaaS 化完整平台；Gitee 有镜像。
- **标签**: 平台, Apache-2.0, Gitee
### CineGen-ShortDrama
- **仓库**: [UllrAI/CineGen-ShortDrama](https://github.com/UllrAI/CineGen-ShortDrama)
- **星标/活跃**: 568★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-11-04T01:59:17Z` · License `NOASSERTION`
- **摘要**: 开源 AI 漫剧/动画/分镜生成系统。
- **为何有用**: 漫剧与分镜向。
- **标签**: 漫剧, 分镜
### AI-Canvas-tauri
- **仓库**: [Tenney95/AI-Canvas-tauri](https://github.com/Tenney95/AI-Canvas-tauri)
- **星标/活跃**: 324★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-11-04T02:28:43Z` · License `NOASSERTION`
- **摘要**: 轻量无限画布：短剧剧本、角色、分镜、图/视频、剪辑，可接 ComfyUI/Agent/MCP。
- **为何有用**: 轻量桌面画布方案。
- **标签**: 画布, Tauri, ComfyUI
### ai-moive-studio
- **仓库**: [869413421/ai-moive-studio](https://github.com/869413421/ai-moive-studio)
- **星标/活跃**: 1652★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-03T16:56:20Z` · License `Apache-2.0`
- **摘要**: AICON：自然语言驱动无限画布工作流 Agent（剧本拆解、分镜、素材、视频）。
- **为何有用**: 画布工作流 Agent 方向。
- **标签**: 画布, Agent, Apache-2.0
### ai_story
- **仓库**: [xhongc/ai_story](https://github.com/xhongc/ai_story)
- **星标/活跃**: 1990★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T05:57:05Z` · License `见仓库`
- **摘要**: AI 视频/动漫/短剧/漫剧自动化生成工具。
- **为何有用**: 自动化生成工具链参考。
- **标签**: 自动化, 短剧, 漫剧
### director_ai
- **仓库**: [freestylefly/director_ai](https://github.com/freestylefly/director_ai)
- **星标/活跃**: 1825★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-03T12:32:22Z` · License `见仓库`
- **摘要**: 手机端 AI 漫剧：一键生成剧本、分镜及合成视频。
- **为何有用**: 移动端漫剧生产思路。
- **标签**: 移动端, 漫剧

### 2.2 剧本 / Skill / 提示词工作流（编剧优先）
### shuohao-skills
- **仓库**: [eternityspring/shuohao-skills](https://github.com/eternityspring/shuohao-skills)
- **星标/活跃**: 5974★ · 语言 `JavaScript` · 最近更新（Search 快照）`2026-11-04T06:16:06Z` · License `Apache-2.0`
- **摘要**: AI 短剧 skill 集合：拆角色、排大纲、场景道具设定、写剧本、切分镜。
- **为何有用**: 纯文本/Agent 技能层，可直接嵌进 Claude Code/Codex 做剧本与前期筹备。
- **标签**: Skill, 剧本, 大纲, 分镜, Apache-2.0
### drama-skills
- **仓库**: [zenstory-ai/drama-skills](https://github.com/zenstory-ai/drama-skills)
- **星标/活跃**: 3752★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T06:14:59Z` · License `MIT`
- **摘要**: 12 技能：原著分析→分集剧本→视觉设定→图/视频提示词→生产→剪辑→审查；Markdown 事实文件约束一致性。
- **为何有用**: 对「只写剧本/分镜文档」的编剧最友好：先产出可核对文档再花钱出片。
- **标签**: Skill, 剧本, 分镜, 审查, MIT
### short-drama
- **仓库**: [0xsline/short-drama](https://github.com/0xsline/short-drama)
- **星标/活跃**: 1554★ · 语言 `-` · 最近更新（Search 快照）`2026-11-04T03:50:35Z` · License `MIT`
- **摘要**: 专业短剧剧本创作 skill：选题立项→分集撰写→质量自检→合规审核→海外出海。
- **为何有用**: 聚焦剧本生产全流程（非视频生成），适合专业编剧工作流。
- **标签**: Skill, 编剧, 合规, 出海, MIT
### shanyin-screenwriting-master
- **仓库**: [Shanyin-ai/shanyin-screenwriting-master](https://github.com/Shanyin-ai/shanyin-screenwriting-master)
- **星标/活跃**: 1443★ · 语言 `-` · 最近更新（Search 快照）`2026-11-04T00:54:48Z` · License `MIT`
- **摘要**: 山音超级编剧大师：概念超短片到电影长片、多集剧集的全格式剧本技能。
- **为何有用**: 格式覆盖广，可与短剧/影视通用剧本结构对照学习。
- **标签**: Skill, 编剧, 多格式, MIT
### shanyin-director-master
- **仓库**: [Shanyin-ai/shanyin-director-master](https://github.com/Shanyin-ai/shanyin-director-master)
- **星标/活跃**: 621★ · 语言 `-` · 最近更新（Search 快照）`2026-11-04T01:58:52Z` · License `MIT`
- **摘要**: 导演 Agent：定调→节奏→剧本微调→分镜，输出九列分镜表 xlsx。
- **为何有用**: 剧本完成后的导演/分镜表环节。
- **标签**: Skill, 导演, 分镜表, MIT
### short-drama-factory
- **仓库**: [lixiaoxiao9888-create/short-drama-factory](https://github.com/lixiaoxiao9888-create/short-drama-factory)
- **星标/活跃**: 535★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T04:50:02Z` · License `MIT`
- **摘要**: 工业化编剧系统：一句创意/网文 → 60–100 集标准短剧剧本（含付费墙、钩子、反转、机检规则）。
- **为何有用**: 强「爆款结构/集数工业」；适合研究红果/抖音向剧本骨架。
- **标签**: Skill, 工业化, 多集, 付费墙, MIT
### manju-laoli-skill
- **仓库**: [lixiaoxiao9888-create/manju-laoli-skill](https://github.com/lixiaoxiao9888-create/manju-laoli-skill)
- **星标/活跃**: 1886★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T06:15:58Z` · License `MIT`
- **摘要**: 漫剧老李全流程 Skill 套装：总控 + 多子技能。
- **为何有用**: 漫剧向 Agent 技能包。
- **标签**: Skill, 漫剧, MIT
### awesome-short-drama-skills
- **仓库**: [UnderleveledBuilder/awesome-short-drama-skills](https://github.com/UnderleveledBuilder/awesome-short-drama-skills)
- **星标/活跃**: 1751★ · 语言 `HTML` · 最近更新（Search 快照）`2026-11-04T06:10:40Z` · License `CC0-1.0`
- **摘要**: AI 短剧/漫剧 Skill 精选合集（剧本、改编、分镜、各视频模型提示词等）。
- **为何有用**: 作为「技能包导航」收藏，CC0。
- **标签**: 合集, Skill, CC0-1.0
### Seedance2-Storyboard-Generator
- **仓库**: [liangdabiao/Seedance2-Storyboard-Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator)
- **星标/活跃**: 2757★ · 语言 `-` · 最近更新（Search 快照）`2026-11-03T19:59:42Z` · License `见仓库`
- **摘要**: Seedance 2.0 剧情剧本/分镜 Skill，强调提示词与试错成本。
- **为何有用**: 对接当前主流视频模型的分镜提示词生产。
- **标签**: Skill, Seedance, 分镜
### screen-creative-skills
- **仓库**: [VanGong1999/screen-creative-skills](https://github.com/VanGong1999/screen-creative-skills)
- **星标/活跃**: 493★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T03:22:56Z` · License `MIT`
- **摘要**: 31 个影视创作评估策划 Agent Skills。
- **为何有用**: 偏评估/策划，可补剧本立项与质量关。
- **标签**: Skill, 策划, 评估, MIT
### OnlyShot
- **仓库**: [A-cat-with-carrots/OnlyShot](https://github.com/A-cat-with-carrots/OnlyShot)
- **星标/活跃**: 350★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-04T04:54:21Z` · License `MIT`
- **摘要**: OnlyShot 工业流水线 Claude Skill：一句话→剧本/分镜/分镜图/视频/剪辑。
- **为何有用**: Skill 形态的端到端短剧流水线。
- **标签**: Skill, 流水线, MIT
### Micro-Drama-Skills
- **仓库**: [zhaihao118/Micro-Drama-Skills](https://github.com/zhaihao118/Micro-Drama-Skills)
- **星标/活跃**: 329★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-03T23:42:54Z` · License `见仓库`
- **摘要**: Claude Skills 短剧全流程：剧本、角色、分镜到视频提交。
- **为何有用**: 又一 Skills 产线实现。
- **标签**: Skill, 全流程
### llm-script-factory
- **仓库**: [oidahdsah0/llm-script-factory](https://github.com/oidahdsah0/llm-script-factory)
- **星标/活跃**: 50★ · 语言 `TypeScript` · 最近更新（Search 快照）`2026-10-30T02:05:57Z` · License `MIT`
- **摘要**: 短剧 AI 生产线：从概念到完整剧本工作流。
- **为何有用**: 小而专注的剧本工厂。
- **标签**: 剧本, LLM, MIT
### juben
- **仓库**: [VanGong1999/juben](https://github.com/VanGong1999/juben)
- **星标/活跃**: 179★ · 语言 `Python` · 最近更新（Search 快照）`2026-11-03T03:01:40Z` · License `MIT`
- **摘要**: 剧本相关仓库（影视创作技能生态中的剧本组件）。
- **为何有用**: 可与 screen-creative-skills 对照。
- **标签**: 剧本

### 2.3 相关工具与导航
### short-video-factory
- **仓库**: [YILS-LIN/short-video-factory](https://github.com/YILS-LIN/short-video-factory)
- **星标/活跃**: 6011★ · 语言 `-` · 最近更新（Search 快照）`2026-11?` · License `AGPL-3.0`
- **摘要**: 产品营销/泛内容短视频：文案、TTS、自动混剪、字幕、批量任务。
- **为何有用**: 不是短剧剧本核心，但后期混剪/批量合成可借鉴。
- **标签**: 短视频工厂, 剪辑, AGPL-3.0, 边缘相关
### director-desk
- **仓库**: [mangfufu/director-desk](https://github.com/mangfufu/director-desk)
- **星标/活跃**: 452★ · 语言 `JavaScript` · 最近更新（Search 快照）`2026-11-04T01:56:43Z` · License `MIT`
- **摘要**: AI 短剧白模预演与摄影机调度。
- **为何有用**: 分镜/镜头调度专项工具。
- **标签**: 预演, 调度, MIT
### awesome-manyu
- **仓库**: [TWO-ICE/awesome-manyu](https://github.com/TWO-ICE/awesome-manyu)
- **星标/活跃**: 星标未核验 · 语言 `-` · 最近更新（Search 快照）`2026-10-26` · License `见仓库`
- **摘要**: Awesome 漫剧：按生产流水线分类的开源工具地图，License 红绿灯，约收录 41 项目，数据可自动刷新。
- **为何有用**: 最适合作为「持续更新的导航仓库」；本调研星标未用 Search API 直接命中，故不写死星数。
- **标签**: 合集, 导航, License

### 2.4 其他相关仓（星标≥50，正文未展开）

| 仓库 | 星标 | License | 一句话 |
|---|---:|---|---|
| [sorker/ai-shotlive](https://github.com/sorker/ai-shotlive) | 349 | NOASSERTION | AI 短剧，小说、剧本、分镜、提示词、关键帧、视频、AI剪辑的一站式服务。参考shuyu-labs/BigBanana-AI-Director、shamshar |
| [jeffstric/ZJT](https://github.com/jeffstric/ZJT) | 239 | NOASSERTION | ZhiJuTong (ZJT) is an AI-powered, open-source platform specifically designed for |
| [neopen/story-shot-agent](https://github.com/neopen/story-shot-agent) | 236 | MIT | 剧本分镜智能体（PenShot）：电影/动漫/短剧/小说→分镜片段→视频提示词。基于 LLM 通过 LangGraph+LlamaIndex实现任意格式剧本的自 |
| [XiakeMan777/xiakeman-ai-short-drama](https://github.com/XiakeMan777/xiakeman-ai-short-drama) | 230 | NOASSERTION | AI漫剧 / AI仿真人短剧/Seedance2.0专用创作工具：剧本创作、剧本分析、小说改编、AI 分镜、图片资产和 Seedance2.0提示词 / 火山方 |
| [dav-niu474/huobao-drama-ai](https://github.com/dav-niu474/huobao-drama-ai) | 108 | MIT | 🎬 AI短剧创作平台 — 从剧本到成片，一站式AI短剧制作工作台。支持70+大模型(GLM5.1/DeepSeek V4/Qwen3.5等)、图片生成、视频生成 |
| [lixiaoxiao9888-create/short-drama-teardown](https://github.com/lixiaoxiao9888-create/short-drama-teardown) | 86 | - | 🔍 扒剧引擎 Short-Drama Teardown V3.1 · 把爆款短剧从成片视频逆向还原为逐字稿、标准剧本与骨架分析卡。双通道门禁锁（发链接 vs 直 |
| [xixihhhh/ai-short-drama-skill](https://github.com/xixihhhh/ai-short-drama-skill) | 83 | MIT | Dramake：面向 Codex、Claude Code、WorkBuddy 的文字转 AI 短剧 Skill；串起剧本、分镜、Wan 3/Seedance/M |
| [GitXarmoron/BigBanana-AI-Director](https://github.com/GitXarmoron/BigBanana-AI-Director) | 69 | NOASSERTION | BigBanana AI Director是一个工业级一站式  AI 短剧，AI 漫剧,AI 导演平台，面向创作者，实现从灵感到成片的高效生产。  它摇弃了传统 |
| [15673312611/AnimaHub](https://github.com/15673312611/AnimaHub) | 68 | - | ai漫剧/动漫/动态漫/短剧生成系统。支持小说导入转剧本  一键实现文本到 AI 动漫的自动化创作   |
| [Xiao-rx/Douyin-Micro-Horror-Studio](https://github.com/Xiao-rx/Douyin-Micro-Horror-Studio) | 68 | MIT | 抖音/红果微恐漫剧/短剧/动画短剧「半自动化」生产工具链：基于 Python 的一站式工作流和桌面端 GUI，串联全季主线规划、剧本创作、世界观与人物设定、视觉 |
| [VanGong1999/skills](https://github.com/VanGong1999/skills) | 51 | - | 剧本｜ 热门短剧剧本|拉片分析 |

---

## 3. Gitee / 中文平台

### 3.1 Gitee 镜像与项目（WebSearch）

| 名称 | URL | 说明 |
|---|---|---|
| LocalMiniDrama | https://gitee.com/bi_shang_a/localminidrama | GitHub 项目的 Gitee 镜像/分发，本地短剧工作流 |
| Toonflow-app | https://gitee.com/HBAI-Ltd/Toonflow-app | 官方/社区 Gitee 镜像，国内克隆更快 |
| FastMovieAI | https://gitee.com/yc_open/FastMovieAI | 开源短剧/短视频平台（Apache-2.0，页面显示星标信息以站点为准） |
| Yihen-Drama | https://gitee.com/yi-mark/yihen-drama-studio | AI 短剧平台：章节提取→资产→分镜→视频任务，Docker 全家桶 |

### 3.2 掘金

- [2026AI短剧本地一键部署方案](https://juejin.cn/post/7621389051503083555)（2026-03-26）  
  归纳流程：剧本 → 角色/场景一致性 → 分镜图 → 图/文生视频 → 剪辑。  
  推荐优先级提及：OpenClaw+漫剧 Skills、Toonflow、Jellyfish/LocalMiniDrama、ComfyUI、ai_story、Huobao Drama 等。  
  强调纯本地视频模型显存门槛高，多数方案仍是「本地编排 + 云端视频 API」混合。

### 3.3 知乎

- [用 NAS 搭短剧工厂：融光 `Stonewuu/ai-fusion-video`](https://zhuanlan.zhihu.com/p/2036533363322902176)  
  实测向：剧本→分镜→角色资产→参考图→视频，强调先控流程再花钱出片。
- 另有短剧编剧商业/教程向文章（如「AI 短剧创作」题材），偏方法论而非开源仓列表；以及 SkyReels 等视频基座模型讨论（偏模型层，非剧本工具）。

### 3.4 Bilibili / CSDN / HelloGitHub

- B 站：社区与 X 帖均指向「AIGC短剧教程」关键词；Toonflow 文档中出现过上手视频链（如 BV1na6wB6Ea2，见 Gitee README 摘要）。本次未逐条抓取 B 站开放仓库列表。
- CSDN / HelloGitHub：本次 WebSearch 未返回与上述头部项目不同的独立高价值开源仓；建议以 GitHub/`awesome-manyu` 为主索引。

---

## 4. X 上的线索

检索工具：`x.search_posts_all`（公开读），查询含「短剧剧本 开源/github/工作流」「Toonflow/huobao/ArcReel」等。  
下列均为工具返回中的真实帖子链接；星标数字若出现在帖文中为博主口述，**以 GitHub 快照为准**。

| 作者 | 帖子 | 要点 |
|---|---|---|
| @awe0_io | https://x.com/awe0_io/status/2114611392984862855 | 推荐 Toonflow 与 short-video-factory；配合 Codex/Claude |
| @Duoduorimi | https://x.com/Duoduorimi/status/2112202027694698717 | 完整列出 6 工具：Toonflow、火宝、LocalMiniDrama、ArcReel、LumenX、黄果（平台型，非开源仓） |
| @aoteman1can | https://x.com/aoteman1can/status/2111774290018504905 | 推荐 AID Studio（剧本到成片） |
| @Breitenberiv9m | https://x.com/Breitenberiv9m/status/2109124171720687644 | 「7 个 GitHub 项目」清单开篇，首推 Toonflow |
| @maskghost975 | https://x.com/maskghost975/status/2109285174861254843 | 6 个 AI 短剧/漫剧项目，含火宝 |
| @Huahuazo | https://x.com/Huahuazo/status/2111478340247065028 | 「2026 六大 AI 短剧开源」排序帖（Toonflow 起） |
| @huoshan007 | https://x.com/huoshan007/status/2110191359818596527 | 同主题六大开源推荐（高互动） |
| @lujunneng | https://x.com/lujunneng/status/2110050773371658689 | 「GitHub AI 短剧与影视创作项目集合」调研帖（正文被截断，需点进帖看全文） |
| @CY160909 | https://x.com/CY160909/status/2113964593722662971 | Toonflow、Jellyfish 等；另帖推荐 AI Video Production Editor |
| @KOF97AI | https://x.com/KOF97AI/status/2117100245867983331 | 高星 6 项目，火宝起 |
| @bkdgiffug | https://x.com/bkdgiffug/status/2109073242333884691 | 高星清单，火宝为首 |
| @superfang119 | https://x.com/superfang119/status/2117829739708891581 | 「Agent 无限创作」类小说转长视频开源流水线讨论 |
| @peng11_ai | https://x.com/peng11_ai/status/2112114152672047594 | Toonflow、ArcReel 等 |
| @grok | https://x.com/grok/status/2113308317334286638 | 工作流摘要：LLM 写剧本分镜 → Seedream 资产 → Seedance/可灵视频 → TTS → 剪映/FFmpeg；串联 ComfyUI/n8n/Dify/ArcReel/短剧 skill |

**注意**：同期 X 上大量「黄果短剧」硬件/本地 Wan 模型讨论偏成人内容生产，与正规短剧剧本开源路线不同，本档案不展开复现步骤。

---

## 5. 推荐工作流摘要

### 5.1 只写剧本（推荐起步）

1. 安装/导入 `drama-skills` 或 `short-drama` / `shuohao-skills` 到 Claude Code 或 Codex。  
2. 固定产出 Markdown：`剧本.md`、角色/场景设定、分集地图。  
3. 用 `short-drama-factory` 或山音编剧技能补「钩子/反转/付费墙/集数工业结构」。  
4. 用 `shanyin-director-master` 或 Seedance 分镜 Skill 导出分镜表，再决定是否进视频工具。

### 5.2 小说/网文 → 短剧成片

1. 文本进入 ArcReel / Toonflow / LumenX / LocalMiniDrama。  
2. 人工确认：分集切点、角色定妆、关键场次。  
3. 视频模型：Seedance / 可灵 / 本地 Wan 等（按预算）。  
4. 导出剪映草稿或 FFmpeg 成片。

### 5.3 本地优先 / NAS

1. LocalMiniDrama 或 Toonflow 桌面/Docker。  
2. 融光（ai-fusion-video）知乎 NAS 方案。  
3. 编排层可用 ComfyUI；掘金文亦提到 OpenClaw + 漫剧 Skills。

### 5.4 License 红绿灯（社区共识摘要，非法律意见）

| 类型 | 例子 | 商用注意 |
|---|---|---|
| MIT / Apache-2.0 | Toonflow、LocalMiniDrama、Jellyfish、LumenX、多数 Skills | 相对宽松，保留声明 |
| AGPL-3.0 | ArcReel、moyin-creator、short-video-factory | 网络提供修改版常需开源 |
| CC BY-NC-SA / Elastic 等 | 社区对火宝、部分引擎的标注 | **禁止或限制商用/托管**，以仓库 LICENSE 为准 |

---

## 6. 可直接复用的链接清单

### 平台
- https://github.com/HBAI-Ltd/Toonflow-app
- https://github.com/chatfire-AI/huobao-drama
- https://github.com/Forget-C/Jellyfish
- https://github.com/ArcReel/ArcReel
- https://github.com/xuanyustudio/LocalMiniDrama
- https://github.com/alibaba/lumenx
- https://github.com/shijue-aid/aid-studio
- https://github.com/Stonewuu/ai-fusion-video
- https://github.com/oiuv/ai-short-drama
- https://toonflow.net （Toonflow 主页，WebSearch）
- https://arc-reel.com/zh/ （ArcReel 主页，WebSearch）

### Skill / 剧本
- https://github.com/zenstory-ai/drama-skills
- https://github.com/eternityspring/shuohao-skills
- https://github.com/0xsline/short-drama
- https://github.com/Shanyin-ai/shanyin-screenwriting-master
- https://github.com/Shanyin-ai/shanyin-director-master
- https://github.com/lixiaoxiao9888-create/short-drama-factory
- https://github.com/UnderleveledBuilder/awesome-short-drama-skills

### 导航 / 中文镜像 / 文章
- https://github.com/TWO-ICE/awesome-manyu
- https://gitee.com/HBAI-Ltd/Toonflow-app
- https://gitee.com/bi_shang_a/localminidrama
- https://gitee.com/yi-mark/yihen-drama-studio
- https://juejin.cn/post/7621389051503083555
- https://zhuanlan.zhihu.com/p/2036533363322902176
- https://openmicrodrama.com/guides/open-source-pipeline-self-hosting （英文自托管指南，WebSearch）

### 周边
- https://github.com/YILS-LIN/short-video-factory
- https://github.com/dramaclaw/dramaclaw
- https://github.com/yi1108/printfilm

---

## 7. 调研局限与未覆盖点

1. 部分 X 长帖 `note_tweet` 未完整返回（如 @lujunneng、@Huahuazo、@CY160909），列表可能不全。  
2. GitHub WebFetch 对部分仓显示「0 stars」与 Search API 不一致，**以 Search 快照为准**。  
3. `TWO-ICE/awesome-manyu` 的仓库自身星标本次 Search 未命中，仅确认 URL 与页面内容摘要。  
4. 未执行任何 `git push` / 创建 GitHub 仓库；等待用户空仓链接后再上传。  
5. 成人向「黄果」本地流水线仅作生态现象记录，不提供复现指南。

---

*档案结束*
