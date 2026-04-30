# 📚 AP Human Geography Study Hub

**Winslow's custom AP exam prep app** — built in one evening, deployed on Cloudflare Pages.

🚀 **Live:** [winslow-study.pages.dev](https://winslow-study.pages.dev) | [winslow.fosterlabs.org](https://winslow.fosterlabs.org)

---

## What This Is

A mobile-first PWA for AP Human Geography exam prep, sourced from Rubenstein's *The Cultural Landscape* (11th Edition, AP Edition). Built for a 9th grader with 6 days until the AP exam.

## Features

| Feature | Description |
|---------|-------------|
| 📖 **Study Guide** | All 14 chapters with key concepts, models, definitions, and textbook examples |
| 🃏 **Flashcards** | 140+ interactive flip cards with swipe gestures and mastery tracking |
| 📝 **Quizzes** | 100+ multiple choice questions with instant grading, explanations, and score rings |
| 🔍 **Glossary** | Searchable database of all key terms across all chapters |
| 📊 **Progress** | Tracks chapters read, cards mastered, quiz scores (localStorage) |
| ⏱️ **Countdown** | Days until exam (May 5, 2026) |
| 🔥 **Streaks** | Daily study streak tracking |
| 📱 **PWA** | Installable to home screen, works offline via service worker |
| 🌙 **Dark Mode** | Default dark theme, easy on the eyes |

## Interaction

- **Tap** flashcards to flip
- **Swipe right** = "Got it" (mastered)
- **Swipe left** = "Again" (needs review)
- **Haptic feedback** on correct/incorrect quiz answers
- **Confetti** on quiz scores ≥80% and completing a flashcard deck

## Tech Stack

- **Zero dependencies** — vanilla HTML/CSS/JS, no frameworks
- **~100KB** single-file app (index.html)
- **Cloudflare Pages** for hosting
- **Service Worker** for offline caching
- **localStorage** for progress persistence

## Chapter Coverage (Rubenstein 11th Ed)

| # | Chapter | Unit |
|---|---------|------|
| 1 | Basic Concepts | Thinking Geographically |
| 2 | Population | Population & Migration |
| 3 | Migration | Population & Migration |
| 4 | Folk & Popular Culture | Cultural Patterns |
| 5 | Language | Cultural Patterns |
| 6 | Religion | Cultural Patterns |
| 7 | Ethnicity | Cultural Patterns |
| 8 | Political Geography | Political Geography |
| 9 | Development | Agriculture & Development |
| 10 | Agriculture | Agriculture & Development |
| 11 | Industry | Industrialization |
| 12 | Services | Cities & Urban Land Use |
| 13 | Urban Patterns | Cities & Urban Land Use |
| 14 | Resource Issues | Cities & Urban Land Use |

## Reference Materials

- `textbook-reference.txt` — Full OCR text of Rubenstein's *The Cultural Landscape* (13th ed, same content structure as 11th ed AP). 89,000 lines. Used as source material for study content.
- `study-guide.md` — Comprehensive markdown study guide covering all 14 chapters.
- `dist/` — Deployable static site (Cloudflare Pages).

## Deployment

```bash
# Deploy to Cloudflare Pages
wrangler pages deploy dist --project-name winslow-study --branch main

# Custom domain
# winslow.fosterlabs.org → CNAME → winslow-study.pages.dev
```

## Adding Content

The app is a single `index.html` file. All data (study content, flashcards, quizzes, glossary) is embedded in JavaScript objects:

- `STUDY_CONTENT` — HTML content per chapter
- `FLASHCARDS` — Array of {term, definition, example} per chapter
- `QUIZZES` — Array of {question, options, answer, explanation} per chapter
- `GLOSSARY` — Auto-built from flashcard data

To add more content, edit the relevant JS object in `index.html` and redeploy.

## Credits

- **Textbook:** James M. Rubenstein, *The Cultural Landscape: An Introduction to Human Geography*, 11th Edition (AP Edition), Pearson 2014
- **Built by:** Scott Foster + Skippy (OpenClaw AI) — April 29, 2026
- **For:** Winslow, with love from Uncle Scott's robot 🤖

---

*"The guy who barely graduated college just built a better study app than Pearson."*
