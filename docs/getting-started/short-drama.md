# short-drama

- 仓库：<https://github.com/0xsline/short-drama>
- 上游说明：<https://github.com/0xsline/short-drama#安装方式>
- 许可证：**MIT**（上游「许可协议」）。以仓库 `LICENSE` 为准。

## 适合谁

只要微短剧**剧本**，不要视频生成。覆盖选题立项、分集撰写、质量自检、合规审核、海外格式。上游写明是纯 Markdown 规则，零额外依赖，给已经在用的 AI 编程助手当技能。

适合：国内竖屏短剧流程，或需要切到英文好莱坞场景标题格式的出海稿。不适合：已经要画布出片（改看 [Toonflow](./toonflow.md) 等）。

## 怎么开始

2026-11-04 上游「安装方式」写的是把仓库克隆到技能目录。

- 全局示例路径：`~/.claude/skills/short-drama`（Windows 示例为用户目录下的 `.claude/skills/short-drama`）。
- 仅当前项目：克隆到该项目的 `.claude/skills/short-drama`。
- 验证：启动助手后输入 `/start`，出现选题引导即表示装上。

其他 Agent 的技能目录若不同，README 没有逐一列举，见上游 README，或把仓库放在该助手能读取的技能路径。

## 上游给出的命令顺序

```text
/start → /plan → /characters → /outline → /episode → /review → /compliance → /export
```

出海时上游写 `/overseas` 再写分集。各命令的字段在仓库「命令手册」，这里不抄全。

本仓库对应的手写顺序是：[系列设定](../../templates/series-bible.md) → [角色卡](../../templates/character-card.md) → [多集大纲](../../templates/outline-multi-ep.md) → [单集剧本](../../templates/episode-script.md)，流程说明在 [workflows/script-only.md](../../workflows/script-only.md)。两边可以并行对照，不必强行合成一个文件名。

## 注意

- 技能里的题材模板和付费卡点是创作提示，不是平台审核结论。
- 合规命令不能代替你对授权和当地法律的判断。
