# 只写剧本

从选题到可拍分集，停在文本。单集按 **60–120 秒** 写。确认对白之前不要开视频生成。

工具可选。手写用 [templates/](../templates/)。若要 Agent 技能，对照 [选型](./ai-pipeline-picks.md)：专业编剧流程看 [short-drama](../docs/getting-started/short-drama.md)，原著改编看 [drama-skills](../docs/getting-started/drama-skills.md) 或 [shuohao-skills](../docs/getting-started/shuohao-skills.md)，几十集到上百集的工业结构看 [short-drama-factory](../docs/getting-started/short-drama-factory.md)。

## 1. 选题

用三句话写完，写不完就换题：

1. 谁被压在一个具体处境里。
2. 观众为什么站他/她。
3. 第一集前 3 秒能看见什么（动作或反差，不是世界观说明）。

记下原著状态：原创，或已获授权。未授权小说不要进入下一步。

## 2. 系列设定

填写 [templates/series-bible.md](../templates/series-bible.md)。

- 世界观只留能拍出来的规则，最多三条。
- 全剧只留一个必须被回答的问题。
- 主要角色各建一张 [角色卡](../templates/character-card.md)，先写欲望、秘密和一句外形锁。

## 3. 多集大纲

填写 [templates/outline-multi-ep.md](../templates/outline-multi-ep.md)。

- 一行一集：开场已发生的事、本集翻转、结尾钩子。
- 先写前 3 集。前 3 集站不住，不要铺到第 30 集。
- 付费墙是可选项。要用就卡在一次已经演出来的反转之后。

## 4. 分集

对要写的那一集：

1. 用 [场次节拍](../templates/scene-beat.md) 把这一集拆成少数几场。每场写「谁要什么、被什么挡住、结束时变了什么」。
2. 再填 [单集剧本](../templates/episode-script.md)。`△` 只写看得见的动作；对白用角色卡里的说话习惯。
3. 一场写完就念一遍。超秒就删说明，不删冲突。

一次只写一集或一个小批次。大纲改了，就回改设定里被推翻的事实。

## 5. 自检

每一集过一遍：

- [ ] 60–120 秒能念完（或你在大纲里声明的别的时长）
- [ ] 前 3 秒已经出事
- [ ] 有一次观众能看懂的翻转
- [ ] 结尾钩子是新问题，不是把情绪解释完
- [ ] 角色没有突然换口吻、换造型而不记录
- [ ] 没有连续多句纯解释

## 6. 合规

- [ ] 不把未授权作品改头换面当原创
- [ ] 不写依赖真实违法操作才能成立的情节
- [ ] 暴力、亲密、未成年人相关内容若出现，已在系列设定里标明尺度；拿不准就删
- [ ] 准备投平台时，再按该平台现行规范看一遍

用 [short-drama](../docs/getting-started/short-drama.md) 时，上游把这一步放在 `/review` 与 `/compliance`。用 short-drama-factory 时，上游用仓库内脚本做机检。规则以你选用的工具和平台为准。

## 完成时你手里有什么

- 一份系列设定
- 一张分集表
- 若干角色卡
- 至少一集可拍剧本

下一步若要镜头，走 [剧本到分镜](./script-to-storyboard.md)，不要在剧本未锁定时改提示词。
