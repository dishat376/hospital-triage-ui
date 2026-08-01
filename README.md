# Meridian Health — AI Triage & Capacity Console

A front-end concept for an **AI-powered medical queue and hospital management system**. It shows how an emergency department could sort patients by clinical urgency (not arrival time), while giving staff a live view of beds and workload — all in one screen.

![status](https://img.shields.io/badge/status-demo-blue) ![type](https://img.shields.io/badge/type-frontend--only-lightgrey)

---

## What this is

This is a **static, front-end demo** — a single HTML file with embedded CSS and JavaScript. There is no backend, database, or real patient data behind it. It's meant to show the *design and interaction concept* of an AI-assisted triage system, not to run a real hospital.

## Live preview

Open `index.html` in any modern browser — no build step, no install, no server required.

```bash
# just open it directly
open index.html        # macOS
start index.html        # Windows
```

Or host it for free with GitHub Pages once pushed to a repo (Settings → Pages → deploy from `main` branch).

---

## Key features

| Feature | Description |
|---|---|
| **AI Triage Queue** | Patients are grouped into 5 tiers using the real-world **ESI (Emergency Severity Index)** scale — from ESI 1 (immediately life-threatening) to ESI 5 (non-urgent) — instead of a simple first-come-first-served line. |
| **Live pulse indicator** | Each patient card has an animated pulse-line whose speed and height reflect their urgency level — fast/sharp for critical, slow/calm for minor. |
| **Hospital vitals bar** | Top bar shows real-time-style stats: patients waiting, average wait time, open beds, and staff on shift. |
| **Bed status grid** | Visual grid showing which beds are occupied, available, or being cleaned. |
| **Staff load panel** | Shows each doctor/nurse and how many patients they're currently handling, to help balance workload. |
| **AI assistant note** | A small panel explaining that patient order is continuously re-scored as new vitals come in. |
| **Responsive layout** | Sidebar collapses into a horizontal scroll bar on narrow/mobile screens. |
| **Simulated live updates** | Wait times tick upward automatically every 15 seconds to mimic a real, live queue. |

## What ESI means

The **Emergency Severity Index** is a 5-level scale real hospitals use to sort ER patients by urgency:

| ESI Level | Meaning | Example |
|---|---|---|
| 1 | Immediate — life-threatening | Cardiac arrest |
| 2 | Emergent — high risk | Stroke symptoms |
| 3 | Urgent — needs prompt care | Suspected fracture |
| 4 | Standard — stable, lower acuity | Sprain, mild fever |
| 5 | Minor — non-urgent | Prescription refill |

The queue always shows Tier 1 at the top, regardless of who checked in first — the sickest patients are seen soonest.

## Tech stack

- **HTML5 / CSS3** — layout, styling, responsive design
- **Vanilla JavaScript** — no frameworks or libraries; queue rendering, live simulation, and clock all run in plain JS
- **Google Fonts** — IBM Plex Sans, IBM Plex Sans Condensed, IBM Plex Mono

No dependencies to install. No `npm install`, no build pipeline.

## Project structure

```
hospital-triage-ui/
├── index.html      # everything — markup, styles, and logic in one file
└── README.md        # this file
```

## Customizing the demo

All sample data lives near the top of the `<script>` block in `index.html`:

- `patients` — array of patient objects (id, name, age, complaint, ESI level, wait time, vitals)
- `bedStates` — array representing each bed's status (`"occ"`, `"free"`, `"clean"`)
- `staff` — array of staff members and their current patient load

Edit these arrays directly to change what's shown — no build step needed, just refresh the page.

## Limitations (by design, since this is a demo)

- No real backend, database, or API — all data is hardcoded sample data
- No patient intake form or authentication
- Not intended for real clinical use — ESI assignment here is illustrative, not a real triage tool
- No persistence — refreshing the page resets everything to the sample data

## Possible next steps

- Connect to a real backend/database for live patient records
- Add a patient intake form to add new patients to the queue
- Add click-to-expand patient detail view with full vitals history
- Add authentication/role-based views (nurse vs. doctor vs. admin)
- Add real bed-assignment workflow (drag-and-drop patient to bed)

---

*This project is a UI/UX concept only and is not a certified medical device or clinical decision-support tool.*
