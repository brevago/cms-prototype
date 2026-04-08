# SOTI CMS — Digital Signage Platform Prototype

> A functional prototype demonstrating how SOTI MobiControl integrates with a content management system for enterprise digital signage. Built for product evaluation by SOTI stakeholders and customers.

---

## 🚀 Live Demo

**[▶ Open the Prototype](https://yourname.github.io/soti-cms-prototype/soti-cms-shareable.html)**

> No login required. Opens directly in any modern browser. Mock data is pre-loaded so you can explore all features immediately.

---

## 📋 What This Prototype Demonstrates

This prototype shows the value of combining **SOTI MobiControl** with a dedicated digital signage CMS — giving operators a single platform to create content, schedule deployments, and verify playback across all managed screens.

### The Value Story

| Without SOTI CMS | With SOTI CMS + MobiControl |
|---|---|
| Manual content updates per device | Push playlists to device groups instantly |
| No visibility into what's on screen | Real-time Proof of Play with screenshots |
| Separate tools for content and device mgmt | Unified platform — create, schedule, deploy, verify |
| No remote troubleshooting | Remote reboot via MobiControl from the dashboard |
| No scheduling intelligence | Time-of-day playlist switching, automated |

---

## ✨ Features

### 🎨 Layout Editor (WYSIWYG)
- Drag-and-drop canvas with pixel-accurate positioning
- Add **images, video, text, and ticker zones**
- Text styling: font size, colour, alignment, bold
- Multi-zone layouts (Main Content + Lower Third)
- Resolution presets: **1920×1080, Portrait 1080×1920, 4K, 720p**
- Content expiry dates per slide
- Multi-slide management with per-slide duration

### 📂 Content Library
- Upload images, videos, and HTML assets
- Reusable asset library across all slides and playlists
- Drag-and-drop upload support

### 🎬 Playlist Manager
- Group slides into named playlists with loop control
- Per-slide duration override
- One-click **Push to MobiControl** deployment

### 📅 Scheduler
- Visual 24-hour timeline per device group
- **Time-of-day playlist switching** (e.g. Morning / Afternoon / Evening)
- Date ranges, repeat rules (Daily / Weekdays / Weekends / One-time)
- Device group targeting synced from MobiControl
- Bulk deploy all schedules to devices

### ✅ Proof of Play Dashboard
Real-time verification of every screen, pulling live data from MobiControl:

| Metric | Source |
|---|---|
| Device online / offline | MobiControl device status |
| Connectivity type (WiFi / Cellular / Ethernet) | MobiControl device metadata |
| Signal strength | MobiControl device metadata |
| Correct playlist deployed | CMS deployment record |
| **Live screenshot of what's on screen** | MobiControl Screenshot API |
| Remote reboot | MobiControl Device Actions API |

### 🖥️ Device Management
- Full device list synced from MobiControl
- Group hierarchy, OS version, IP address, last check-in
- Per-device screenshot and reboot actions

### 🚨 Emergency Override
- One-click push of emergency content to **all screens instantly**
- Bypasses all active schedules
- Cancel to resume normal programming

### ⚙️ MobiControl Settings
- Configurable server URL, Client ID, Client Secret
- Live connection test with feedback
- Mock mode fallback for demos without a live MC instance

### 📋 Audit Log
- Full history of all CMS actions with timestamps
- Exportable as CSV

---

## 🔌 MobiControl Integration

This prototype integrates with the **MobiControl REST API v2** using OAuth2 client credentials flow.

### Authentication
```
POST {server}/api/token
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials
client_id={your_client_id}
client_secret={your_client_secret}
```

### API Endpoints Used

| Feature | Endpoint |
|---|---|
| Device list | `GET /api/v2/devices` |
| Device groups | `GET /api/v2/devicegroups` |
| Screenshot | `POST /api/v2/devices/{id}/screenshot` |
| Remote reboot | `POST /api/v2/devices/{id}/actions` |

### Connecting to Your MobiControl Instance

1. Open the prototype in your browser
2. Navigate to **MC Settings** (bottom of left sidebar)
3. Enter your:
   - **Server URL** — e.g. `https://your-tenant.soti.net/MobiControl/`
   - **Client Name**
   - **Client ID**
   - **Client Secret**
4. Click **Test Connection**
5. On success, all device data loads live from your MobiControl environment

> **No MobiControl instance?** The prototype runs fully in mock mode with realistic simulated data — 8 devices across 5 location groups, pre-built playlists, and simulated screen previews.

---

## 🗂️ Repository Structure

```
soti-cms-prototype/
├── README.md                    ← You are here
├── soti-cms-shareable.html      ← Full prototype (no credentials, shareable)
```

The entire application is a **single self-contained HTML file** — no build step, no dependencies, no server required. Open it directly in a browser.

---

## 🧭 How to Run Locally

1. Download `soti-cms-shareable.html`
2. Open it in Chrome, Edge, Firefox, or Safari
3. That's it — no install, no server, no Node.js

---

## 🌐 How to Deploy on GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)` folder
4. Save — your live URL will be:
   ```
   https://your-username.github.io/soti-cms-prototype/soti-cms-shareable.html
   ```

---

## 📐 MVP Feature Tiers

### Tier 1 — Implemented in this prototype
- [x] MobiControl Settings & live connection
- [x] Content Library with asset upload
- [x] WYSIWYG Layout Editor with zones, multi-element canvas
- [x] Text styling (font size, colour, alignment, bold)
- [x] Resolution + orientation presets
- [x] Playlist Manager with slide ordering
- [x] Time-of-day Scheduler with visual timeline
- [x] Device group targeting
- [x] Emergency override
- [x] Proof of Play dashboard (online, connectivity, signal, playlist, screenshot)
- [x] Remote reboot via MobiControl
- [x] Audit log with CSV export
- [x] Proof of Play CSV export
- [x] Mock mode fallback

### Tier 2 — Recommended next phase
- [ ] Proof of Play PDF report export
- [ ] Content expiry automation (auto-remove expired slides)
- [ ] Ticker data feeds (RSS, live data sources)
- [ ] Role-based access (Editor / Publisher / Admin)
- [ ] Approval workflow before publishing
- [ ] Multi-tenant / multi-customer support

---

## 🔒 Security Notes

- This repository contains **no credentials** — the shareable file requires users to enter their own MobiControl connection details at runtime
- Credentials entered in the Settings panel are stored in browser memory only and are not persisted or transmitted anywhere other than the MobiControl API
- For production use, credentials should be managed server-side with proper secret management

---

## 🏗️ Technical Notes

- **No frameworks** — pure HTML, CSS, and vanilla JavaScript
- **No build step** — single file deployment
- **No backend** — all state is in-memory; MobiControl is the data source
- **CORS** — live MobiControl API calls require your MC server to allow requests from the prototype's origin. For local file use, some browsers may require a local server (`python3 -m http.server`) or CORS to be configured on the MC server

---

## 📬 Contact

Built by the SOTI Product team for internal evaluation and customer demonstrations.

For questions about MobiControl API access or this prototype, contact your SOTI product representative.

---

*SOTI CMS Prototype — For evaluation purposes only. Not a production product.*
