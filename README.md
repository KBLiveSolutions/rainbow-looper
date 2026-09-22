# Rainbow Looper

An 8-track quantized multi-looper for [Ableton Move](https://rnbo.cycling74.com/learn/move-intro-and-setup), built with [RNBO](https://rnbo.cycling74.com/). Each of the 8 tracks is its own looper with per-step muting, a built-in sample player, and a set of performance effects.

![RainbowLooper](https://github.com/KBLiveSolutions/rainbow-looper/blob/main/misc/images/IMG_5573.webp)

## Installation

This project includes an exported RNBO graph at [`misc/graphs/rainbow-looper-rnbo-1.4.3.rnbopack`](./misc/graphs/rainbow-looper-rnbo-1.4.3.rnbopack). From the RNBO Graph Editor at `move.local:3000/`, you can import this `.rnbopack` directly and start looping right away.

## How it works

### The 8 loopers

Each looper is controlled by a column of 4 pads (bottom to top):

- **Red** — Rec
- **Green** — Play
- **White** — Stop
- **Rainbow color** — Select (also opens the looper's parameter page)

The first looper sets the base loop length. Every other looper is quantized to it: recording can start freely at any time, but playback always launches on a multiple of the first looper's length, so all 8 loopers stay in sync.

### Step sequencing

Each looper has its own step pattern, controlled with Move's step buttons. Turning a step off mutes the looper's output at that point in the loop — the volume envelope for muting is shaped by the **Attack** and **Release** parameters.

- **+ / -** — multiply the step speed
- **< / >** — create/cycle through patterns
- **Undo** — retriggers the loop on every active step (when the previous step is off)

### Parameters

Parameters are organized in two pages, switched with the encoder or by pressing the looper's **Select** pad again.

**Page 1**
- Volume
- Pan
- Attack
- Release
- Filter Freq (DJ filter)
- Resonance
- Filter Env (follows the step pattern and the Attack/Release envelope)
- Sample Start

**Page 2**
- Delay Time
- Delay Feedback (`0` = delay off)
- Autopan Amount
- Autopan Freq
- Downsample (bitcrusher)
- Looper State (exposed for external mapping)
- *(unused)*
- Sample Selector

### Sample player

Pressing **Capture** switches a looper into sample-player mode: instead of playing back its recorded loop, it plays one of 12 built-in samples (chosen with the **Sample Selector** parameter), triggered by the looper's step pattern.

### Other controls

- **Loop** — reverses the looper's audio (loop or sample)
- **M** — mutes the looper
- **X** — clears the looper
- **Main Rec** - toggles monitoring On
- **Sample Rec** - looper state (same behavior as Live's Looper big button)

## Requirements

This project targets the [RNBO Runner](https://rnbo.cycling74.com/learn/raspberry-pi-target-overview) on Ableton Move.

## License

See [LICENSE.md](./LICENSE.md) (MIT).
