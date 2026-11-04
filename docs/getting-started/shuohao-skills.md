# Shuohao Skills

- 仓库：<https://github.com/eternityspring/shuohao-skills>
- 上游说明：<https://github.com/eternityspring/shuohao-skills#install>
- 中文 README：仓库内 `README.zh.md`（英文 README 顶部有链接）
- 许可证：**Apache-2.0**（上游 README「License」）。以仓库 `LICENSE` 为准。

## 适合谁

把小说或已有故事做成短剧前期：改编大纲、角色圣经、场景道具、剧本、开场站位、分镜。技能设计成任何能阅读 `SKILL.md` 并运行附带脚本的 Agent 都能用；Claude Code 与 Codex 是上游点名的例子。

2026-11-04 的英文 README 列出七个技能：

| 技能 | 作用 |
|---|---|
| `novel-outline` | 小说改编为短剧大纲 |
| `novel-characters` | 角色圣经 |
| `character-refs` | 按描述生成角色参考图（这一步才需要图像模型） |
| `novel-art` | 场景与道具美术设定 |
| `novel-script` | 剧本、时长估计、开场钩子、对白本 |
| `novel-staging` | 每场开场站位 |
| `novel-storyboard` | 分段、切镜、关键帧与视频提示词 |

上游写明：大纲定改编，角色、美术和剧本一起迭代，站位在分镜之前。报告默认中文界面。

## 怎么开始

安装命令以 README「Install」为准。该节写的是克隆仓库后执行 `./scripts/install.sh`。安装器会检测 Claude Code 和 Codex，并用符号链接放好技能，因此之后 `git pull` 会直接生效。只装其中一个技能、只装进 Codex，或手工链接，同一节有说明。

环境（摘自上游 Requirements）：

- **Node.js 18+**。脚本只用标准库，没有 npm 依赖要装。
- 需要一个能读 `SKILL.md` 并跑 Node 脚本的 Agent。文本阶段用当前会话额度，上游写明不需要另配 API key。
- 只有 `character-refs` 需要图像模型（ComfyUI、Codex 出图、OpenAI 图像接口或自定义命令，首次使用时选择）。

中文说明以 `README.zh.md` 为准；若与英文页的安装段不一致，以你准备执行的那一页为准。

## 使用时知道的一件事

上游写明分镜**还不会**自动读入 `staging.json`。站位通过之后，要把开场站位句子交给 Agent，抄进每场第一段分镜。站位阶段本身不出图、不出视频。

## 和本仓库的关系

小说改编可走本技能；原创短剧、强调合规与出海命令时，更贴近 [short-drama](./short-drama.md)。镜头表的中性空表在 [workflows/script-to-storyboard.md](../../workflows/script-to-storyboard.md)。
