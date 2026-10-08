# Voudontronics NERVE
Hybrid sampler + synthesizer

**NERVE is an omnivorous transduction synthesizer for Linux.**

It is deliberately not a virtual analogue. Four **AFFERENTS** ingest arbitrary files and reinterpret them as signal/state/events. Four nontraditional generators — **AXON, GANGLION, BYTEWORM, KNOT** — form the other half of the organism. **GLIA** is a cellular-automaton modulation field, while **SYNAPSE** is a sparse routing system in which individual connections may use Sample+Hold.

This is the first playable architectural prototype, not the finished instrument.

## Current organs

- Four AFFERENT slots; each can load *any non-empty file*.
- Modes: `RAW BYTE`, `BITPLANE`, `TERRAIN`, `EVENT`, `AUDIO`.
- AUDIO understands uncompressed WAV directly; all other formats safely fall back to raw-byte interpretation.
- **AXON**: stochastic continuously mutating breakpoint waveform.
- **GANGLION**: stochastic impulse population exciting a resonant process.
- **BYTEWORM**: bitwise/integer computational generator.
- **KNOT**: nonlinear Hénon-like strange-attractor generator.
- **GLIA**: elementary cellular automaton used as global modulation weather.
- **SYNAPSE**: sparse node-to-node modulation matrix, with S&H living at connection level.
- Deterministic 64-bit patch seed plus BLAKE2b-256 identity for every ingested file.
- `SPACE` = new reproducible random state.
- `M` = mutation rather than replacement.
- `S` = record/stop and save WAV.
- Save/load `.nerve.json` patches; changed or missing food files are reported rather than silently substituted.
- Optional TouchMe support: CC90 controls **NERVE PRESSURE**.
- Optional generic gamepad support: trigger axes control pressure; main face buttons randomize/mutate.
- Offline renderer for machines where realtime audio is not yet configured.

## Install on Debian / Ubuntu / Ubuntu Studio

You will normally want PortAudio development/runtime packages available:

```bash
sudo apt install python3-venv libportaudio2 portaudio19-dev
```

Then:

```bash
cd nerve_v0_1
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -e .
nerve
```
