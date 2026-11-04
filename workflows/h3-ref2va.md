# MiniMax H3 参考生成（Ref2VA）传参与台词规范

> 本仓库短剧成片默认按 **MiniMax H3** 全参考模式写提示词。  
> 依据上游：[MiniMax-H3 h3-prompt-writing](https://github.com/MiniMax-AI/MiniMax-H3) 的 `references/ref-en.txt`（2026-11-04 快照）。  
> 剧本锁定后再走本文件；不要在对白未定稿时改 H3 提示词。

## 何时用哪种模式

| 模式 | 用途 |
|---|---|
| T2VA / I2VA / FL2VA / L2VA | 无整套参考素材时的基础音画生成 |
| **Ref2VA（全参考）** | 有角色锁图、音色参考、分镜板、动作/剪辑参考时（短剧默认） |

短剧建议：**角色锁图 + 音色参考音频 +（可选）分镜板图** → Ref2VA。

## 六段式顺序（不可打乱）

1. `subject_definitions` — 定义 `<Subject>` / `<Picture>` / `<Video>` / `<Audio>`  
2. `summary` — 方括号任务类型 + 一句话关系  
3. `retention_analysis` — 保留强度  
4. `detailed_description` — 按播放顺序的镜头、动作、**台词**  
5. `overall_soundscape` — 环境声 / 物理声  
6. `non_diegetic_music` — 观众向配乐（无则 `N/A`）

正文用英文；**台词、歌词、画面可见文字保留原文**。

## 参考素材怎么传（分工一物一责）

上传顺序习惯：图片 → 视频 → 独立音频。提示词里用标签引用：

| 标签 | 管什么 | 短剧常见用法 |
|---|---|---|
| `<Subject N>` | 可复用的可见内容（人/景/道具/动作） | 角色脸与服装锁 |
| `<Picture N>` | **整图当帧锚**（首帧/关键帧/分镜板） | 仅当它真是帧或分镜板时单独定义；只锁脸则写进 Subject |
| `<Video N>` | 整段视频关系（剪辑源/续写/运镜结构） | 运镜或剪辑节奏参考 |
| `<Audio N>` | 独立音频轨 | **音色参考**或整轨复用 |

同一参考视频里的画面与声音：`<Video>` 与 `<Audio>` **各自独立编号**，不强制同号配对。视频文件自带声音 ≠ 必须定义 Audio；只有真要用那段声音才建 `<Audio>`。

### 素材上限（常见实现）

- 图片最多约 9、视频最多约 3、独立音频最多约 3（以实现为准）  
- 每个文件在提示词里写清：**编号 + 唯一用途**（脸 / 动作 / 音色 / 节奏），不要一个文件身兼多职却不写清。

## 音频传法（最关键）

在 `subject_definitions` 里先定性，再在 `retention_analysis` 用固定英文标记：

| 标记 | 含义 | 短剧何时用 |
|---|---|---|
| `fully_copy` | 整段音频 1:1 作为成片最终音轨 | 已录好整轨对白/现场声，直接贴片 |
| `partially_copy` | 只复制时间轴局部或某层，其余另加/替换 | 保留一段环境声，换对白层 |
| `reference` | **不复制波形**；只借音色、节奏、语气、音乐风格 | **角色音色锁**：用参考音定 `(S1)` 嗓音，台词写新稿 |
| `weak_reference` | 仅大类/氛围相似 | 弱风格参考 |

音色绑定示例（定义里复用目标片说话人 ID，不在 Audio 段重新编号）：

```text
<Audio 1> is the voice-timbre reference for <Subject 1> (S1).
```

```text
<Audio 1>: reference - vocal timbre and measured delivery guide <Subject 1> (S1); do not copy the original signal or original lines.
```

**硬规则**

1. 只要音色 → 用 `audio reference` + `reference`，**禁止**把参考音频里的旧台词带进新片。  
2. 要整轨原声 → 用 `audio reuse` + `fully_copy` / `partially_copy`。  
3. 台词正文只写在 `detailed_description` 的对话标签里；**不要**在 `overall_soundscape` / `non_diegetic_music` 重复台词。  
4. 环境声归 `overall_soundscape`，观众配乐归 `non_diegetic_music`；参考音频属于哪一层，就在哪一层声明关系。

`summary` 任务类型前缀可组合，例如：

```text
[reference generation + audio reference]
[video editing + audio reuse]
[video continuation + keyframe completion + audio reference]
```

## 台词在提示词里怎么写

1. 按目标片**真实发声顺序**固定 `(S1)` `(S2)`…，全程不改号。  
2. 可见角色说话：同时保留视觉标签与说话人 ID：`<Subject 1> (S1) says ...`  
3. 台词放在对话标签内，保留原语言：`<d>[Chinese] 原句。</d>`（实现里标签名以官方指南为准；语义为「语言标记 + 原文台词」）。  
4. 句末用 `.` `?` `!`；听不清写 `[unclear]`，禁止瞎猜。  
5. 画外音：标明 `off-screen` / voiceover，并写明嘴唇闭合。  
6. 跨镜头连续说话用官方连续性描述（跨切 / 被片尾截断等），不要拆成两句互不相关的新台词。  
7. 仅当「整轨 BGM/原声里顺带有一句、且没有独立发声主体」时，才用 `<Audio>` 作为可听来源、不再另造 `(Sx)`。

示例骨架：

```text
<Subject 1> (S1) says in a tense young female voice referenced from <Audio 1>, <d>[Chinese] 我先转一半行吗？</d>
```

## 短剧一镜打包清单

生成每一镜 / 每一小段 H3 提示词前勾选：

- [ ] 剧本该场对白已锁定（与 `episode-script` 一致）  
- [ ] 每角色有锁图 → Subject；音色参考 → Audio + `reference`  
- [ ] 每个参考文件只写一个主用途  
- [ ] `retention_analysis` 音频标记与用途一致（音色绝不用 `fully_copy`）  
- [ ] 台词在 `detailed_description`，环境声与配乐分栏  
- [ ] 不想要配乐时 `non_diegetic_music: N/A`

## 与本仓库工作流的衔接

1. [workflows/script-only.md](./script-only.md) 完成并锁定剧本  
2. [workflows/script-to-storyboard.md](./script-to-storyboard.md) 拆镜头表  
3. **本文件**：按镜头填 Ref2VA 六段式 + 素材槽位表（图片编号 / 音频编号 / `(Sx)`）  
4. 再提交 H3 生成；改台词必须同步改 `detailed_description`，不要只改素材文件名

## 素材槽位表（复制到每集）

| 槽位 | 文件 | 用途 | H3 标签 | retention |
|---|---|---|---|---|
| 图1 | | 锁林夏脸+服装 | Subject 1 ← Picture 1 | fully_preserved |
| 图2 | | 锁周妍 | Subject 2 ← Picture 2 | fully_preserved |
| 音频1 | | 林夏音色 | Audio 1 → (S1) | reference |
| 音频2 | | 阿凯音色（画外） | Audio 2 → (S2) | reference |
