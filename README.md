# Send_to_OSC — Releases

This repo hosts compiled releases of **Send_to_OSC**, a VirtualDJ native plugin that broadcasts deck metadata, lyrics, BPM, and beat position over OSC.

## Latest Release

**[v0.2.7](https://github.com/fitzgr/send_to_osc_releases/releases/tag/v0.2.7)** — 2026-03-23  
Adds INI-configurable OSC host/port (`Send_to_OSC.ini`) and updated plugin build.

## Installation

1. Download the `.zip` from the [Releases](https://github.com/fitzgr/send_to_osc_releases/releases) page
2. Copy `Send_to_OSC.dll` into your VirtualDJ plugins folder:  
   `C:\Users\<you>\Documents\VirtualDJ\Plugins64\`
3. Restart VirtualDJ
4. Load **Send_to_OSC** as an effect on the MASTER channel
5. The plugin broadcasts OSC to `127.0.0.1:9000` on every beat

Optional endpoint override:

- `C:\Users\<you>\Documents\VirtualDJ\Plugins64\Send_to_OSC.ini`

```ini
[osc]
host=127.0.0.1
port=9000
```

## Bridge Server (optional)

The included `bridge_server.py` bridges OSC into a browser-friendly HTTP/SSE API for the p5.js visualizer:

```powershell
python bridge_server.py --osc-host 0.0.0.0 --osc-port 9000 --http-host 127.0.0.1 --http-port 5173
```

Then open `index.html` in a browser.

## Source Code

https://github.com/fitzgr/send_to_osc

## Changelog

See [RELEASES.md](RELEASES.md) for full version history.