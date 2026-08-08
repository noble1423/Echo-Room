# Echo Room

A spatial voice memory app. No feed, no timeline, no profile — just a dark
room that remembers your voice. Walk through it and get close to a memory
to hear it again.

## Controls (mobile)
- **Bottom-left joystick** — walk
- **Drag anywhere else** — look around
- **Orange button (bottom-right)** — hold to record, release to drop the
  memory in the space in front of you
- Tilt your phone for a subtle gyroscope sway (asks permission on iOS)

## How it works
- Pure single-file HTML/JS, Three.js loaded from CDN — no build step
- Voice is recorded via `MediaRecorder`; if mic access is denied it falls
  back to a synthesized tone built from typed text (`OfflineAudioContext`)
- Playback runs through a real-time feedback-delay echo (`DelayNode` +
  `GainNode` loop)
- Memories persist locally in **IndexedDB** — nothing leaves the device,
  no backend

## Deploy
This is a static site — just `index.html`. Works as-is on GitHub Pages,
Netlify, Vercel, or any static host.
