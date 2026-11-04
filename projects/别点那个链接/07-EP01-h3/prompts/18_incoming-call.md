# 块 18 · 人事来电 + 别接

- 时间轴：95–102s
- 镜号：19–20
- 请求时长：约 7 秒（24fps ≈ 168 帧量级）
- 说话人：(S1)林夏 (S2)阿凯 (S3)周妍
- 音频 retention：全部 `reference`（只借音色）
- 挂载参考：Subject1, Subject2, Subject3, Subject4, Audio2

## 可粘贴正文（六段式 · 英文）

```text
subject_definitions:
<Subject 1> is the 25-year-old East Asian intern Lin Xia whose appearance comes from refs/linxia_lock.png.
<Subject 2> is the 26-year-old East Asian roommate Zhou Yan whose appearance comes from refs/zhouyan_lock.png.
<Subject 3> is the fictional vertical phone UI mock from refs/phone_ui_mock.png with HR call banner and masked pending confirm; no real phone numbers.
<Subject 4> is the scam-mentor chat avatar from refs/akai_avatar.png.
<Audio 2> is the voice-timbre reference for the off-screen scam mentor voice (S2) associated with <Subject 4>'s avatar.

summary:
[reference generation + audio reference] Dual crisis: an urgent HR call banner slides in while (S2) orders her not to answer.

retention_analysis:
<Subject 1> (appears in [Shot 1], [Shot 2]): fully_preserved.
<Subject 2> (appears in [Shot 1], [Shot 2]): fully_preserved.
<Subject 3> (appears in [Shot 1], [Shot 2]): fully_preserved - call banner 公司人事·紧急; confirm still flashing under; no real numbers.
<Subject 4> (appears in [Shot 2]): fully_preserved - avatar bubble.
<Audio 2>: reference - vocal timbre and urgent delivery guide off-screen (S2); do not copy the original signal or original lines.

detailed_description:
The target video is a vertical 9:16 Chinese short-drama clip with cold phone screen light as the key source, cramped night shared-bedroom realism, tight oppressive pacing, and no decorative film grade.
[Shot 1] Extreme close-up of <Subject 3>: a system incoming-call banner slides from the top with visible Chinese label 公司人事·紧急, vibration light pulsing. Underneath, the masked 确认转账 key still blinks. Soft cut to both <Subject 1> and <Subject 2> turning their eyes to the banner together.
[Shot 2] At 00:03.000, near phone close-up: <Subject 4>'s chat bubble almost overlays the call banner. Both women keep lips closed. Off-screen (S2), urgent timbre from <Audio 2>, says, <d>[Chinese] 公司人事打你了？别接。接了今晚名额作废。他们在卡你的窗口。</d> Micro shake matching vibration.

overall_soundscape:
Phone vibration motor and incoming-call ringtone pulses over tight night room tone; UI taps minimal.

non_diegetic_music:
N/A
```
