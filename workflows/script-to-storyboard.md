# 剧本 → 分镜 → 镜头表 → 提示词

输入是已经通过 [只写剧本](./script-only.md) 自检的一集。这一步仍不直接花钱生视频：先把镜头和提示词落成文字，确认后再交给 Toonflow、ArcReel、LocalMiniDrama、LumenX 或你自己的模型界面。

## 1. 锁定剧本

- 对白和场次以 [单集剧本](../templates/episode-script.md) 为准。
- 角色外形以 [角色卡](../templates/character-card.md) 的「外形锁」为准。
- 发现不可拍（纯心理、没有画面）时，改剧本或 [场次节拍](../templates/scene-beat.md)，不要在提示词里补设定。

## 2. 从节拍拆镜

一场里一个清楚动作一块镜头。短剧单镜常见大约 **2–5 秒**，一集合计仍落在大纲里的秒数（默认 60–120 秒）。

每镜只回答：谁、在做什么、观众新看到什么。做不到就合并或删掉。

## 3. 镜头表

复制到该集文件里填写。这不是某一上游产品的固定列名；山音导演等工具若输出自己的表，以那个仓库的说明为准。

| 镜号 | 秒 | 景别 | 画面（谁在做什么） | 对白 / 声 | 运镜 | 要用的参考 |
|---:|---:|---|---|---|---|---|
| 1 | | 近 / 中 / 全 | | | 固定 / | 角色卡外形锁 |
| 2 | | | | | | |

景别和运镜写人话即可。对白必须能在单集剧本里找到原句，不要另写一套词。

## 4. 提示词

一镜一条，四行就够：

1. **锁**：外形锁 + 场景（时代、地点、光线），与上一镜相同的部分原样复制。
2. **本镜**：这一秒发生的动作和景别。
3. **声音**：对白原句或「无对白」。
4. **不要**：不能出现的人、现代物、文字，除非剧本要求。

先要静止关键帧。关键帧里的脸、衣服、道具和镜头表一致后，再写视频提示词（在关键帧上增加动作和运镜）。未确认关键帧之前不提交视频任务。

## 5. 交给工具

| 你要的结果 | 看 |
|---|---|
| 仍在 Agent 里写分镜和提示词文件 | [drama-skills](../docs/getting-started/drama-skills.md) 或 [shuohao-skills](../docs/getting-started/shuohao-skills.md) |
| 导演向分镜表 | [山音导演大师](https://github.com/Shanyin-ai/shanyin-director-master)（上游写明输出九列分镜表；列定义见该仓库） |
| 视频模型向的分镜提示词 | [Seedance2 Storyboard Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator) |
| 画布里接着出图、出视频 | [Toonflow](../docs/getting-started/toonflow.md) 及 [ArcReel / LocalMiniDrama / LumenX](../docs/getting-started/more-platforms.md) |

选型对照见 [ai-pipeline-picks.md](./ai-pipeline-picks.md)。

## 6. 出片前再看一眼

- [ ] 镜号秒数相加等于这一集的目标时长
- [ ] 每条提示词都能指回某一镜，没有剧本里没有的新情节
- [ ] 同一角色的外形锁没有在中途被改写
- [ ] 关键帧确认记录写在镜头表「参考」列或单独一行
- [ ] 模型 API 费用你自己承担；本仓库不代选供应商

## 7. 分镜之后写 H3 提示词

镜头表确认后，视频提示词按 [h3-ref2va.md](./h3-ref2va.md) 写 MiniMax H3 全参考（Ref2VA）。

- 只要音色、不要参考音频里的旧台词：用 `reference`。整段已录好的原声才用 `fully_copy`（局部沿用用 `partially_copy`）。
- 台词只写在 `detailed_description`：说话人编号 `(S1)` `(S2)` 全程不改，中文原句保留，例如 `<Subject 1> (S1) says ... <d>[Chinese] 原句。</d>`。
