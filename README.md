# Ondinha Resonance

**Dynamic resonance tamer for harsh mixes, vocals and guitars: pulls down narrow peaks only while they ring and leaves the broad tone alone.**

A VST3 and Audio Unit plug-in from [Ondinha](https://github.com/ondinha), a DAW 2.0: native AI tools combined with traditional sound engineering tools.

Finds the narrow, ringing peaks that make a mix sound harsh, boxy or fizzy and pulls them down, only while they ring. The broad tone you dialled in stays where it is.

Use **Delta** to hear exactly what's being taken out.

## What it's good for

- Master: a few dB of gentle harshness control.
- Guitars: fizz and honk between 1.5 and 9 kHz.
- Vocals: harsh S sounds and ringing, without a separate de-esser.
- Low-mid boom in rooms, toms or acoustic guitar.

## Controls

| Control | Range | What it does |
|---|---|---|
| Depth | 0-12 dB | Maximum reduction. |
| Threshold | 0-12 dB | How far a peak must stick out before it's touched. |
| Smoothing | 0.1-1 oct | What counts as 'the tone' vs a peak. |
| Focus low / high | 20 Hz - 20 kHz | Only this range is touched. |
| Attack / Release | 0.5-50 ms / 10-500 ms |  |
| Mix | 0-100 % |  |
| Delta | Off / On | Plays only what is removed. |

## Presets

Built in as host programs (your DAW's preset menu):

- Master: gentle harshness
- Guitars: fizz and honk
- Vocal: harsh S and ring
- Low-mid boom

## Download and install

Builds will be on the [Releases](../../releases) page.

**macOS:** copy `Ondinha Resonance.vst3` to `~/Library/Audio/Plug-Ins/VST3` and `Ondinha Resonance.component` to `~/Library/Audio/Plug-Ins/Components`, then rescan plug-ins in your DAW.

| Format | Platform |
|---|---|
| VST3 | macOS |
| Audio Unit (AU) | macOS |

Works in any VST3 or AU host: Ableton Live, Logic Pro, Reaper, Bitwig Studio, Cubase, Studio One, FL Studio and others.

## How it works

Every STFT frame (2048 samples at 44.1 / 48 kHz, 75 % overlap), the spectrum is compared with its own smoothed shape. A bin that sticks out more than the threshold is pulled down by what sticks out, at most the depth, with its own attack and release. Both channels get the same gain, so the stereo image doesn't move. At depth 0 the input passes unchanged. Latency: one frame, reported to the host.

## More Ondinha plug-ins

- [Ondinha Bus Comp](https://github.com/ondinha/ondinha-bus-comp): Console-style glue compressor for the mix bus and groups.
- [Ondinha Split EQ](https://github.com/ondinha/ondinha-split-eq): Transient / tonal split EQ: separate gain for the attack and the sustain in every band.
- [Ondinha Limiter](https://github.com/ondinha/ondinha-limiter): True-peak brickwall limiter for mastering, with an optional oversampled clipper.
- [Ondinha Unmask](https://github.com/ondinha/ondinha-unmask): Spectral side-chain ducking: dips a track only at the frequencies where the key is loud, only while it plays.
- [Ondinha Imager](https://github.com/ondinha/ondinha-imager): Multiband stereo imager with mono low end: width for lows, mids and highs on phase-matched Linkwitz-Riley crossovers.
- [Ondinha Delay](https://github.com/ondinha/ondinha-delay): Tempo-synced stereo / ping-pong delay with filtered, saturated feedback and ducking, so the echoes stay out of the way of the vocal.
- [Ondinha Graphic EQ](https://github.com/ondinha/ondinha-graphic-eq): 10-band octave graphic EQ with analog-matched bells (31 Hz - 16 kHz, +-12 dB).
- [Ondinha Tube Air](https://github.com/ondinha/ondinha-tube-air): High-frequency exciter with a tube stage: adds warm even or bright odd harmonics above a frequency, under the untouched signal.

## Feedback

Found a bug or a host where it misbehaves? [Open an issue](../../issues) with your DAW, its version and your OS.
