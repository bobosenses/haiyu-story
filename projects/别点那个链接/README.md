# 《别点那个链接》· script-only 工作流包

按仓库 [`workflows/script-only.md`](https://github.com/bobosenses/haiyu-story/blob/main/workflows/script-only.md) **依序**完成；并映射 short-drama 技能顺序：

`/start` → `/plan` → `/characters` → `/outline` → `/episode` → `/review` → `/compliance`

单集按 90–120 秒表演口径。EP01 的镜头表与 H3 Ref2VA 提示词在 [`07-EP01-h3/`](./07-EP01-h3/)；参考图和音色样片没有附二进制。

## 已完成步骤

| 顺序 | 工作流 | short-drama | 产出 |
|---:|---|---|---|
| 1 | 选题 | `/start` | `00-选题.md` |
| 2 | 系列设定 | `/plan` | `01-series-bible.md` |
| 2b | 角色卡 | `/characters` | `02-characters/` |
| 3 | 多集大纲 | `/outline` | `03-outline.md` |
| 4.1 | 场次节拍 | `/episode`（先节拍） | `04-EP01-beats/` |
| 4.2 | 单集成稿 | `/episode` | `05-EP01-script.md` |
| 5–6 | 自检+合规 | `/review` `/compliance` | `06-review-compliance.md` |

## 文件地图

```
haiyu-story-anti-fraud/
├── README.md
├── 00-选题.md
├── 01-series-bible.md
├── 02-characters/
│   ├── 林夏.md
│   ├── 周妍.md
│   ├── 阿凯.md
│   └── 假人事-小陈.md
├── 03-outline.md
├── 04-EP01-beats/
│   ├── 场次01-倒计时逼仓.md
│   ├── 场次02-证据拆穿.md
│   └── 场次03-双线来电.md
├── 05-EP01-script.md
├── 06-review-compliance.md
└── 07-EP01-h3/
    ├── README.md
    ├── 镜头表.md
    ├── 素材槽位.md
    ├── prompts/          # 19 条 Ref2VA 提示词
    └── refs/README.md    # 占位说明，无图片/音频
```

## EP01 一句话

实习生林夏被虚假投资群倒计时逼到 9800 元确认键上，室友周妍夺机用「禁截图 / 私人转账 / 极限催促」三条屏幕证据拆穿；阿凯封死对外求证的同一秒，「公司人事·紧急」来电打入，骗子喝令「别接」——接或不接，悬在下一集。

## 下一步（未做）

1. 按 [`07-EP01-h3/素材槽位.md`](./07-EP01-h3/素材槽位.md) 自行准备锁图和音色样片后再提交生成。本目录不附参考图、音频，也不写 H3 API 密钥或安装命令。  
2. 改 EP01 对白时，同步改 `07-EP01-h3/prompts/` 里对应的 `<d>[Chinese]…</d>`。  
3. 可按大纲继续 EP02 节拍→成稿。
