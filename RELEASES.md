# Release Notes

---

## v0.2.6 — 2026-03-23

First public release of Send_to_OSC.

### What's included
- `Send_to_OSC.dll` — VirtualDJ native audio effect plugin (x64)
- `bridge_server.py` — Python OSC→HTTP bridge for browser clients
- `tools/p5_visualizer/` — p5.js beat-reactive visualizer with video sync

### Plugin features
- Broadcasts deck metadata over OSC to `127.0.0.1:9000` on every beat (configurable)
- OSC addresses: `/vdj/title`, `/vdj/artist`, `/vdj/bpm`, `/vdj/beat_phase`, `/vdj/bar_phase`, `/vdj/song_pos_beats`, `/vdj/position_seconds`, `/vdj/lyrics`, and a wide `/vdj/probe/*` namespace covering VDJ internal variables (pitch, gain, volume, elapsed, remain, etc.)
- Four toggle parameters in VDJ UI: Send Metadata, Send Lyrics, Send Status, Send On Beat

### Bridge features
- `/state` — full latest metadata snapshot as JSON
- `/events` — Server-Sent Events stream for live browser updates
- `/media` — HTTP range-request video streaming for browser video sync
- `updated_at` timestamp in state enables transit-latency compensation

### Visualizer features
- Beat-reactive comet with fading trail
- Center media mode: rotates between static internet art and track video
- Video sync with transit compensation and proportional `playbackRate` correction
- Now Playing HUD (artist + title)
- Debug HUDs available (off by default)

### Requirements
- VirtualDJ 2024+ (64-bit)
- Windows 10/11 x64
- Python 3.10+ (for bridge server)
- Modern browser (Chrome/Edge recommended for video sync)

### Installation
1. Copy `Send_to_OSC.dll` → `Documents\VirtualDJ\Plugins64\`
2. Restart VirtualDJ
3. Load **Send_to_OSC** as a MASTER effect

### Source
https://github.com/fitzgr/send_to_osc — tagged `v0.2.6`
