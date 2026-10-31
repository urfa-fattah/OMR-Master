# OMR Master Pro 🎯

> **A modern, responsive, and privacy-focused digital OMR examination, grading, and diagnostic platform built for competitive students and educators.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20PWA-green.svg)](#features)
[![UI: TailwindCSS](https://img.shields.io/badge/UI-TailwindCSS%20%2B%20Glassmorphism-38bdf8.svg)](https://tailwindcss.com/)
[![React](https://img.shields.io/badge/React-18-61dafb.svg)](https://react.dev/)

---

## 📖 Overview

**OMR Master Pro** transforms standardized pen-and-paper OMR (Optical Mark Recognition) practice into a high-speed, intelligent web experience. It allows students preparing for competitive exams (medical, engineering, university admission, BCS, and public service tests) to simulate realistic timed exams, instantly grade their sheets with customized positive/negative marking schemes, and diagnose their cognitive mistake habits through deep performance diagnostics.

Built completely client-side with **zero server dependencies**, the application runs smoothly in modern desktop and mobile browsers, works offline as an installable **Progressive Web App (PWA)**, and keeps all test results strictly private inside your browser's local storage.

---

## ✨ Key Features

### 1. ⚙️ Smart Exam Configurator (`index.html`)
- **Custom Exam Setup**: Configure question count (1 to 200+), exam duration (minutes/hours), options count (4 or 5 options: A–D or A–E), positive marks per question, and negative marking penalty deductions (e.g., 0.20, 0.25, 0.50).
- **Exam Presets**: Fast 1-click presets for popular competitive exam formats.
- **Active Session Resumption & Cancellation**: Automatically detects in-progress exams with a live time progress indicator. Students can resume seamlessly or cleanly cancel the session.
- **Dashboard Overview**: Displays quick historical test metrics (total exams taken, overall average score, last exam date).
- **PWA Installation**: Installable directly onto mobile devices and PCs as a standalone app.

### 2. 📝 Realistic OMR Exam Sheet (`exam.html`)
- **Fluid OMR Bubble Grid**: Highly tactile, touch-optimized circular bubbles with smooth animations and instant visual feedback.
- **Fast Keyboard Navigation**:
  - `A`, `B`, `C`, `D`, `E` — Bubble selection with auto-advance to next question.
  - `F` — Flag / unflag question for later review.
  - `Backspace` / `Delete` — Clear selected answer for the current question.
  - `↑` / `↓` / `←` / `→` — Navigate between questions smoothly.
- **Dynamic Header & Countdown Timer**: High-visibility timer with low-time warning alerts (< 60s).
- **Quick Question Drawer**: Drawer displaying all questions with distinct badges (Answered, Flagged, Unanswered) allowing one-tap jumping.
- **Exam Safeguards**:
  - **Quit Exam Modal**: Prevents accidental exits while providing a clear option to abandon when needed.
  - **Submit Confirmation Modal**: Summarizes answered vs. unanswered counts before submission.
  - **Auto-Save & `beforeunload` Protection**: State auto-saves locally; accidental tab closure or browser back is intercepted with a confirmation prompt.

### 3. 🎯 Answer Key Verification & Instant Grading (`correction.html`)
- **Side-by-Side Verification**: Displays the student's chosen answer next to answer key input buttons for each question.
- **One-Click Key Configuration**: Select correct answers (`A`–`E`) for individual questions or use quick batch presets.
- **Answer Key Templates**: Automatically remembers and persists answer keys for identical exam names for effortless re-grading.
- **Immediate Score Calculation**: Calculates total marks gained, negative penalty deductions, skipped questions, and net score accurately.

### 4. 📊 Advanced Analytics & Mistake Diagnostic Hub (`analytics.html`)
- **Detailed Question Breakdown**:
  - Inspect every question individually with filter tabs: **All**, **Correct**, **Wrong**, and **Skipped**.
  - Side-by-side comparison of **Your Answer** vs. **Correct Key** with net mark impacts (`+1.00`, `-0.25`, etc.).
  - Jump-to-question search and interactive clickable heatmap grid.
- **Frequent Mistakes Diagnostic Hub**:
  - **Penalty Loss Math**: Calculates exact marks deducted due to incorrect guesses and computes potential score without wild guessing.
  - **Trap Option Bias**: Identifies which specific option letter (e.g., Option `B` or `C`) the student defaults to when making incorrect guesses.
  - **3-Phase Fatigue Analysis**: Divides the exam into Early, Middle, and Late thirds to detect whether errors increase due to mental fatigue or rushing near the end.
  - **Consecutive Wrong Streak Detection**: Highlights streaks of back-to-back mistakes to reinforce disciplined exam-taking pacing.
  - **Multi-Exam Historical Insights**: Compares mistake patterns across all previous tests.
- **Targeted Retake Mode**: "Retake Mistakes Only" allows students to launch a focused practice session consisting solely of questions answered incorrectly.
- **Score Comparison & Attempt History**: Compare performance across repeated attempts of the same test.
- **Printable Summary**: Clean layout optimized for printing or saving as a PDF summary report.

### 5. 🌐 Bilingual & Accessibility Support
- **Dual Language Support**: Instant switching between **English (EN)** and **Bengali (BN)** with native typography (`Hind Siliguri`).
- **Dark & Light Mode**: Smooth theme transitions with persistent theme storage.
- **Cross-Device Responsiveness**: Tailored layouts for Android smartphones, tablets, laptops, and wide desktop screens.
- **Bulletproof Error Resilience**: Integrated `ErrorBoundary` architecture across all pages preventing blank screens and offering one-click recovery.

---

## 🗂️ Project Structure

```text
OMR-Master-main/
│
├── index.html          # Main landing dashboard, configuration & session resume
├── exam.html           # Fullscreen interactive OMR examination interface
├── correction.html     # Answer key entry, auto-grading & score finalization
├── analytics.html      # Comprehensive exam analysis & mistake diagnostics
├── guideline.html      # Examination instructions, keyboard guides & best practices
├── report.html         # Issue reporter & feedback management
├── about.html          # Project overview & developer profile
├── contact.html        # Contact information & message portal
├── donate.html         # Platform support & sponsorship details
│
├── manifest.json       # Progressive Web App (PWA) manifest
├── sw.js               # Service Worker for offline asset caching
├── icon.png            # Application logo and touch icon
└── README.md           # Project documentation
```

---

## 🛠️ Technology Stack

- **Core Framework**: [React 18](https://react.dev/) (Browser Standalone via UMD)
- **Compiler**: [Babel Standalone](https://babeljs.io/) (In-browser JSX compilation — no build step required)
- **Styling**: [Tailwind CSS CDN](https://tailwindcss.com/) with modern Glassmorphism, CSS variables, and dark mode
- **Charts & Visualizations**: [Chart.js](https://www.chartjs.org/) (Radar, Doughnut, Line & Bar charts)
- **Typography**: Google Fonts ([Inter](https://fonts.google.com/specimen/Inter) and [Hind Siliguri](https://fonts.google.com/specimen/Hind+Siliguri))
- **Data Persistence**: HTML5 `localStorage` (100% private, client-side, zero backend server required)
- **Offline / PWA**: Web App Manifest & Service Worker API

---

## 🚀 Getting Started

No build tools, bundlers, or package managers (npm, pnpm, yarn) are required. The project runs directly out of the box:

### Option 1: Direct File Launch
Simply double-click `index.html` in your file explorer to open it in Google Chrome, Microsoft Edge, Mozilla Firefox, or Safari.

### Option 2: Local HTTP Server (Recommended for PWA testing)
For the best experience with Service Workers and PWA installation:

```bash
# Using Python 3
python -m http.server 8000

# Or using Node.js npx serve
npx serve .
```

Then visit `http://localhost:8000` in your browser.

---

## ⌨️ Exam Keyboard Shortcuts

| Key | Action |
|:---:|:---|
| `A`, `B`, `C`, `D`, `E` | Select bubble & advance to next question |
| `F` | Flag / Unflag current question for review |
| `Backspace` / `Delete` | Clear current question's answer |
| `↓` / `→` | Move to next question |
| `↑` / `←` | Move to previous question |

---

## 🔒 Privacy & Security

OMR Master Pro operates entirely in the user's browser:
- **No external servers** track, log, or store test papers, scores, or personal responses.
- All exams, templates, and analytics remain strictly in the device's browser `localStorage`.
- Works fully **offline** once the page and fonts are cached.

---

## 👨‍💻 Author & Maintainer

- **Developer**: **Urfa Hasan Fattah**
- **Repository**: [OMR-Master](https://github.com/UrfaHasanFattah)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
