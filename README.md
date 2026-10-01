# CYBERSPEED 3D — Autonomous 3D Internet Speed Telemetry

A futuristic, standalone, single-page 3D web application built with pure HTML5, CSS3, and native WebGL to measure real internet connection bandwidth, latency, and stability. 

Contains **zero third-party speed test APIs**, **zero external JavaScript libraries/CDNs**, and **zero tracking scripts**. Everything runs autonomously directly in the browser.

[Demo Website](https://tricksxtech.github.io/CyberSpeed/)

---

## Features

### 1. Pure In-House 3D WebGL Engine
- **Custom 3D Math Pipeline**: Built from scratch with custom 4x4 matrix transformation primitives (`perspective`, `lookAt`, `rotateX`, `rotateY`, `rotateZ`, `translate`).
- **3D Speedometer Instrument**: 252° curved gauge track with graduated major and minor tick marks, metallic center hub, and a dynamic illuminated neon arc that fills in real time with bandwidth.
- **Physical Spring-Damped Needle**: Realistic needle inertia, acceleration, and spring physics.
- **Interactive Orbit Camera**: Click and drag (or touch swipe on mobile) to inspect the 3D gauge from any angle, with an instant camera reset control.
- **3D Warp Field Starfield**: 3,000 perspective particles streaming through 3D space, accelerating into lightspeed streaks during download and reversing outward with a violet hue shift during upload.
- **Infinite Perspective Grid**: Ambient horizon grid grounding the 3D instrument.

### 2. 100% Real Live Network Telemetry (No Mock / Fake Data)
- **Ping & Latency**: High-precision round-trip delta measurement using microsecond-accurate `performance.now()`.
- **Packet Jitter**: Real-time calculation of Mean Absolute Deviation between consecutive packet deltas.
- **Downlink Throughput**: Concurrent multi-stream raw binary chunk pipeline measuring true bits-per-second arriving over the wire:
  $$\text{Mbps} = \frac{\text{Bytes Received} \times 8}{\text{Elapsed Seconds} \times 1,000,000}$$
- **Uplink Throughput**: In-memory high-entropy payload generation and transmission rate profiling via direct HTTP POST socket streams.
- **Nearest Datacenter Detection**: Automatically identifies the closest active CDN edge node.
- **Real-Time Waveform Oscilloscope**: 60 FPS hardware-accelerated canvas visualizer rendering live bandwidth fluctuations.

### 3. Integrated Web Audio Synthesizer
- Built using the native Web Audio API (zero external audio files).
- Engine rev frequency modulation tied to live Mbps speed.
- High-frequency radar ping blips during latency probing.
- Completion triad chord fanfare.
- Instant sound toggle (`AUDIO: ON / MUTED`) in the top navigation bar.

### 4. Professional Responsive UI
- Cyberpunk dark glassmorphism design system (`#060913` obsidian background, electric cyan and hyper-violet accents).
- High-contrast, tabular digits (`font-feature-settings: "tnum"`) to eliminate number jitter during rapid counting.
- Adaptive layout: 4-column telemetry deck on desktop, responsive 2x2 grid on mobile devices.
- Auto-scaling 3D camera distance based on screen aspect ratio so the dial never clips on narrow phone screens.

---

## File Structure

```
├── index.html     # Complete self-contained single-page application (HTML5, CSS3, WebGL JS)
└── README.md      # Project documentation and technical overview
```

---

## How to Run

No installation, build tools, or dependencies required.

1. Navigate to the `hkkl` folder.
2. Double-click `index.html` to open it in any modern browser:
   - Google Chrome
   - Microsoft Edge
   - Mozilla Firefox
   - Brave
   - Safari (macOS / iOS)
3. Click **"START TEST"** to initiate the 3D benchmark.

*Optional*: You can also host it with any local static HTTP server:
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .
```

---

## Verification

To verify that the speed measurements are 100% real:
1. Open `index.html` in your browser.
2. Press <kbd>F12</kbd> (or right-click $\rightarrow$ **Inspect**) and open the **Network** tab.
3. Click **"START TEST"**.
4. Observe the live multi-megabyte socket streams transferred across the wire, with byte counts and timing matching the on-screen 3D gauge.

---

## License

MIT License. Free to use, modify, and distribute.
