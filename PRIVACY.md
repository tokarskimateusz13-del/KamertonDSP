# KamertonDSP Privacy Policy (GDPR)

**Effective Date:** November 18, 2026  
**Product:** KamertonDSP (macOS Open Beta)  
**Origin:** Engineered in Wrocław, Poland

---

## 1. Zero Audio Recording or Streaming
KamertonDSP processes **100% of your system audio locally in real time** inside macOS memory using Apple's native CoreAudio Process Tap and 64-bit `vDSP` math.

- KamertonDSP **never** records microphone input.
- KamertonDSP **never** writes audio buffers to disk.
- KamertonDSP **never** streams, uploads, or inspects your audio on any remote server.

System Audio Recording permission in macOS is used exclusively to apply your local headphone calibration, crossfeed, and EQ filters before returning audio to your headphones or DAC.

---

## 2. Data Processed When AI Album Mastering Is Enabled
If you keep **Auto-Lock AI Mastering** enabled (and AI Intervention is not set to `Off`), KamertonDSP sends a minimal text-only classification request (`POST /classify`) to our Cloudflare Worker proxy (`aetherdsp-api.matrio.workers.dev`) and, on a cache miss, to the **Google Gemini API**:

- **Track metadata:** Artist name, album name, track title (if available), and selected headphone model name.
- **Anonymized device identifier (`X-Device-Id`):** A one-way salted SHA-256 hash derived locally on your Mac for rate limiting and license binding.
- **IP address (transient):** Processed by Cloudflare at the edge strictly for DDoS protection, rate limiting, and global cost-protection circuit breaking. IP addresses are not stored in the album classification cache.

Classification results are cached locally in `~/Library/Application Support/AetherDSP/album_cache.json` and globally in Cloudflare KV (keyed strictly by normalized `artist::album`, without user identifiers) for up to 90 days.

You can disable all cloud classification at any time by turning **Auto-Lock** off or setting **AI Intervention** to **Off**.

---

## 3. Optional Feedback & Headphone Requests
When you voluntarily submit the built-in **Feedback & Headphone Request** form (`POST /feedback`):

- Your selected category, message, optional email address (if provided for v1.0 beta tester follow-up), and optional technical diagnostics (app version, macOS version, headphone model, output device name, and sample rate — **zero music or listening history**) are stored in **Cloudflare KV** under `feedback:<timestamp>`.
- If configured by the maintainer, a summary notification may be forwarded to a private support webhook.
- Providing an email address is completely optional.

---

## 4. Offline Licensing & Local Storage
- User settings, custom PEQ variants, album cache, Open Beta sunset state, and Ed25519 license certificates (`license.dat`) are stored locally in `~/Library/Application Support/AetherDSP/`.
- KamertonDSP does **not** include third-party ad SDKs, behavioral analytics, or background telemetry beacons.

---

## 5. Your Rights Under GDPR
If you reside in the European Economic Area (EEA) or the UK, you have the right to access, rectify, or request deletion of any optional personal data you submitted (such as an optional email address in a feedback submission).

To request deletion or ask privacy questions, send a message via the in-app Feedback form referencing your email/submission ID, or clear all local data at any time by deleting `~/Library/Application Support/AetherDSP/`.
