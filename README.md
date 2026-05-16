# atomquest-nexagoals
AtomQuest Hackathon
# NexaGoals

> **AtomQuest Hackathon 1.0** — Goal Setting & Tracking Portal

**Live demo → [amogh2222.github.io/atomquest-nexagoals](https://amogh2222.github.io/atomquest-nexagoals/)**

---

## Overview

NexaGoals is a fully functional, browser-based goal management portal built for the AtomQuest Hackathon 1.0 problem statement. It handles the complete performance cycle — goal setting, manager approval, quarterly check-ins, and weighted scoring — across three user roles with zero setup required.

---

## Quick start

```
Open index.html in any browser. No install. No server. No build step.
```

### Demo accounts

| Role | Name | How to log in |
|------|------|---------------|
| Employee | Rahul Verma | Select Employee → click name |
| Employee | Sneha Iyer | Select Employee → click name |
| Employee | Dev Anand | Select Employee → click name |
| Manager | Meena Pillai | Select Manager → click name |
| Manager | Ajay Nambiar | Select Manager → click name |
| Admin / HR | Prachi Sood | Select Admin → click name |

---

## Features

### Core (per BRD)
| # | Feature | Status |
|---|---------|--------|
| 1 | Goal creation — thrust area, UoM, target, unit, weightage | ✅ |
| 2 | Weightage validation — exactly 100%, min 10%, max 8 goals | ✅ |
| 3 | Manager L1 approval — approve / edit inline / return | ✅ |
| 4 | Goal locking after approval with audit trail | ✅ |
| 5 | Shared goals — manager pushes KPI, recipients adjust weightage only | ✅ |
| 6 | Quarterly achievement logging — actual vs target | ✅ |
| 7 | Goal status — Not Started / On Track / Completed | ✅ |
| 8 | Manager check-in module with structured comments | ✅ |
| 9 | Auto-scoring engine across all 6 UoM types | ✅ |
| 10 | Weighted overall score per employee | ✅ |
| 11 | Cycle management — name, status, check-in windows | ✅ |
| 12 | Org hierarchy view | ✅ |
| 13 | Full audit trail — user, date, action, note | ✅ |
| 14 | CSV achievement export | ✅ |

### Novelty (beyond BRD)
| Feature | What it does |
|---------|-------------|
| 🔥 Performance heatmap | Admin sees all employees colour-coded by score band — green / yellow / red. Click any cell for instant detail. |
| 🤖 AI coaching insights | Flags at-risk goals, recommends recovery actions, projects year-end score range per employee. |
| 📊 Live weightage visualiser | Colour bar updates in real time as goals are added — turns red above 100%, green at exactly 100%. |
| 🏅 Score band labels | Scores auto-classified as Excellent / Good / Moderate / At Risk across all views. |

---

## Scoring engine

| UoM type | Formula |
|----------|---------|
| Numeric – higher better | `min(100, actual ÷ target × 100)` |
| Numeric – lower better | `min(100, target ÷ actual × 100)` |
| Percentage – higher better | `min(100, actual ÷ target × 100)` |
| Percentage – lower better | `min(100, target ÷ actual × 100)` |
| Timeline (date) | `actual ≤ target → 100%` · else −4% per day late |
| Zero-target | `actual = 0 → 100%` · else `0%` |

```
Overall score = Σ(goal score × weightage) ÷ Σ(weightage)
```

---

## Architecture

```
Browser
└── index.html  (single self-contained file)
      ├── HTML / CSS   — three role dashboards
      ├── JavaScript   — state, scoring, validation, audit
      └── In-memory    — users, goals, check-ins
```

**Production path (if deployed)**

| Layer | Technology | Cost |
|-------|-----------|------|
| Frontend | React → Vercel | Free tier |
| Backend | Express → Railway | Free tier |
| Database | PostgreSQL → Supabase | Free tier |
| Auth | Azure AD Entra ID | Existing tenant |
| Notifications | SendGrid + MS Teams webhooks | Free tier |

---

## Repo structure

```
atomquest-nexagoals/
├── index.html    — complete portal
└── README.md     — this file
```

---

<div align="center">

Built for **AtomQuest Hackathon 1.0** · May 2026

</div>
