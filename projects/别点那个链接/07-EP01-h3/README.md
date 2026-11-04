# EP01 · H3 Ref2VA 分镜包

剧名《别点那个链接》第 1 集「高收益群」。  
流程：`script-only` 锁定剧本 → `script-to-storyboard` 镜头表 → **`h3-ref2va` 六段式**（本目录）。

## 本目录

| 文件 | 内容 |
|---|---|
| [镜头表.md](./镜头表.md) | 21 镜 · 合计 105 秒 · 对白=剧本原句 |
| [素材槽位.md](./素材槽位.md) | Picture/Subject + Audio1/2/3；音频一律 `reference` |
| [prompts/](./prompts/) | 19 块可粘贴英文六段式提示词 |
| 本 README | 使用顺序 |

## 生成前

锁图 A–D 已在 `refs/`（`linxia_lock.png`、`zhouyan_lock.png`、`phone_ui_mock.png`、`akai_avatar.png`）。

1. 音色样片仍按 `素材槽位.md` 补齐（`audio_*_timbre.wav` 仍空）；锁图文件名保持现状，**标签编号不要改**。  
2. 确认 `05-EP01-script.md` 对白未再改；改词必须同步改对应 `prompts/*.md` 的 `<d>[Chinese]…</d>`。  
3. 画幅：**竖屏 9:16**；时长按每块文件头标注请求（约 5–8 秒）。

## 提示词生成顺序（按时间轴粘贴）

| 序 | 文件 | 时间 | 覆盖镜号 |
|---:|---|---|---|
| 1 | `01_hook-phone-face.md` | 0–5s | 01–02 |
| 2 | `02_chat-scroll.md` | 5–10s | 03 |
| 3 | `03_akai-three-slots.md` | 10–15s | 04 |
| 4 | `04_memo-delete.md` | 15–20s | 05 |
| 5 | `05_bubble-shame.md` | 20–25s | 06 |
| 6 | `06_akai-half-position.md` | 25–32s | 07 |
| 7 | `07_linxia-half-ask.md` | 32–38s | 08 |
| 8 | `08_akai-no-half.md` | 38–45s | 09 |
| 9 | `09_thumb-hover.md` | 45–50s | 10 |
| 10 | `10_shower-stop.md` | 50–55s | 11 |
| 11 | `11_zhou-snatch.md` | 55–60s | 12 |
| 12 | `12_linxia-defend.md` | 60–65s | 13 |
| 13 | `13_evidence-1.md` | 65–72s | 14 |
| 14 | `14_evidence-2.md` | 72–80s | 15 |
| 15 | `15_evidence-3.md` | 80–85s | 16 |
| 16 | `16_akai-seal.md` | 85–90s | 17 |
| 17 | `17_almost-pressed.md` | 90–95s | 18 |
| 18 | `18_incoming-call.md` | 95–102s | 19–20 |
| 19 | `19_freeze-frame.md` | 102–105s | 21 |

每块文件内已是完整六段：`subject_definitions` → `summary` → `retention_analysis` → `detailed_description` → `overall_soundscape` → `non_diegetic_music`。  
把「可粘贴正文」整段复制进 H3 Ref2VA，并挂上该块需要的 Subject / Audio 文件。

## H3 传参要点（本集）

- **音频**：`<Audio N>` + retention **`reference`**；只要音色，不要样片旧台词。  
- **台词**：只写在 `detailed_description`；格式 `(S1)/(S2)/(S3)` + `<d>[Chinese] 原句。</d>`。  
- **阿凯**：画外音 (S2)，嘴唇闭合的可见角色不跟嘴型。  
- **配乐**：本集 `non_diegetic_music: N/A`。  
- **合规**：银行 UI 打码；无真实账号。

## 不包含

- API Key / 账号密钥  
- 自动推送到 GitHub（需你另行指示）  
- 音色 wav（`audio_*_timbre.wav` 仍空；锁图 PNG 已在 `refs/`）
