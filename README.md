# STOTT PILATES® Certification Study App

A fully self-contained study app to prepare for the **STOTT PILATES Level 1 Reformer Certification Exam** — hosted at a permanent URL via Vercel.

## 🌐 Live App

> Once deployed, your permanent URL will be:
> `https://stott-pilates-study-app.vercel.app` (or your custom domain)

---

## 🚀 Deploy to Vercel (Step-by-Step)

### Step 1 — Push to GitHub

```bash
# Clone or initialize the repo
git init
git add .
git commit -m "Initial commit — STOTT Pilates study app"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/stott-pilates-study-app.git
git push -u origin main
```

### Step 2 — Connect to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in (use your GitHub account)
2. Click **"Add New Project"**
3. Click **"Import"** next to your `stott-pilates-study-app` repository
4. Leave all settings as default — Vercel will auto-detect the static site
5. Click **"Deploy"**
6. ✅ Your app is live at `https://your-project-name.vercel.app`

### Step 3 — Auto-deploy on every update

Every time you push a change to GitHub, Vercel automatically re-deploys. No manual steps needed.

---

## 📚 App Features

| Tab | Description |
|-----|-------------|
| **Flashcards** | 30+ cards — 5 Principles, Anatomy, Muscles, Exam, Reformer |
| **Quiz** | Multiple choice with instant feedback & explanations |
| **🫀 Body Map** | Clickable SVG front/back/side body — click to see muscle details |
| **👁 Visual Quiz** | Highlighted region on body — identify like the real written exam |
| **Study Guide** | 5 Principles, pelvic positions, scapular movements, contraction types |
| **Anatomy Table** | Full STOTT Muscular References — filterable by region |
| **Exam Info** | Scores, time limits, practical evaluation criteria |
| **📋 Postural Analysis** | Side/Front/Back with 4-question framework for every region |
| **💪 Programming** | Side/Front/Back — every checklist finding mapped to exercises |
| **AI Tutor** | Ask any question — powered by Claude (Anthropic API) |

---

## 📁 File Structure

```
stott-pilates-study-app/
├── index.html        ← entire app (single file)
├── vercel.json       ← Vercel deployment config
└── README.md         ← this file
```

---

## 🔑 AI Tutor — API Note

The AI Tutor tab uses the Anthropic Claude API. When running inside **Claude.ai** the key is handled automatically.

If you want the AI Tutor to work on your hosted Vercel deployment, you have two options:

**Option A — Simple (client-side key, not recommended for public sites):**
Find this section in `index.html` and add your key:
```javascript
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'YOUR_ANTHROPIC_API_KEY_HERE',
  'anthropic-version': '2023-06-01',
  'anthropic-dangerous-direct-browser-access': 'true',
},
```

**Option B — Secure (recommended for public hosting):**
Build a small proxy API route. With Vercel you can add an `/api/chat.js` serverless function that holds the key server-side and proxies requests to Anthropic.

> ⚠️ **Never commit an API key to a public GitHub repo.** Use Vercel Environment Variables instead:
> Vercel Dashboard → Your Project → Settings → Environment Variables → Add `ANTHROPIC_API_KEY`

All other tabs (flashcards, quizzes, body map, postural analysis, programming) work **fully offline** — no API key needed.

---

## 🎯 Exam Quick Reference

| Requirement | Detail |
|-------------|--------|
| Passing score | 80% average + 75% min per component |
| Exam window | Within 6 months of last course |
| Written + Practical | Within 7 days of each other |
| Reformer Level 1 | 6 Essential + 4 Intermediate, 40–50 min |
| Practical opening | 5–10 min client history + postural analysis |
| 5 Basic Principles | Breathing, Pelvic Placement, Rib Cage, Scapular, Head & Cervical |

---

## 📋 Content Sources

- STOTT PILATES® Instructor Trainer Handbook (Merrithew, July 2020)
- STOTT PILATES® Muscular References Sheet
- Postural Analysis Guide Checklist (Merrithew, 2025)
- Bony Landmark Reference Guide (Merrithew, 2025)

> STOTT PILATES® is a registered trademark of Merrithew International Inc. This is an independent study tool, not affiliated with or endorsed by Merrithew.

---

Good luck on your certification! 💪
