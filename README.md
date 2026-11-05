# Focus — Personal Exam & Study Tracker

> A distraction-free, zero-build, single-file study dashboard and discipline engine built for competitive exam preparation.

![Focus App Preview](https://img.shields.io/badge/Stack-HTML5%20%7C%20CSS3%20%7C%20Vanilla%20JS-black?style=flat-square)
![Dependencies](https://img.shields.io/badge/Dependencies-GSAP%203.12%20%7C%20Three.js%20r128-black?style=flat-square)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local%20(No%20Server)-emerald?style=flat-square)

---

## Overview

**Focus** is an editorial-grade study companion designed for deep work, consistent problem-solving, and milestone tracking. Built without frameworks or build pipelines, the entire experience runs out of a single, self-contained `index.html` file that you can double-click to run locally or host directly on **GitHub Pages**.

It prioritizes quiet focus over gamification, featuring an austere monochrome palette, robust local persistence, safe-area mobile compatibility, and an adaptive missed-day recovery system.

---

## Key Features

### 1. Minimal Full-Screen Hero & Countdown
* **Live Countdown Display**: High-impact editorial numerals (*Instrument Serif*) tracking months, days, and total days remaining until the target exam date (28 Nov 2027).
* **"Where you stand" Live Headline**: A rotating data stage that continuously displays real-time tracker insights (questions solved today, focus time, current streak, latest mock percentile, Quant completion).
* **Quotes Carousel**: 12 curated quotes rotating smoothly with touch-swipe support and pause-on-hover.
* **Minimal Focus CTA**: Centered, prominent `Start Study` button that launches directly into deep work mode.

### 2. Focus River & Deep Work HUD
* **Three.js Particle River Canvas**: Generative particle flow that mirrors calm mental focus, backed by a lightweight 2D canvas fallback.
* **Persistent Session Timer**: High-precision stopwatch tracking elapsed active time across browser reloads.
* **Screen Wake Lock**: Automatically prevents mobile and laptop displays from sleeping while studying.
* **Under-60s Discard Guard**: Accidental or short sessions (< 1 minute) are discarded to maintain data integrity.

### 3. Daily Practice Question Logger
* **Three Core Sections**: Dedicated tracking for **VARC** (*Verbal Ability*), **DILR** (*Data Interpretation & Logical Reasoning*), and **Quant** (*Quantitative Aptitude*).
* **Clean Card Ergonomics**: Question addition controls stay hidden until toggled, preserving a clean workspace.
* **Quick-Add Buttons**:
  * VARC & Quant: `+5`, `+10`, `+15`, `+25`
  * DILR: `+4` (1 set), `+8` (2 sets), `+12`, `+16`
* **Mini Month Heatmap Widget**: Ultra-compact 250px monthly calendar in the section header showing active days and daily practice intensity.
* **Any-Date Practice Logging**: Jump to any past date or return to today with one click.

### 4. Mock Drills & Exam Analytics
* **Metric Dialog**: Log Sectional and Full Mocks with **Total Questions**, **Score/Marks**, and **Percentile (%ile)**.
* **Mock History Feed**: Chronological list of recorded attempts with section tags, scores, percentiles, and deletion support.
* **Interactive Mock Performance Chart (SVG)**:
  * Metric toggle: **Percentile** (primary) vs **Marks / Score**.
  * Scope filter: **All Mocks**, **Full Mocks**, or **Sectional Mocks**.
  * Section filter: **All**, **VARC**, **DILR**, **Quant**.
  * Reference target lines at **90%ile**, **95%ile**, and **99%ile**.

### 5. Quant Syllabus Mastery
* **22 Foundational Chapters**: Track progress across all 22 core arithmetic, algebra, geometry, and modern math topics strictly by name.
* **Granular Progress Control**: Percentage sliders and quick chips (`0%`, `25%`, `50%`, `75%`, `100%`).
* **Overall Completion Ring**: Animated SVG ring reflecting total syllabus mastery.

### 6. Missed-Day Alerts & Recovery System
An intelligent, non-shaming accountability engine calculated strictly from real stored data:
* **Part A (1-Day Miss)**: Firm self-check headline in "Where you stand" (*"Yesterday left nothing behind... One session now fixes it."*), alternating every other rotation until you study today.
* **Part B (2+ Days Miss)**: Accessible, full-screen blurred dialog on first Home view of the day with staggered reality checks and an encouraging closing line.
* **Part C (Section Miss)**:
  * 1–2 days untouched: Subtle reminder in rotation.
  * 3+ days untouched: Highlighted "Needs Attention" card with a direct `"Log a {Section} session"` action that jumps directly to the section card.

### 7. Performance Intelligence & Diagnostic Charts
* **KPI Stat Strip**: Total active days, current streak, longest streak, total study hours, mock counts, and Quant average.
* **Study Time Bar Chart**: Visualizes focus duration with filters for **14 Days**, **Months**, and **All Time**.
* **13-Month Activity Heatmap**: Complete annual view (Nov 2026 to Nov 2027) with 5 heat intensity levels and detailed hover tooltips.
* **Section Balance Donut Chart**: Proportional breakdown of question volume across VARC, DILR, and Quant.
* **Diagnostic Insights**: Dynamic plain-language analysis identifying strengths, gaps, and pacing projections.

---

## Data Privacy & Safety

* **100% Offline & Private**: All data is stored in your browser's `localStorage` under the key `examTracker.v1`. No external tracking, no accounts, and no servers.
* **JSON Export / Backup**: Download a clean `.json` file anytime from the Analysis page to backup your study history.
* **JSON Restore**: Re-import backup files anytime across different browsers or devices.
* **Safety Reset Guard**: Requires typing `"RESET"` to prevent accidental data wipes.

---

## Technical Architecture

* **Zero Build Step**: No `npm`, `vite`, `webpack`, or Node.js required to run.
* **Libraries Loaded via Pinned CDNs**:
  * [GSAP 3.12.5](https://greensock.com/) (with ScrollTrigger plugin) for animations.
  * [Three.js r128](https://threejs.org/) for the generative particle river.
* **Typography**:
  * Display: *Instrument Serif* (Google Fonts)
  * Body & Interface: *Inter* (Google Fonts)
* **Mobile Ready**:
  * Full `env(safe-area-inset-*)` support for notched phones, dynamic islands, and home indicator bars.
  * Fluid typography and spacing using `clamp()`.
  * Touch targets $\ge 44\text{px}$ across all interactive buttons and inputs.
* **Accessibility**:
  * Full `prefers-reduced-motion` support (disables particle river and heavy motion).
  * WCAG AA contrast ratios across both Dark and Light themes.
  * Dialog focus trapping with `Escape` key listeners.

---

## Getting Started

### Local Use
1. Clone or download this repository:
   ```bash
   git clone https://github.com/your-username/focus-tracker.git
   cd focus-tracker
   ```
2. Double-click `index.html` to open it in Chrome, Safari, Edge, or Firefox.

### Deploy to GitHub Pages
1. Push this repository to GitHub.
2. Go to **Settings** > **Pages**.
3. Under **Branch**, select `main` (or `master`) and folder `/ (root)`.
4. Click **Save**. Your study tracker will be live at `https://your-username.github.io/focus-tracker/`.

---

## License

Personal open-source study tool. Feel free to fork, adapt, and customize for your own exam preparation.

