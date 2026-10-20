# Emotion Ledger · Where Your Money Actually Went (Emotionally)

> 🌐 中文版：[README.md](./README.md)

> *"I know I didn't overspend — but the money is just gone."*

A **minimalist tool for people who always give up on budgeting.** Monument-Valley-style calm visuals, gentle animation, soft sound. It never asks you to log every single transaction — once a month you do one small thing: **tag a few large expenses with an emotion**, and at month-end it tells you: your money was taken by *which* emotion.

- Live site (GitHub Pages): https://dongqianqi-888.github.io/emotion-ledger/
- Style reference: *Monument Valley* — minimal, low-saturation, serene; slowly floating geometry, soft entrance animations, and procedurally generated cue sounds (no audio files needed).

---

## The Problem It Solves

| Pain point | How this tool responds |
| --- | --- |
| Budgeting apps demand logging every purchase; you quit after 3 days | Tag only **5–10 large expenses** per month — done in two minutes |
| Bank statements show "Dining -38" but never "why" | Statements are by **category**; people live by **motive** — this tool adds the motive layer |
| What spirals out of control is small, frequent emotional spending | Focus on large non-fixed spending, and connect emotion to its **trigger scenario** |
| Existing tools hand you a pie chart and leave you with guilt | It delivers not a report, but one **actionable step** and one **kind word** |

---

## The 3-Step Flow

**Step 1 · Import & Overview**
- Upload / paste your statement (CSV or plain text); it auto-detects "date / amount / description" and categorizes.
- Or just walk the built-in demo flow to experience the full path.
- You get a "spending by category" chart first — see roughly where the money went.

**Step 2 · Tag the Emotion**
- First check off fixed expenses like **housing / transport / communication / medical** (editable, add/remove).
- The app auto-picks the **Top 10 large non-fixed expenses**; for each you pick one emotion + an intensity score of 1–5.
- Manual entries are supported too.

**Step 3 · Now You See**
- An "emotion tower" card: where your money flowed by share of amount (e.g. Reward 32% / Anxiety 28% / Social 21%).
- Plus a **scenario insight** (e.g. "Your anxiety spending clusters on Wednesday evenings and Sundays, mostly right after overtime").
- One **word to yourself** + one **tiny habit to try**.

---

## The Emotion List (8)

| Emotion | Meaning | Theme color |
| --- | --- | --- |
| 犒赏 Reward | Rewarding the hard-working self | warm gold |
| 焦虑 Anxiety | Paying for an emotion | purple |
| 社交 Social | Favor & connection | pink |
| 孤独 Lonely | Buying temporary company | blue |
| 冲动 Impulse | Didn't get to think | terracotta |
| 疲惫 Fatigue | Recharging via spending | sage green |
| 快乐 Joy | Pure happiness | bright yellow |
| 解压 Stress-relief | The load was too heavy | lotus pink |

> To add/remove emotions or change theme colors, edit the `EMOTIONS` array in `index.html`.

---

## Privacy

- **All data lives only in your own browser (localStorage). Nothing is uploaded to any server.**
- No account, no backend, no tracking.
- Clearing your browser data removes everything permanently.

---

## How to Import Your Statement

The tool auto-recognizes common Chinese/English column names (日期 / time / 描述·备注·摘要·商户 / 金额·amount, etc.). Easiest approach: your exported CSV should contain at least these three kinds of info —

```csv
日期,描述,金额
2026-10-01,Starbucks Latte,38.00
2026-10-02,JD-Mechanical Keyboard,299.00
2026-10-03,Metro Top-up,50.00
```

- Quoted fields with embedded commas are supported (e.g. `"Taobao, Sweater",299`).
- Both expenses (positive) and income (negative) are recognized; fixed expenses (housing/transport, etc.) are auto-categorized and can be checked off in Step 2.
- Bank headers vary widely — if parsing is off, paste a sample to me and I'll harden the rules.

---

## Open Locally

The whole tool is **a single `index.html` file** (styles, scripts, and sounds all inlined).

- Just **double-click** to open in a browser — works **offline** too.
- Send this one file to a friend; they double-click to run it, with data stored separately in each of your browsers.

---

## Technical Architecture

- **Pure front-end, single file**: HTML + inlined CSS + inlined JS. Zero dependencies, zero build.
- **Audio**: synthesized live via the Web Audio API —
  - a calm, continuous background music (two soft pads + long legato arpeggio notes);
  - emotion intensity 1–5 maps to a pentatonic scale from low to high, so a stronger feeling sounds brighter;
  - each emotion has its own root note, making the feedback feel more "mind-reading".
- **Data**: persisted in localStorage.
- The `♪` at top-right is the master switch — turning it off stops both music and cues.

---

## Deployment (GitHub Pages)

The repo already has GitHub Pages enabled, published from the root of the `main` branch. To update later: after editing `index.html`, push to `main` and Pages rebuilds automatically (live in ~30–60 seconds).

---

## Possible Extensions (TBD)

- Adapt to real statement column names (tune the parser per your bank / payment platform)
- Export the "emotion tower" result as a PNG for easy sharing
- Multi-currency / historical month review (RM supported for Malaysia residents)
- Finalize product naming and brand color

---

© 2026 董芊岐（Donna）. Open-sourced under the MIT License, see [LICENSE](./LICENSE).
