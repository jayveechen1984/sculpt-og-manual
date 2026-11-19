# SCULPT OG 0.19 操作手册

SCULPT OG 是面向 **Polyend Tracker 原版（OG）** 的非官方采样工作站。本手册对应 **SC0019 / 0.19**。F1–F8 指屏幕下方从左到右的八个长键。

## 安装与返回原厂

1. 确认设备是 **原版 Tracker OG**。Tracker+ 和 Tracker Mini 请使用各自适用的固件。
2. 备份 SD 卡上的工程和采样。将 **PolyendTrackerSC0019.ptf** 原名放到 SD 卡的 `/Firmware/`，并保留一个适用于 OG 的原厂固件镜像。
3. 在 Tracker 的 **Config → Firmware Update** 选择 SC0019。安装期间保持电源连接，等待设备重启。
4. 恢复原厂时，在 SCULPT 的 **Config → Firmware** 选回 OG 原厂镜像。 [Polyend Tracker 支持](https://polyend.ladesk.com/567216-Tracker)

## WAV 导入与原始 BPM

支持单声道和双声道 WAV。PCM 支持 8／16／24／32 bit，也支持 32 bit 浮点 WAV。导入会转换为 44.1 kHz。每轨加载上限约 **11.89 秒**，长文件会显示 `FIRST 11.8 s LOADED`。想用长录音后面的片段，可以先在电脑上裁成独立 WAV。

不知道原始 BPM 时，可用 **拍数 × 60 ÷ 时长（秒）**换算。四秒八拍的片段 把 SRC BPM 设为 120。裁剪和 OFFSET 从第二组调整。


## 从采样到效果

1. 按 **Note** 选择 T1–T4，顶部高亮显示当前轨道。
2. 按 **Sample Loader**，用旋钮或上下选择 WAV，**Insert** 导入。浏览器打开时只列文件，**F6** 手动预听，**F7** 返回。
3. 导入有进度提示，可用 **Delete** 取消；完成后在 MATERIAL 确认 SRC BPM。导入时会用文件时长估算原始 BPM。
4. 用四个方向键在 **底部一行八个格子**中选择，用大旋钮改值。设置 SRC BPM、MODE 和工程 BPM，再用 RATE 选播放倍率。短按 Shift 切到第二组，调整循环区域。
5. 按 **Play** 开始播放。
6. 用 **FX1 向左／FX2 向右**切换 **MATERIAL → GRAIN → FILTER → RING → COLOR → SPACE**，按 **Master** 进入混音。增加 GRAIN 的 WET 后进行声音塑形；其余设置页也采用相同的方向键＋旋钮操作。八格分别对齐下方实体八键，屏幕不再显示 F1／F2 等编号。

不需要建立 Instrument、输入音符或写 Pattern。任何页面编辑的都是当前选中的轨道；切页不会重置采样。

## MATERIAL 两组八格

短按并松开 **Shift**，在 `MATERIAL 1/2` 和 `MATERIAL 2/2` 间切换。长按 Shift 或使用 Shift 组合键时，当前组保留。两组都可以按 FX2 直接进入 GRAIN。

| MATERIAL 1/2（从左到右） | 用途 |
|---|---|
| VOLUME | 当前轨音量 |
| MODE | STRETCH 保持音高，SYNC 变速时改变音高，FREE 按采样速度播放 |
| RATE | 选择 1/4、1/2、1、2、4 倍速 |
| DIRECTION | 点按切换正放／倒放，第 4 列 Pad 也可切换 |
| PITCH | STRETCH 下独立移调 |
| SRC BPM | 每轨的采样原始 BPM |
| TEMPO | 工程 BPM，Shift + 旋钮精调 |
| RND FILE | 选中后向右转旋钮，从当前采样的文件夹抽取另一份 WAV。成功后回到 CURRENT，保留轨道上的参数与映射 |

例如，4 秒 8 拍的 Loop 将 SRC BPM 设为 120，工程保持 120 BPM，选 RATE 1/2，Loop 会以原速一半播放，时长变为 8 秒。在 STRETCH 下保留原音高，在 SYNC 下下降一个八度。

## 参数操作

- 按 F1–F8 选择参数，然后转编码器；也可按住对应 F 键转编码器。
- Shift + 转编码器：精调。
- Shift + F 键：所对应参数恢复默认。
- 方向键在可用参数间移动，自动跳过空格。
- Note：下一轨；Shift + Note：上一轨。
- FX1：上一个设置页；FX2：下一个设置页，保留当前轨道。
- 页面键直接进入对应页面，再按一次回到上一屏，保留轨道、参数组和焦点。可从浏览器、调制或 Config 里使用。
- **Pattern／Sample Playback** 打开 MATERIAL，**Instr Params** 打开 GRAIN，**Performance／Master** 打开同一个 PERFORM 页面，**Shift + Master** 打开 SPACE。
- **Song** 打开场景，**File** 打开工程，**Sample Loader** 打开浏览器，**Sample Editor** 打开调制，**Sample Recorder** 打开主混音录音，**Config** 打开设置。**Instr** 打开总览，**Copy** 打开参数层。
- Insert（MATERIAL 页）：打开采样浏览器。

## Pad 固定布局

四行对应四轨。第 1 列和第 6–12 列会选轨，第 2–5 列直接操作对应的轨道。屏幕每个工作站页底部从左到右对应当前轨的 12 个 Pad，亮起的 ENABLE、MUTE、REVERSE、LOCK 代表已开启。顶部轨道框右上角是每轨输出电平，选中轨也会显示。静音或停止的轨道标 MUTE 或 OFF。ENABLE 关闭会停止轨道，再开启按 QUANTIZE 启动。MUTE 静音时保留播放位置。

| 列 | 作用 |
|---|---|
| 1 | 选轨 |
| 2 | 轨道启动／停止；播放中启动按 QUANTIZE，停止即时 |
| 3 | 静音，播放相位继续 |
| 4 | 正反向切换 |
| 5 | 后级颗粒缓冲 LOCK |
| 6–10 | MATERIAL / GRAIN / FILTER / COLOR / SPACE |
| 11 | PERFORM |
| 12 | 为这条轨导入采样 |

## MATERIAL 2/2 · 循环细调

八项从左到右为 START、END、GRID、OFFSET、QUANTIZE、STRETCH、EDGE、ZOOM。GRID 支持 FREE、1/16、1/8、1/4、1/2、1 小节；开启拍格后 START／END 按拍移动，Shift 可精调。裁剪保持 Source BPM。

OFFSET 支持 ±2 秒，移动区域内的读取起点，不改变循环长度和原始 BPM。QUANTIZE 设置下次轨道启动为立即、1 拍、2 拍、1 小节或 2 小节。

ZOOM 为 1×／2×／4×／8×／16×，放大视窗跟随 START。选择 GRID 后区域端点显示拍位置；自由模式显示秒。

STRETCH 策略：ECO 为默认低开销相关匹配，DRUMS 使用短窗和简单瞬态锚定，TEXTURE 使用更密的立体声匹配。DRUMS 适合短打击；持续音优先比较 ECO／TEXTURE。三种策略在 MATERIAL 的 STRETCH 播放模式下生效。

## GRAIN / FILTER / RING / COLOR / SPACE

GRAIN 读取 MATERIAL 的输出，有自己独立的立体声环形缓冲。WET 为零时听到基础采样。颗粒湿声以 22.05 kHz 处理并插值混回，缓冲仍是约 1.49 秒，高频纹理会柔和一些。LOCK 停止写入颗粒缓冲，但前级采样继续同步；解锁后重新接收它的声音。SCAN 是缓冲中的回看位置，不是整个采样文件的绝对位置。

GRAIN 第二键 **MODE** 在 CLASSIC 和 TEXTURE 间切换。TEXTURE 根据 SIZE 和 RATE 自动安排约 2–4 个重叠颗粒，SPRAY 增加平滑漂移和立体声摆动。建议从 **SIZE 140–180 ms、RATE 20 Hz、WET 55%、SPRAY 40%** 试起。底排第 5 列 Pad 仍可 LOCK。

### RING 共振器

从 FILTER 按 **FX2** 进入 RING，或按住 **Shift** 点当前轨第 8 列 **FILTER Pad**。抵达后点最左侧 **RING** 键打开共振，再用八键和旋钮调整。RING 与低通、带通、高通共用滤波位置，打开它会切换到 RING，关闭后回 BYPASS。

| 从左到右 | 用途 |
|---|---|
| Ring | 点按开关 |
| Wet | 共振干湿比 |
| Decay | 共振持续时间与强度 |
| Tune | 根音，显示音名 |
| Bank | METAL 敲击式共振，或 TUNED 音阶共振 |
| Tone | 明暗控制，0 为中性 |
| Spread | 频段间距 |
| Morph | 在频段间移动强调重心 |

在 RING 第一组第五格 **BANK** 选 **METAL** 或 **TUNED**。新工程默认 METAL。METAL 从颗粒前的素材检测起音，用短宽带脉冲激发三条反馈延迟线。三根条显示它们的输出权重。TUNED 仍用八个音高模态。短按 **Shift** 切换到 Cutoff、Slope、Tail、Mix Mode 和 TUNED 的 Scale。SUSTAIN 在主体滤波之后加共振，CHOKE 让截止滤波塑造共振尾音。

**METAL + MIX** 下，Decay 高于 3% 时，Wet 在原声与共振之间交叉混合。Wet 到 100% 可单独听到共振。SEND 把共振叠到原声上。TUNED 在 MIX 中混合滤波主体与音阶余音。Decay 为零时，MIX 可用作滤波器。

想听金属质感，可从 **METAL、Tune C3、Decay 75–85%、Tone +50%、Wet 65%** 开始，试着把 Wet 推到 100% 听尾音。旧工程保留原先保存的 BANK，缺少 BANK 参数时按旧版行为用 TUNED。TUNED 的八根条显示频段权重。

### COLOR 与 DEFORM

第一组为 **Drive、Tilt、Compress、Crush、Redux、Wet、Chorus、Noise**。短按 Shift 访问分频、噪声类型和包络、混合方式与 Chorus 的 Rate 和 Depth。

| DEFORM | 用途 |
|---|---|
| Compress | 双声道联动压缩。加大后降低阈值并提高压缩比 |
| Tilt、Crossover | Tilt 向左强调低频，向右强调高频。选 80 Hz、650 Hz 或 2.5 kHz 可让 Drive 分开处理两段。AUTO 在 Tilt 居中时使用宽频 Drive，有 Tilt 时在 650 Hz 分频 |
| Noise、Noise Type | 随素材包络起伏的噪声，类型为 Pink、White、Dust |
| Noise Decay、Noise Tone | 噪声尾音速度和频谱重心 |
| Mix Mode | MIX 混合干湿。SEND 在干声上叠加湿声，音量会增加 |

Chorus 位于染色后，独立旁通。左右采用不同的延时中心和调制相位，Depth 增加摆幅。可以先在单声道素材上试 Chorus 65%、CH Depth 65%。想先听 DEFORM，可从 **Drive 25%、Tilt +15%、Crossover 650 Hz、Compress 25%、Noise 10%** 开始。

### SPACE

第一组依次是 **DLY SEND、REV SEND、DLY TIME、FEEDBACK、DLY MIX、DLY MODE、REV SIZE、DAMPING**。第 5 格 **DLY MIX** 为当前轨选择 SEND 或 MIX。SEND 保留原声，第 1 格 **DLY SEND** 控制送入延迟的比例。MIX 下第 1 格变成 **DLY WET**，会同时降低这条轨的原声。试听时可先把 DLY WET 推到 **100%**，这条轨只剩延迟回声。REV SEND 仍可独立叠加混响。

第一组第 6 格 **DLY MODE** 选择回声路由。短按 Shift 进入第二组，依次是 **DLY RTN、DLY TONE、REV RTN**。播放停止后，空间尾音继续衰减。

- **WIDE** 保留交叉反馈并把部分回声混入另一侧。**STEREO** 保留发送时的左右声道，各自反馈。**PINGPONG** 将回声依次送到左、右、左。
- **DLY TONE** 负值衰减重复声的高频，正值衰减低频。调节拍值会在新旧延时之间做约 12 ms 的交叉淡化。

Reverb 在左右约 7 ms 和 12 ms 产生早期反射，约 18 ms 后进入扩散。SIZE 拉长后段衰减，DAMPING 调高让尾音变暗。SPACE 的两条返回可分开听，便于判断是回声重复过多还是混响尾音过长。

## WAVE、RANDOM 和调制映射

按 **Sample Editor** 进入，左右切换 LFO1–4、RND1–2，上下跳三个源。底排前六个 Pad 选左相位，后六个选右相位。波形预览使用固定的 −1 到 +1 刻度。降低 Amount，波形会相应缩小。

前七个大键直接选参数，由旋钮调值。**第八键始终是 MAPPING**。短按 Shift 切换参数组。

| 调制源 | 第一组 | 第二组 |
|---|---|---|
| WAVE | Shape、Rate、Sync、Amount、Phase、Offset、Skew | Fold、Curve、Retrig |
| RANDOM | Rate、Sync、Length、Loop、Seed、Amount、Offset | Smooth、Variation、Phase |

- **Shape** 选择波形。**Sync** 选 Free 时可以改 Rate。选 1/16 等拍值后，Rate 显示按工程 BPM 换算的 Hz。例如 120 BPM 下 1/16 显示 8 Hz，WAVE 每拍跑四圈，RANDOM 每拍走四步。S&H 图显示四个保持周期，游标跟随当前值从左向右走，图下列出已映射的轨道和参数。
- **RANDOM** 支持 1–32 步。在 Evolve 下，Variation 控制每圈更新随机序列的概率，Smooth 控制步间滑动。Loop 从 Evolve 改为 Fixed 会用当前 Seed 固定循环。**Insert** 重掷 Seed。
- **第八键 MAPPING** 打开目标列表。左右切轨，上下或旋钮选参数。第七键 **BACK** 退回，第八键 **CONFIRM** 确定。确定后可直接调整映射深度。主界面上按 **FX2** 也可查看已有路由，在列表里用 Delete 删除。
- **从音色页快速映射**：选中目标，按住 Rec，再点第 1–6 列 Pad 选 LFO1–4、RND1–2，然后保持按住 Rec 转旋钮。

## Perform 与宏映射

在音色页选中参数，例如 RATE、DIRECTION 或 Wet，单独按住 **Shift** 约 3 秒。宏窗口的八格显示每个宏的首个目标及映射数，方向键浏览完整列表。点对应大键或按 Insert 确定。新映射会从目标当前值朝有余量的方向改变。例如 Wet 为 100% 时，增加宏值会降低 Wet。重复选择同一个宏会修复完全动不了的旧映射，有可用范围的映射保留原深度。

按 **Performance** 或 **Master** 打开 PERFORM。中间四行显示音量及 LIVE／MUTE／OFF。按 Up 进入音量区，左右选轨后转旋钮。短按 Shift 切换音量与声像，按 Down 回到底部宏区。第 2、3 列 Pad 仍分别控制 Enable、Mute。

八个大键显示宏值与目标。左右选宏后转旋钮，或按住宏键转旋钮。按 Down 进入当前宏的目标列表，旋钮调深度，Delete 移除。点宏键退出目标编辑。**按住 Shift 转旋钮**临时调所选宏或音量，松开 Shift 恢复。

在其他音色页按住 **Delete** 可进入 TEMP，松开后恢复参数值。临时调节期间写入的音频、调制路由和播放相位会继续生效。

## 场景与工程

**Song** 打开 SCENE。Shift + F1–F8 存储场景，F1–F8 立即调用。当前场景包含参数快照，四轨仍共用当前样本。MIDI Program Change 0–7 也可调用。

**File** 打开工程。编码器选 P01–P16；F1 加载，F2 保存。工程保存在 `/Lab/SCULPT/Projects/`，自动会话保存为 `/Lab/SCULPT/autosave.sog`。WAV 不嵌入工程，需保留原路径。缺失样本的轨道会禁用。

File 第三个按钮为 NEW：点一次进入确认，再点一次创建空白会话并停止播放。原始采样和已保存工程保留；新会话需自行保存到项目槽。New 也会取消正在进行的导入，重置场景、调制和 MIDI 学习。

0.19 可读取 version 1–3 工程，新保存的工程仍为 version 3。新增参数和场景设置随工程保存。旧工程保留已有参数。缺少对应参数时，使用 TUNED 共振器、CLASSIC 颗粒、WIDE 延迟以及 SEND 混合模式。

按 **Sample Recorder** 打开录音页，第一个大键开始或停止主混音录音。切回其它页面仍可继续录音。**Shift + Rec** 也可开始或停止，文件保存在 `/Lab/SCULPT/Rec/`。音频叠录和录完自动回灌到轨道尚未实现。

## Ambient 和 Techno Ambient 示例

### Ambient · 漂移中的底色

| 轨道 | 素材 | 起始设置 |
|---|---|---|
| T1 底色 | 4–8 秒的单音 pad、弓弦或吉他泛音 | FREE、RATE 1/2。要保持音高可选 STRETCH / ECO。低通 2–4 kHz，REV SEND 20–30% |
| T2 颗粒 | 2–6 秒的雨声、摩擦声或磁带噪声 | TEXTURE、SIZE 160 ms、RATE 18 Hz、SCAN 30%、SPRAY 35%、WET 60% |
| T3 金属点缀 | 起音清楚、后面留白的杯沿或钥匙敲击 | METAL / MIX / SUSTAIN，Decay 75%、Tone +40%、Wet 55%。Tune 从底色的主音开始找 |

在 T2 加一个 **Sine / Free / 0.03 Hz** 的 LFO，浅映射到 SCAN。找到有趣的纹理后，点第 5 列 Pad 锁住颗粒缓冲，再转 SCAN。共享 Reverb 从 **SIZE 75%、DAMPING 55%** 起步，用各轨的 REV SEND 拉开远近。

### Techno Ambient · 稳定低鼓与错拍纹理

1. 工程从 **122 BPM** 起步。加一条短 kick Loop，用 SYNC 并确认 SRC BPM。两种空间 Send 先设为 0。
2. 颗粒轨换成沙锤或机械声，选 **CLASSIC、SIZE 80–110 ms、RATE 12–16 Hz、WET 30–45%**。
3. 把 **RND1** 浅映射到 SCAN，设置 **Sync 1/8、Length 7、Loop Fixed、Smooth 15–25%**。七个八分步每 3.5 拍重复一次，会相对四拍小节移动。
4. 给金属轨少量送入 **PINGPONG**，试 **1/8.、FEEDBACK 25–35%、DLY TONE −20%**。把 T2 的 GRAIN Wet 和 REV SEND 绑到同一宏，可以在 Perform 按住 Shift 转宏，松开后回到原值。

## CPU 与常见问题

- 右上角 **CPU** 显示最近约半秒内最慢音频块占用的预算。超过 100% 表示有块来不及完成。四轨负载随采样、模式和调制变化。90% 是 SC0019 的实机验收目标。
- 听到爆音时，先试旁通次要轨的 **RING**，再把次要轨的 **GRAIN Wet** 归零。允许音高随速度变化的轨可用 SYNC 节省拉伸开销。归零时检查宏或 LFO 是否还在推高参数。
- SPACE 使用两条共享总线。想停掉一条总线的处理，将四轨相应的 Send 归零并等尾音结束。
- 工程引用 SD 卡上的 WAV 路径。移动文件后，重新导入缺失轨的素材。回到 0.3 及更早固件时请用对应的旧工程副本。
- 导入可用 **Delete** 取消。遇到异常时，记录固件编号、启用轨数、素材规格和复现按键。诊断日志可能包含你的文件名。

## 致谢与来源

- **BULUT / polyend-tracker-lab** 是直接代码基础。SCULPT 在上游的 `firmwares/bulut/` 快照上开发，本地项目记录的基线提交为 `f14223960bbb7b9580534663a5b7c6110ee6ff7b`。复用 LABKIT 的参数、浏览器、调制、状态保存和模拟器框架。 [上游项目](https://github.com/semierendonmez-commits/polyend-tracker-lab)
- **OpenTracker / sandlbn 及贡献者** 提供 Tracker OG 的底层实现。SCULPT 经 BULUT 继承硬件适配、SD、显示、按键、音频 I/O 和 WAV 支持。 [OpenTracker](https://github.com/sandlbn/polyend-tracker-re)
- **Retrack / math0ne** 提供同一硬件上的四轨 Looper 与长素材 SD 流式读取的架构参考。SCULPT 0.19 的 RAM 循环播放为本项目实现。 [Retrack](https://github.com/math0ne/retrack-tracker)
- **Torso Electronics S-4** 提供采样优先流程和效果分段的交互灵感，包括导入、同步、拉伸，颗粒、共振、空间处理，以及调制、宏和场景。SCULPT 的操作适配了 Tracker 的单旋钮、屏幕键和 Pad。 [S-4 官方用户指南](https://docs.torsoelectronics.com/s4/introduction/)
- **Émilie Gillet 与 Mutable Instruments** 的 Clouds、Beads 和 stmlib 属于 BULUT 的上游 DSP 依赖。BULUT 也记录了 artifex 和 rete 等 GPL 派生成果。相关代码沿用其各自的许可证和署名。 [BULUT 上游](https://github.com/semierendonmez-commits/polyend-tracker-lab) · [Mutable Instruments eurorack](https://github.com/pichenettes/eurorack)

SCULPT OG 是独立的社区项目。Polyend Tracker 与 Torso S-4 的名称用于说明兼容设备和设计出处。
