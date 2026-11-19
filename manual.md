# SCULPT OG 0.19 User Manual

SCULPT OG is an unofficial four-track sampling workstation for the **original Polyend Tracker (OG)**. This manual covers firmware **SC0019 / 0.19**. F1–F8 refer to the eight long buttons below the display, from left to right.

## Install and return to stock

[Download firmware bundle (ZIP)](https://github.com/jayveechen1984/sculpt-og-manual/releases/download/v0.19.0/SCULPT-OG-SC0019.zip) · [Download the .ptf](https://github.com/jayveechen1984/sculpt-og-manual/releases/download/v0.19.0/PolyendTrackerSC0019.ptf) · [Release notes](https://github.com/jayveechen1984/sculpt-og-manual/releases/tag/v0.19.0)

1. Confirm that your device is the **original Tracker OG**. Tracker+ and Tracker Mini require firmware built for their own hardware.
2. Back up the SD card. Copy **PolyendTrackerSC0019.ptf** to the card's `/Firmware/` directory with its original filename. Keep a stock OG firmware image on the card as well.
3. On the Tracker, open **Config → Firmware Update** and select SC0019. Keep the Tracker powered until it restarts.
4. To return to stock, open **Config → Firmware** in SCULPT and select the stock OG image. [Polyend Tracker support](https://polyend.ladesk.com/567216-Tracker)

## Load a WAV and start shaping

1. Press **Note** to select T1–T4. The selected track is highlighted at the top of the display.
2. Press **Sample Loader**. Use the encoder or Up and Down to find a WAV. Press **F6** to preview, **Insert** to import, or **F7** to go back. **Delete** cancels an import in progress.
3. In **MATERIAL**, check **SRC BPM** and choose **MODE**. Import estimates the source tempo from duration. If you know the beat count, calculate source BPM as **beats × 60 ÷ seconds**. An eight-beat, four-second loop has a source tempo of 120 BPM.
4. Press **Play**. Use **FX1** and **FX2** to move backward and forward through **MATERIAL → GRAIN → FILTER → RING → COLOR → SPACE**. Raise **GRAIN Wet** to bring in the granular layer.
5. Press **Performance** or **Master** to mix tracks and play the eight macros. You can start with an empty session and go directly from importing WAVs to playback.

Both mono and stereo WAVs are supported. The decoder accepts 8-, 16-, 24-, and 32-bit PCM and 32-bit floating-point WAVs, and converts audio to 44.1 kHz. Each track loads up to 524,288 stereo frames, about **11.89 seconds**. Longer files display `FIRST 11.8 s LOADED`. To use a later passage, trim a copy to that passage before importing.

## Panel shortcuts

| Control | Action |
|---|---|
| F1–F8, arrow keys | Select one of the eight on-screen controls. Turn the encoder to edit it. You can also hold its F key while turning. |
| Shift + encoder | Fine adjustment on sound pages. On PERFORM, it temporarily changes the selected control. |
| Shift + F key | Reset the corresponding parameter on sound pages. |
| Tap Shift | Switch parameter banks on pages with a second bank. |
| Note / Shift + Note | Select the next / previous track. |
| FX1 / FX2 | Select the previous / next sound page. |
| Pattern / Sample Playback | Open MATERIAL. **Insert** on MATERIAL also opens the sample browser. |
| Instr Params | Open GRAIN. |
| Performance / Master | Open PERFORM. **Shift + Master** opens SPACE. |
| Song / File | Open SCENE / project management. |
| Sample Loader / Sample Editor | Open the sample browser / modulation. |
| Sample Recorder / Config | Open the main-mix recorder / settings. |
| Instr / Copy | Open the parameter overview / parameter layer. |

Press a page key again to return to the previous view. SCULPT restores the prior track, parameter bank, and focus.

### Pad grid

The four rows correspond to the four tracks. Column 1 and columns 6–12 select the corresponding track. Columns 2–5 act on the track under the pad while keeping the current selection.

| Column | Action |
|---|---|
| 1 | Select track. |
| 2 | Enable or stop the track. Starts while playing follow QUANTIZE. Stops are immediate. |
| 3 | Mute or unmute. Playback position continues while muted. |
| 4 | Toggle forward or reverse playback. |
| 5 | Lock or unlock the granular buffer. |
| 6–10 | Jump to MATERIAL, GRAIN, FILTER, COLOR, or SPACE. **Shift + FILTER pad** opens RING. |
| 11 | Open PERFORM. |
| 12 | Open the sample browser for that track. |

The track cards show output level for all tracks, including the selected track. MUTE and OFF indicate muted and disabled tracks. The sound pages also show the selected row's pad functions and toggle states.

## MATERIAL

Tap **Shift** to switch between the two banks.

### Bank 1 · Playback

| Control | What it does |
|---|---|
| VOLUME | Adjusts the selected track's output level. |
| MODE | **STRETCH** syncs to the project and preserves pitch. **SYNC** follows project tempo with pitch changing as playback speed changes. **FREE** plays at the chosen rate independently of project tempo. |
| RATE | Selects 1/4×, 1/2×, 1×, 2×, or 4×. |
| DIRECTION | Toggles FWD and REV. Pad column 4 does the same. |
| PITCH | Transposes the sample independently in STRETCH mode. |
| SRC BPM | Sets the original tempo of the current sample. |
| TEMPO | Sets project BPM. Hold Shift while turning for fine adjustment. |
| RND FILE | Turn clockwise to load a different WAV from the current sample's folder. The control returns to CURRENT after the change and keeps track settings and mappings. |

With a four-second, eight-beat loop at SRC BPM 120 and project tempo 120, RATE 1/2 plays the loop over eight seconds. STRETCH keeps its pitch. SYNC drops it an octave.

### Bank 2 · Loop editing

The controls are **START, END, GRID, OFFSET, QUANTIZE, STRETCH, EDGE, ZOOM** from left to right.

- **START / END** trim the playback region while retaining SRC BPM. GRID offers FREE, 1/16, 1/8, 1/4, 1/2, or one bar. With a beat grid selected, the endpoints move in beat increments. Hold Shift for fine adjustment.
- **OFFSET** moves the read start within the region by up to ±2 seconds. The loop length and SRC BPM stay the same.
- **QUANTIZE** schedules the next track start immediately or on a boundary of one beat, two beats, one bar, or two bars.
- **STRETCH** selects the algorithm when MODE is STRETCH. **ECO** uses a lightweight correlation search. **DRUMS** uses short windows and transient anchoring. **TEXTURE** searches a denser set of stereo samples. Try DRUMS on percussion and compare ECO with TEXTURE on sustained sounds.
- **EDGE** sets the fades at the region edges.
- **ZOOM** offers 1×, 2×, 4×, 8×, and 16× and follows START. Region positions are shown in beats with a grid and in seconds in FREE grid mode.

## Sound shaping

### GRAIN and FILTER

GRAIN reads the MATERIAL output into a stereo history buffer of about **1.49 seconds**. **SCAN** sets how far back to read in that history. **LOCK** freezes writes to the history while MATERIAL keeps following the clock. Set WET to zero to hear the base sample. The grain signal is processed at 22.05 kHz and interpolated back into the 44.1 kHz mix.

The controls are **WET, MODE, SIZE, SCAN, PITCH, RATE, SPRAY, SHAPE**. **CLASSIC** gives direct control over grain size and launch rate. **TEXTURE** uses SIZE and RATE to aim for roughly two to four overlapping grains. SPRAY adds drift and stereo movement. Try TEXTURE with **SIZE 160 ms, RATE 18 Hz, WET 55%, SPRAY 35%**.

FILTER offers low-pass, band-pass, and high-pass filtering. FILTER and RING share a processing slot.

### RING

From FILTER, press **FX2**, or hold **Shift** and tap the current track's FILTER pad in column 8. Press the leftmost **RING** button to toggle the resonator. Turning RING on selects it in the shared filter slot. Turning it off returns the slot to BYPASS.

| Control | Action |
|---|---|
| RING | Enable or bypass the resonator. |
| WET | Set the amount of resonator output. |
| DECAY | Adjust the strength and duration of the tail. |
| TUNE | Set the root note. |
| BANK | Choose METAL or TUNED. New projects default to METAL. |
| TONE | Adjust brightness. Zero is neutral. |
| SPREAD | Change the spacing of the feedback lines or tuned modes. |
| MORPH | Move the emphasis across the lines or modes. |

**METAL** detects attacks before GRAIN and excites three short, differently tuned feedback delay lines. **TUNED** uses eight pitched modes. The graph shows their relative weights. Tap **Shift** for **Cutoff, Slope, Tail, Mix Mode**, and the **Scale** setting for TUNED.

**SUSTAIN** adds the resonant tail after the main filter. **CHOKE** lets the cutoff shape the tail. **SEND** adds resonator output to the dry track. In **METAL / MIX**, with Decay above about 3%, Wet crossfades the dry and resonant signals. At Wet 100% you can audition the resonator on its own. In **TUNED / MIX**, Wet blends the dry signal with the filtered body and pitched tail.

For a metallic accent, try **METAL, Tune C3, Decay 75–85%, Tone +50%, Wet 65%**. Turn Wet up briefly to hear the tail by itself, then blend it back. Saved projects keep their saved BANK. Projects from before BANK was added use TUNED.

### COLOR and DEFORM

The first bank offers **Drive, Tilt, Compress, Crush, Redux, Wet, Chorus, Noise**. Tap **Shift** for crossover, noise type, noise decay, noise tone, Mix Mode, Chorus Rate, and Chorus Depth.

- **Tilt** changes the balance of lows and highs. The crossover can split Drive at 80 Hz, 650 Hz, or 2.5 kHz. AUTO uses full-band Drive when Tilt is centered, and splits at 650 Hz when Tilt is active.
- **Compress** uses stereo-linked gain reduction. Raising it lowers the threshold and increases the ratio.
- **Noise** follows the input envelope. Select Pink, White, or Dust and shape it with Noise Decay and Noise Tone.
- **MIX** blends dry and wet. **SEND** adds the processed signal to the dry sound and can increase the level.
- **Chorus** sits after the color stage and has its own bypass at zero. It uses different delay centers and phases on the two sides. Try Chorus 65% and Depth 65% on a mono source to hear the effect clearly.

A starting point for audible DEFORM is **Drive 25%, Tilt +15%, Crossover 650 Hz, Compress 25%, Noise 10%**.

### SPACE

Delay and Reverb each run on a shared bus. The first bank offers **DLY SEND, REV SEND, DLY TIME, FEEDBACK, DLY MIX, DLY MODE, REV SIZE, DAMPING**.

Each track sets its own delay and reverb sends. **DLY MIX → SEND** keeps the track's dry contribution and adds the delay return. In **MIX**, the first control reads **DLY WET** and raising it also reduces that track's dry contribution. At 100% you can audition the delay alone. Reverb send is independent.

- **WIDE** uses cross-feedback and blends some echo across sides.
- **STEREO** keeps left and right sends separated and feeds each side back into itself.
- **PINGPONG** alternates echoes from left to right.
- Tap **Shift** for **DLY RTN, DLY TONE, REV RTN**. Negative DLY TONE darkens repeats. Positive values reduce their low end. Delay time changes crossfade over about 12 ms.
- Reverb SIZE extends the late decay. DAMPING darkens the tail. Both buses can finish their tails after playback stops.

## LFO and random modulation

Press **Sample Editor**. Left and Right switch between LFO1–4 and RND1–2. Up and Down jump by three sources. The first six pads in the bottom row select the left phase, and the last six select the right phase. The graph uses a fixed −1 to +1 scale. Its cursor follows the current output, and the target list below identifies the mapped tracks and parameters.

| Source | Bank 1 | Bank 2 |
|---|---|---|
| WAVE | Shape, Rate, Sync, Amount, Phase, Offset, Skew | Fold, Curve, Retrig |
| RANDOM | Rate, Sync, Length, Loop, Seed, Amount, Offset | Smooth, Variation, Phase |

Tap **Shift** to switch banks. The eighth button is always **MAPPING**.

- **WAVE** supports Sine, Triangle, Saw, Square, Sample & Hold, and Smooth Random. With Sync set to Free, Rate sets frequency in Hz. With a beat division selected, Rate displays the tempo-derived frequency. At 120 BPM, 1/16 is 8 Hz. WAVE completes four cycles per beat, and RANDOM advances four steps per beat. The S&H graph shows four successive holds.
- **RANDOM** supports 1–32 steps. **Fixed** repeats a sequence from its Seed. **Evolve** uses Variation as the probability of changing the sequence at each loop. Smooth controls the glide between steps. Switching from Evolve to Fixed keeps the current seed. **Insert** rolls a new seed.
- To map a source, press **MAPPING**. Left and Right select a track. Up, Down, or the encoder select a parameter. Press **F8 / CONFIRM** to map it, then turn the encoder to set depth. **F7 / BACK** returns. **FX2** on the modulation page opens the route list, where **Delete** removes a route.
- To map from a sound page, select a target, hold **Rec**, and tap a pad in columns 1–6 to select LFO1–4 or RND1–2. Keep holding Rec while turning the encoder to set depth.

## PERFORM and macros

Select a modulatable parameter on a sound page and hold **Shift** by itself for about three seconds. The picker shows each macro's first target and mapping count. Use the arrows to inspect all its routes. Press the appropriate F key or **Insert** to confirm. A new route moves the target in the direction with available range. If Wet starts at 100%, turning the macro up will lower Wet. Assigning the same target again can repair an old route with zero usable range.

Open PERFORM with **Performance** or **Master**.

- The track rows show volume and **LIVE / MUTE / OFF**. Press **Up** to reach those rows, choose a track with Left and Right, and turn the encoder. Tap **Shift** to switch volume and pan. Press **Down** to return to the macros.
- The eight keys show macro values and targets. Select a macro with Left and Right or hold its F key, then turn the encoder. Press **Down** to inspect its routes, turn to adjust depth, or press **Delete** to remove the selected route. Press a macro key to return to the macro value.
- Hold **Shift** while turning to temporarily adjust the selected macro or level. Release Shift to restore the previous value. On other sound pages, hold **Delete** for TEMP. Transport phase, audio written to buffers, and routing changes can continue during temporary adjustments.

## Scenes, projects, and recording

- **Song** opens SCENE. Hold **Shift** and press **F1–F8** to store a scene. Tap the same F key to recall it. MIDI Program Change 0–7 also recalls scenes. Scenes store parameters and reuse the current sample on each track.
- **File** opens project slots **P01–P16**. Choose a slot with the encoder, then press **F1** to load or **F2** to save. Projects live in `/Lab/SCULPT/Projects/`. The last session autosaves to `/Lab/SCULPT/autosave.sog`. Projects reference WAV paths, so keep the original files in place. Tracks with missing files are disabled.
- In **File**, press **NEW** twice to stop playback and start an empty session. This cancels imports and clears current scenes, modulation, and MIDI learn. Existing WAVs and saved project slots stay on the card.
- SC0019 reads project versions 1–3 and saves version 3. Missing settings in older projects default to TUNED, CLASSIC, WIDE, and SEND as applicable. When rolling back to firmware 0.3 or earlier, use a compatible project backup.
- **Sample Recorder** opens the main-mix recorder. Its first key starts or stops recording. **Shift + Rec** also toggles recording, which can continue while you visit other pages. Recordings are saved in `/Lab/SCULPT/Rec/`. This version records the main mix. Track overdubbing and automatic resampling into a track are planned separately.

## Example patches

### Ambient · slowly moving layers

| Track | Material | Starting point |
|---|---|---|
| T1 · pitched bed | Four to eight seconds of a single-note pad, bowed string, or guitar harmonic | FREE and RATE 1/2. Use STRETCH / ECO to preserve pitch. Try a 2–4 kHz low-pass and REV SEND 20–30%. |
| T2 · grain layer | Two to six seconds of rain, fabric, or tape noise | TEXTURE, SIZE 160 ms, RATE 18 Hz, SCAN 30%, SPRAY 35%, WET 60%. |
| T3 · metal accents | A short hit on a cup or keys with silence after the attack | METAL / MIX / SUSTAIN, Decay 75%, Tone +40%, Wet 55%. Start with TUNE on the root note of T1. |

Map a shallow **Sine / Free / 0.03 Hz** LFO to T2 SCAN. When a passage catches your ear, lock the grain buffer with pad column 5 and turn SCAN. Start the shared Reverb at **SIZE 75% and DAMPING 55%**. Use each track's REV SEND to place it closer or farther away.

### Techno ambient · steady kick and shifting texture

1. Start at **122 BPM**. Load a short kick loop, choose SYNC, and confirm SRC BPM. Start with both sends at zero on the kick.
2. Load a shaker or mechanical loop on the grain track. Use **CLASSIC, SIZE 80–110 ms, RATE 12–16 Hz, WET 30–45%**.
3. Map **RND1** lightly to SCAN. Choose **Sync 1/8, Length 7, Loop Fixed, Smooth 15–25%**. The seven eighth-note steps repeat every 3.5 beats, so their accents shift against a four-beat bar.
4. Send some of the metal track to **PINGPONG**. Try **dotted 1/8, Feedback 25–35%, DLY TONE −20%**. Map T2 GRAIN Wet and REV SEND to the same macro, then use **Shift + encoder** in PERFORM for a temporary wash.

## CPU and troubleshooting

- The top-right **CPU** meter reports the slowest audio block in roughly the last half second as a percentage of the block's time budget. Over 100% means an audio deadline was missed. Load varies with the project, modes, and effects. Below 90% is a four-track test target for SC0019.
- If you hear dropouts, try bypassing RING or setting GRAIN Wet to zero on a supporting track. Where pitch can follow speed, SYNC can reduce the cost of stretching. Check whether a macro or LFO is raising an effect amount after you set it to zero.
- To idle a shared SPACE processor, set that send to zero on all tracks and let the tail decay.
- For import trouble, try a mono or stereo WAV within the supported formats and use Delete to cancel a stalled import. To report a reproducible problem, include the firmware version, track count, audio format, and button sequence. Diagnostic logs can contain sample filenames.

## Credits and sources

- **BULUT / polyend-tracker-lab** is the direct code base. SCULPT was developed from its `firmwares/bulut/` snapshot. The locally recorded baseline is commit `f14223960bbb7b9580534663a5b7c6110ee6ff7b`. SCULPT reuses the LABKIT parameter system, browser, modulation, project infrastructure, and simulator framework. [BULUT upstream](https://github.com/semierendonmez-commits/polyend-tracker-lab)
- **OpenTracker / sandlbn and contributors** provide the original Tracker hardware foundation. Through BULUT, SCULPT inherits hardware adaptation, SD support, display and panel controls, audio I/O, and WAV support. [OpenTracker](https://github.com/sandlbn/polyend-tracker-re)
- **Retrack / math0ne** served as an architectural reference for a four-track looper and SD streaming on the same hardware. SCULPT implements its own RAM-based loop player. [Retrack](https://github.com/math0ne/retrack-tracker)
- **Torso Electronics S-4** inspired the sample-first workflow, the sequence of sound-shaping stages, and the organization of modulation, macros, and scenes. SCULPT adapts these ideas to the Tracker encoder, screen buttons, and pad grid. [Official S-4 user guide](https://docs.torsoelectronics.com/s4/introduction/)
- **Émilie Gillet and Mutable Instruments** contributed Clouds, Beads, and stmlib to the wider BULUT dependency chain. BULUT also documents GPL-derived work including artifex and rete. Each upstream component retains its original license and attribution. [BULUT upstream](https://github.com/semierendonmez-commits/polyend-tracker-lab) · [Mutable Instruments eurorack](https://github.com/pichenettes/eurorack)

SCULPT OG is an independent community project. Polyend Tracker and Torso S-4 identify the supported hardware and design reference.
