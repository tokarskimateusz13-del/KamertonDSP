# Security & Privacy Policy

## Supported Versions

Security and stability fixes are provided for the latest Open Beta release on supported macOS versions:

| Version | Supported |
| :--- | :--- |
| Latest Open Beta (`v0.x` on macOS 14.4+) | :white_check_mark: |
| macOS 14.3 and older | :x: (CoreAudio Process Tap API unavailable) |

## Audio Privacy & Architecture Guarantees

Because KamertonDSP uses Apple's native `CATapDescription` (CoreAudio Process Tap) API to apply system-wide EQ without virtual audio drivers, macOS prompts for **System Audio Recording** permission (`NSAudioCaptureUsageDescription`) on first launch.

KamertonDSP enforces the following strict privacy boundaries:

1. **100% On-Device Real-Time Processing:** All DSP rendering (`vDSP_biquadD`), headroom analysis, and peak limiting execute strictly in memory on your Mac. Audio buffers are never written to disk, recorded, or transmitted over the network.
2. **Communication App Exclusion:** Voice and video conferencing applications (Discord, Zoom, Microsoft Teams, FaceTime, Slack) are excluded at the CoreAudio tap level so call audio is neither intercepted nor processed.
3. **Zero Telemetry & No Tracking:** The application contains no analytics SDKs, crash-reporting trackers, or background data collection.
4. **Optional "Album Mastering" Feature:**
   - Disabled/bypassed by default unless toggled on by the user.
   - When enabled, **no audio data** is ever inspected or uploaded—only local track/album metadata (artist and album title) is queried once per album and cached locally to look up mastering dynamic range characteristics.
   - Can be switched completely **Off** at any time from the menu bar.
5. **Local Configuration & Profiles:** All custom PEQ curves, imported `.txt` presets, and per-device settings are stored locally on your machine.

## Reporting a Vulnerability

Please **do not** report security vulnerabilities through public GitHub Issues.

Instead, report them privately using one of the following channels:
- **GitHub Private Vulnerability Reporting (Preferred):** Go to the **Security** tab of this repository and click **"Report a vulnerability"**.
- **Direct Contact:** Reach out via the repository owner's contact details listed on the GitHub profile with `[SECURITY] KamertonDSP` in the subject line.

Please include steps to reproduce, your macOS version, and the affected KamertonDSP release version. Reports are typically acknowledged within a few days, and fixes are coordinated prior to public disclosure.
