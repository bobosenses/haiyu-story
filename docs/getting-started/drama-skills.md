# Drama Skills

- 仓库：<https://github.com/zenstory-ai/drama-skills>
- 上游说明：<https://github.com/zenstory-ai/drama-skills#安装>
- 项目主页（上游 README 所链）：<https://zenstory.ai/zh/drama-skills>
- 许可证：上游 README 与 License 徽章为 **MIT**。以仓库 `LICENSE` 为准。

## 适合谁

编剧、漫剧编导，希望在 Claude Code、Codex 或其他能加载 Agent Skill 的环境里，把创作决定写成可核对的 Markdown，而不是先绑死在一个画布应用上。

上游写明覆盖：原著分析 → 分集剧本 → 视觉设定 → 图片提示词与分镜 → 视频提示词 → 确认后生产 → 剪辑成片 → 审查。正文称为一组共十二个技能（页眉徽章数字若不一致，以正文和仓库目录为准）。

## 你会得到什么

上游要求分阶段维护这些文件：`剧本.md`、`视觉设定.md`、`分镜.md`、`图片提示词.md`、`视频提示词.md`，剪辑时再加 `剪辑单.md`。只做前半段就只交付对应文档。需要跨镜保持的造型写成可原样贴进提示词的短句。

图片、视频、配音、音乐在上游流程里都是先预览并明确确认，再调用外部接口。

## 怎么开始

完整安装以仓库 README「安装」为准。2026-11-04 该节写的是：

- 你已经在用支持 Agent Skill 的编程 Agent。
- 从 GitHub 安装时，终端需要能运行 `npx`；上游给出的命令是 `npx skills add zenstory-ai/drama-skills -y -g`（`-g` 为全局，更新时重新执行）。
- 脚本需要 **Python 3.9+**。剪辑成片另需 `ffmpeg` / `ffprobe` 在 PATH 中。
- 也可以按 README 把各个 `skills/*` 链接进 Claude Code 或 Codex 的技能目录，或让 Agent 打开上述仓库地址自行安装。

调用方式随环境变化。上游写明 Claude Code 用 `/short-drama`，Codex 用 `$short-drama`，也可以直接说人话。快速开始示例在上游 README，不要把示例剧情当成必须使用的题材。

## 和本仓库的关系

手写稿仍可用 [templates/](../../templates/)。若改用本技能，文件名跟随它的 `剧本.md` 等约定。只写到文本时，停在审查之前，见 [workflows/script-only.md](../../workflows/script-only.md)。

## 注意

- 生产步骤会调用你自己的模型接口，费用不在本仓库范围内。
- 供应商凭据不要写进项目文件。上游也强调凭据不进入项目。
- 原著须为你拥有或已获改编许可。
