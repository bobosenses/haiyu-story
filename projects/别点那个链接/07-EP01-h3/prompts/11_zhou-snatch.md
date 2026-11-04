# 块 11 · 周妍夺机

- 时间轴：55–60s
- 镜号：12
- 请求时长：约 5 秒（24fps ≈ 120 帧量级）
- 说话人：(S1)林夏 (S2)阿凯 (S3)周妍
- 音频 retention：全部 `reference`（只借音色）
- 挂载参考：Subject1, Subject2, Subject3, Audio3

## 可粘贴正文（六段式 · 英文）

```text
subject_definitions:
<Subject 1> is the 25-year-old East Asian intern Lin Xia whose appearance comes from refs/linxia_lock.png: slightly messy ponytail, cheap grey blazer over lounge pants, pale face under desk-lamp side light, habitually twisting a thin silver ring on her left hand.
<Subject 2> is the 26-year-old East Asian roommate Zhou Yan whose appearance comes from refs/zhouyan_lock.png: wet hair stuck to her face, old T-shirt with a light outer layer, a charging cable wrapped around her fingers, alert and sharp expression.
<Subject 3> is the fictional vertical phone UI mock from refs/phone_ui_mock.png used as a physical phone prop with a pending masked transfer page.
<Audio 3> is the voice-timbre reference for <Subject 2> (S3).

summary:
[reference generation + audio reference] <Subject 2> shoulder-opens the door, wet hair and charger cable, snatches the phone and asks who pulled <Subject 1> into the group.

retention_analysis:
<Subject 1> (appears in [Shot 1]): fully_preserved.
<Subject 2> (appears in [Shot 1]): fully_preserved - wet hair, old T, charger cable on fingers.
<Subject 3> (appears in [Shot 1]): fully_preserved - phone as prop.
<Audio 3>: reference - vocal timbre and measured delivery guide <Subject 2> (S3); do not copy the original signal or original lines.

detailed_description:
The target video is a vertical 9:16 Chinese short-drama clip with cold phone screen light as the key source, cramped night shared-bedroom realism, tight oppressive pacing, and no decorative film grade.
[Shot 1] Medium shot: the door bursts open under a shoulder. <Subject 2> enters with wet hair stuck to her face, old T-shirt, charging cable wrapped around fingers, and snatches <Subject 3> from <Subject 1>. <Subject 2> (S3), lower clear urgent timbre referenced from <Audio 3>, says, <d>[Chinese] 谁拉你进这种群的？</d> Camera tracks the snatch.

overall_soundscape:
Quiet night shared-bedroom room tone, faint fridge hum, and close phone UI taps continue; no crowd bed.

non_diegetic_music:
N/A
```
