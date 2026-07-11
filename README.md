# Bloom — Math Garden

A small, no-build, single-file math app for early learners (roughly ages 4–8), built around one idea: **you grow a garden by solving problems.**

## Philosophy

- **Concrete before abstract.** Every concept is taught with something you can see and tap — apples in a basket, dots on a dice face, ten-frames, number lines, plates being shared — before it's ever reduced to a bare equation.
- **Explore, then practice.** Each skill opens with a short narrated, animated walkthrough that shows *why* the answer is what it is, before the child is ever asked to answer on their own. Nobody is quizzed on something they haven't been shown first.
- **Mistakes are gentle.** A wrong answer gets a soft "let's look again," and where it helps, the objects re-count themselves on screen. The tone throughout — from the companion ladybug **Dot** to every line of encouragement — is playful and forgiving, never punitive.
- **Mastery over scores.** Progress per skill is tracked as Seed 🌱 → Sprout 🌿 → Bloom 🌸, based on how much a child gets right in a session, not a single pass/fail grade.
- **Narrated, not just written.** Every stage of every lesson is spoken aloud (Web Speech API, tuned to prefer natural-sounding voices) — this is built for kids who can't yet, or would rather not, read.
- **One path, four phases.** Skills unlock in order of conceptual dependency:

| Phase | Skills |
|---|---|
| 🟢 Foundations | Counting · Subitizing · Compare · Ordering |
| 🔵 Core | Make & Break · Addition · Subtraction |
| 🟡 Supporting | Skip Counting · Place Value |
| 🟣 Advanced | Multiply · Divide |

## How it's built

Everything lives in a single `index.html` — no build step, no framework, no dependencies beyond two Google Fonts. Every visual (apples, ten-frames, arrays, sharing plates, number lines) is hand-drawn inline SVG from small JS template functions, so the app loads instantly and works offline once cached.

State (XP, flowers, stickers, skill levels, chosen avatar/voice) is saved to `localStorage` through one small persistence seam (`Store`), kept deliberately swappable for something like `@capacitor/preferences` if this ever becomes a packaged mobile app.

**Run it:** open `index.html` in a browser, or serve the folder with any static file server.

## Roadmap: Fractions

The natural next step after **Divide** ("fair shares") is **Fractions** — naming the share instead of just finding it.

> 🍕 **Fractions — Equal shares**
> *A fraction names one fair share of a whole that's been cut into equal parts — like 1 slice out of 4 equal slices is one-fourth.*
> 🗣️ "When we cut something into equal parts and talk about just one part, that's a fraction!"

It fits as the next **Advanced**-phase skill, right after Divide, because it reuses the same "fair sharing" intuition kids just built — the difference is naming the piece (½, ⅓, ¼) instead of counting how many each friend gets. Planned shape, following the existing lesson pattern:

- **Explore** — cut a pizza or candy bar into equal parts, tap one slice, hear "This is one out of four equal parts — one-fourth."
- **Practice** — "Which picture shows one-half?" style multiple choice, reusing the plates/groups visuals already built for Divide.
- Unlocks its own phase badge and sticker, same as every other skill.
