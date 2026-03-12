# 🔊 TTS Script Player

A single-file, browser-based **Text-to-Speech script runner** — no installation, no server, no dependencies. Open `tts-player.html` in any modern browser and start speaking your script.

---

## Features

- **Script cards** — add, edit, reorder (drag-and-drop or arrow buttons), and delete lines
- **Timeline mode** — assign `M:SS` or `M:SS.s` timestamps to cards and fire them automatically like subtitle-driven audio
- **Voice selector** — grouped dropdown distinguishing Neural/Online voices from Standard ones, with auto-preference for Microsoft Andrew (Natural)
- **Rate & Pitch sliders** — fine-tune speech in real time
- **Live clock** — animated timeline counter with pulsing indicator while running
- **Import / Export JSON** — save and reload scripts; accepts both raw arrays and `{ lines: [...] }` objects
- **Audio routing tip** — built-in guide for routing TTS output to a virtual mic (e.g. VB-Audio CABLE) for use in recording apps
- **Zero dependencies** — uses the browser's native Web Speech API; no npm, no build step

---

## Usage

1. Download `tts-player.html`
2. Open it in Chrome, Edge, or any browser with Web Speech API support
3. Add lines manually, or click **★ Load Demo** to see a sample Steve Jobs script with timestamps
4. Hit **▶** on any card to speak it, or use **▶ Run Timeline** to play scheduled lines automatically

### Timeline Mode

Enter a timestamp on any card (e.g. `0:05`, `1:30.5`), then press **▶ Run Timeline**. Cards fire at their scheduled times — like an audio teleprompter.

### JSON Format

Scripts can be exported and re-imported. Format:
```json
{
  "lines": [
    { "text": "Hello world.", "timestamp": "0:00" },
    { "text": "This fires at 5 seconds.", "timestamp": "0:05" }
  ]
}
```

Or simply a root array of `{ "text": "...", "timestamp": "..." }` objects.

---

## Browser Support

| Browser | Status |
|---------|--------|
| Chrome / Edge (desktop) | ✅ Full support, including Neural voices |
| Firefox | ✅ Basic support (limited voice selection) |
| Safari | ✅ Basic support |
| Mobile browsers | ⚠️ Partial — Web Speech API support varies |

---

## Audio Routing (for streamers / recorders)

To use TTS as a mic input in OBS, Discord, Zoom, etc.:

1. Install [VB-Audio CABLE](https://vb-audio.com/Cable/)
2. In Windows Volume Mixer, set your browser's audio output to **CABLE Input (VB-Audio)**
3. In your recording app, select **CABLE Output** as your microphone

---

## License

This project is licensed under the **GNU General Public License v3.0**. See [LICENSE](LICENSE) for details.
