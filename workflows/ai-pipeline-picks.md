# 怎么选开源项目

先看你卡在哪一步，再打开对应的上手说明。链接与一句话介绍的总表在 [README](../README.md)。许可证、安装命令以各项目仓库为准；下面不重复命令。

## 按手头材料选

| 你现在有 | 先做 | 先用 | 先不要 |
|---|---|---|---|
| 一个点子，只要剧本 | [只写剧本](./script-only.md) | [short-drama](../docs/getting-started/short-drama.md)，或只填本仓库模板 | 打开画布批量生视频 |
| 小说 / 原著，要大纲、角色、可拍剧本 | 确认有改编权，再拆大纲 | [shuohao-skills](../docs/getting-started/shuohao-skills.md) 或 [drama-skills](../docs/getting-started/drama-skills.md) | 按章节数等于集数直接出片 |
| 要几十集到上百集、钩子和付费墙结构 | 先定篇幅档，再写 | [short-drama-factory](../docs/getting-started/short-drama-factory.md) | 用单集模板逐集堆设定 |
| 剧本已锁定，要分镜和提示词 | [剧本到分镜](./script-to-storyboard.md)，视频提示词再走 [H3 Ref2VA](./h3-ref2va.md) | drama-skills、shuohao 的分镜技能，或山音导演 / Seedance 分镜仓库（见该流程文末） | 换一个编剧技能把对白重写一遍 |
| 要在一张画布里把剧本、资产、视频放在一起 | 本地或自托管试一条成片 | [Toonflow](../docs/getting-started/toonflow.md) | 同时再铺三条生产线 |
| 小说改编，并且要导出剪映草稿 | 分镜确认后导出 | [ArcReel](../docs/getting-started/more-platforms.md#arcreel) | 忽略 AGPL 义务就改完拿去商用 |
| 素材和剧本必须留在本机 | 桌面或本地服务 | [LocalMiniDrama](../docs/getting-started/more-platforms.md#localminidrama) | 把唯一成稿只放在未备份的云端草稿 |
| 小说到漫剧，并接受阿里云等模型链路 | Studio 全流程 | [LumenX](../docs/getting-started/more-platforms.md#lumenx) | 没有 API 配额就期待本地白嫖视频 |

## 和本仓库模板的关系

模板是中性稿纸，不绑定上面任何一个项目。

- 手写或让模型按模板填：从 [templates/](../templates/) 开始。
- 某个 Skill 要求自己的文件名（例如 drama-skills 上游写的 `剧本.md`、`分镜.md`）时，以那个项目为准，可把模板里的字段抄过去。
- short-drama-factory 上游自带篇幅档和机检，工业稿用它的模板，不必把本仓库的 60–120 秒默认值硬套进它的长档。

## 本仓库的默认视频模型

分镜锁定之后，默认用 **MiniMax H3 Ref2VA**（全参考）写视频提示词，规范在 [h3-ref2va.md](./h3-ref2va.md)。角色锁图加音色参考；只要嗓音用 `reference`，整轨原声才用 `fully_copy`。台词放在 `detailed_description`，带 `(Sx)` 和中文原文。

画布或平台若能选模型，优先接 H3。平台怎么安装、密钥放哪里，仍看各项目上手说明和上游文档，本页不写。

## 一条足够用的顺序

```text
选题与授权
  → 系列设定 + 角色卡 + 分集大纲
  → 单集剧本自检
  → 镜头表
  → 确认关键帧
  → H3 Ref2VA 提示词
  → 再生视频、配音、剪辑
```

第 1–3 步用剧本类技能或手写。第 4 步用分镜技能或镜头表。视频提示词默认走 H3 Ref2VA，再放到 Toonflow、ArcReel、LocalMiniDrama、LumenX 这类成片平台里生成。平台里也可以改剧本，但改完要回到设定和大纲，避免前后集矛盾。

名单会变。持续跟踪可看 README 里的 [Awesome 漫剧](https://github.com/TWO-ICE/awesome-manyu)。
