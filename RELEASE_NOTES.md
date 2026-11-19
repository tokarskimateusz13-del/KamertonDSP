# KamertonDSP — Open Beta Release Notes (`v1.0.0-beta`)

Engineered in Wrocław, Poland

---

## Highlights
- **64-Bit Lossless Real-Time DSP Engine:** Native CoreAudio Process Tap (`CATapDescription`) with zero virtual audio drivers, 512-point `vDSP` exact headroom preamp calculation, and a 2.0 ms `-0.3 dBFS` lookahead peak limiter.
- **8,850+ AutoEq Profiles:** Built-in offline headphone database calibrated to the Harman OE2018 target curve (Attribution: AutoEq by Jaakko Pasanen, MIT License), plus AutoEq/Squiglink/REW `.txt` import & export.
- **AI Album Mastering:** Metadata-only tonal mastering classification with local caching, Severity gating thresholds, Linear Spectral Tilt (`1 kHz` pivot), L/R Channel Balance, BS2B Crossfeed, and ISO 226 Night Contour.
- **ITU-R BS.1770 Loudness Matching:** Downward-only K-weighted loudness compensation across profiles and `⌥ ⌘ E` A/B bypass comparisons.
- **Voice & Call Exclusion:** Automatically excludes Discord, Zoom, Microsoft Teams, FaceTime, and Slack from DSP processing (configurable under `System & Power`).
- **Clamshell Keep-Awake & Sleep Automation:** Closed-lid listening support protected by four hardware guards (Thermal, Speaker Auto-Bypass, Battery Guard, Silence Guard), Sleep Timer, and Perceptual Fade.
- **Hardened Security & Privacy:** HMAC-SHA256 signed API requests, anti-prompt-injection validation, global hourly AI cost circuit breaker, and 100% local audio processing (`PRIVACY.md`).

## Open Beta Notice
KamertonDSP is currently in Open Beta with all DSP, AutoEq, and AI Mastering features unlocked for testing. Core local EQ playback will remain free after the beta concludes, while advanced studio and cloud features will require a one-time v1.0 license. Active beta testers will receive extended trial access and early-supporter pricing at launch.

## Installation
Open `KamertonDSP-Beta.dmg` and double-click `Install KamertonDSP.command` for 1-click installation into `/Applications`, quarantine cleanup, and launch.
