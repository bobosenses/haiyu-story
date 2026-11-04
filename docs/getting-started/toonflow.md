# Toonflow

- 仓库：<https://github.com/HBAI-Ltd/Toonflow-app>
- 上游说明：<https://github.com/HBAI-Ltd/Toonflow-app#4--下载并安装>
- Gitee 镜像（本仓库精选表已收录）：<https://gitee.com/HBAI-Ltd/Toonflow-app>
- 许可证：2026-11-04 上游「开源许可」写明当前为 **MIT**，并注明更早版本不追溯改变（v1.0.8 之前为 AGPL-3.0，v1.0.8–v1.1.8 为 Apache-2.0 与附加协议）。你用的那一版以该版本 `LICENSE` 为准。第三方依赖和素材另计。

## 适合谁

要把剧本、角色场景、分镜图和视频片段放在**同一张无限画布**里，并且希望项目留在自己的电脑或服务器上。上游写明支持桌面、Android、Docker 和服务器部署，可接第三方模型 API，也可接本地 ComfyUI 与 LLM。

适合已经有故事、想验证能出片的人。不适合还在改前三集结构的阶段，那一步先用 [只写剧本](../../workflows/script-only.md)。

## 上游描述的制作顺序

README「如何用 Toonflow 制作 AI 短剧与漫剧」四步：

1. 在文本节点里整理故事、人物和镜头，用语言模型辅助后自己改。
2. 导入或生成角色、场景和分镜图。
3. 接上参考图，按镜头生成视频。
4. 在画布里预览、整理、下载，再去剪辑。

能生成多长的视频、有没有声音，取决于你选的模型，不是 Toonflow 固定的。

## 怎么开始

具体命令以 README「下载并安装」为准，这里只保留入口，避免抄下会过期的构建步骤。

- **客户端**：Windows、macOS、Android ARM64 的安装包在 [Releases](https://github.com/HBAI-Ltd/Toonflow-app/releases)。Android 仅 ARM64。Windows 依赖 WebView2，上游有闪退时的说明。macOS 打不开时的处理也在同一节。
- **Docker**：上游要求先有 Git、Docker Engine 与 Compose，仓库带 `Dockerfile` 与 `compose.yaml`。展开步骤、端口、数据卷和「不要用会删卷的命令」都在 README，按原文执行。
- **服务器**：同一节另有从源码构建的步骤。
- 模型 API Key 在应用里配置。软件本身按上游说明可自行部署；**调用云端模型另收费**。本地模型或 ComfyUI 需要你自己的环境和算力。

国内克隆可改用上面的 Gitee 地址，安装差异以镜像说明为准。

## 注意

- 上游写明服务端口上的页面没有独立登录。服务器部署时按 README 限制访问来源，不要把无认证端口暴露到公网。
- 配置和项目在本地 `data/` 或 Docker 数据卷里，备份时整份保留。
- 接入模型的细节，上游指向自己的使用教程和开发者文档（飞书链接在 README 常见问题中）。链接失效时仍以仓库 README 为准。
