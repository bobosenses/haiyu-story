# 其他成片平台（简表）

三条都是「剧本之后做出画面」的开源工作台，不是纯编剧技能。安装只作入口说明，命令以各仓库 README 为准（核对日期 **2026-11-04**）。选型见 [workflows/ai-pipeline-picks.md](../../workflows/ai-pipeline-picks.md)。

## ArcReel

- 仓库：<https://github.com/ArcReel/ArcReel>
- 上游快速开始：<https://github.com/ArcReel/ArcReel#快速开始>
- 上游文档首页：<https://docs.arc-reel.com/>
- 中文产品页（调研档案所记）：<https://arc-reel.com/zh/>
- 许可证：**AGPL-3.0**，另有 `NOTICE`。商用、白标或闭源部署前读仓库「许可证与商业使用」。

适合小说、成品剧本做成漫剧或解说短片，需要角色场景道具一致，并且希望导出**中国大陆版剪映草稿**继续剪的人。上游写明与 CapCut 的兼容尚未验证。

怎么开始：README 要求 Docker 与 Docker Compose，克隆后在 `deploy/` 里复制环境文件并 `docker compose up -d`。当时写的访问地址是 `http://localhost:1241`，默认用户名 `admin`，密码在留空时由首次启动写回 `deploy/.env`。端口、账号和「不要直接暴露到公网」的警告以 README 为准。登录后在设置里配置 Agent 与文本、图像、视频能力。更长的第一次使用路径在上游的[入门教程](https://docs.arc-reel.com/guide/getting-started)。

## LocalMiniDrama

- 仓库：<https://github.com/xuanyustudio/LocalMiniDrama>
- 上游快速开始：<https://github.com/xuanyustudio/LocalMiniDrama#-快速开始>
- 发布页：<https://github.com/xuanyustudio/LocalMiniDrama/releases>
- Gitee 镜像（本仓库精选表已收录）：<https://gitee.com/bi_shang_a/localminidrama>
- 许可证：**MIT**。

适合希望故事、素材留在本机的人。上游流程是：故事 → 多集剧本 → 角色 / 场景 / 道具 → 分镜 → 图和视频 → 合成。也有画布模式，和列表共用数据。

怎么开始：README 把 **Windows 安装包**放在推荐位（标准版与 Lite 版，文件名随版本变化，去 Releases 看）。装好后在「AI 配置」填 API Key。源码方式要求 Node.js ≥ 18，前后端命令、端口和 Docker 说明在 README 与仓库 `docs/quickstart.md`，这里不另写一套。首次配置文件路径亦见 README。

## LumenX

- 仓库：<https://github.com/alibaba/lumenx>
- 上游快速开始：<https://github.com/alibaba/lumenx#-快速开始>
- 许可证：**MIT**。

适合小说文本进、漫剧视频出，并且准备使用上游所接的模型（README 中 DashScope 的万相等为文本分析与部分生成的路径）。产品分成 Studio（剧本分析 → 资产 → 分镜视频 → 配音 → 合成）和 Playground（单独生图生视频）。

怎么开始：上游环境要求 **Python 3.11+**、**Node.js 18+**、**FFmpeg**。克隆后复制 `.env.example` 为 `.env`，填写 `DASHSCOPE_API_KEY`（上游标为必填），再用 README 中的 `npm run dev` 或前后端分开的命令启动。当时写的页面是前端 `http://localhost:3008`、API 文档在后端 `17177`。端口和模型表会变，以 README 为准。

没有 DashScope 配额时不要期待这条链路能出片；可改回只写剧本，或换成本地优先的 LocalMiniDrama / 自托管的 Toonflow，并自己准备模型。
