# TruthLens — Misinformation Triage Platform

> **Civic Tech:** A neutral-by-design misinformation triage platform for newsrooms and citizen watchdog groups to triage viral social media claims at the speed of information flow.

---

## 🎯 Overview

Social media moves faster than fact-checkers can. **TruthLens** checks information characteristics, not ideologies. It enables rapid triage of viral posts using rule-based risk signals and an editorial fact-checking workflow.

---

## ⚡ 5 Required Features

1. **Submit a Claim**:
   - Ingest viral posts with source platform selection (**WhatsApp, X, Instagram, Facebook, TikTok, Reddit, Other**), category classification (**Politics, Health, Finance, Other**), and optional source links.
   - Live real-time risk flag calculation as the user types.
   - Quick 1-click sample presets for rapid demonstration.

2. **Automated Risk Flags Engine**:
   - ⚡ **Sensational**: Detects sensationalist keywords (`"breaking"`, `"shocking"`, `"share before deleted"`).
   - 📢 **Shouting**: Triggers if `> 50%` of alphabetic letters are UPPERCASE.
   - 🔗 **Unsourced**: Flags posts with missing HTTP/HTTPS reference citations.
   - 🔥 **High Risk**: Automatically marks posts triggering **2 or more flags** with priority badges.

3. **Review Workflow**:
   - Editorial triage queue enabling fact-checkers to assign verdicts:
     - **Verified True** (Green)
     - **Misleading** (Amber)
     - **False** (Red)
     - **Unverified** (Slate Blue)
   - Mandatory reviewer notes and attribution.

4. **Public Feed**:
   - Clean, responsive card grid with status badges.
   - Filter by Category (*Politics, Health, Finance, Other, All*).
   - Filter by Status (*Unverified, Verified True, Misleading, False, All*).
   - High-Risk only filter.
   - Full-text search across claims, notes, and platforms.

5. **Detail View**:
   - Verbatim post text with 1-click copy.
   - Granular forensic breakdown of triggered risk flags and why they triggered.
   - Reviewer verdict, timestamp, and notes.
   - Complete forensic audit trail.

---

## 🏛️ Architectural Decision Points (DP1 – DP3)

- **DP1 · Feed Order Strategy**: Dual-Lens Hybrid. Default prioritizes High-Risk unverified claims for editorial speed, while providing users seamless toggles between Recency, Risk Severity, and Triage Status.
- **DP2 · Visibility Policy**: Transparent Quarantine with Disclaimers. Holding unverified claims back completely creates dangerous information voids where rumors circulate unopposed. TruthLens displays them with prominent warning disclaimers while withholding viral sharing mechanisms.
- **DP3 · Editing Policy**: Immutable Versioning (`v1` → `v2`) with real-time risk flag re-computation and audit logging.

---

## 🚀 Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Start Development Server
```bash
npm run dev
```

### 3. Build for Production
```bash
npm run build
```

### 4. Preview Production Build
```bash
npm run preview
```

---

## 🛠️ Tech Stack
- **Framework**: React 19 + TypeScript + Vite
- **Styling**: Tailwind CSS
- **Icons**: Lucide React
- **Storage**: LocalStorage Persistence
