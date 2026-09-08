# Foreman Medical Copilot

AI copilot for medical students following the **Foreman method** — generates daily study briefs prioritized by USMLE-relevant ROI, syncs parallel multidisciplinary pacing across subjects, and enforces active-recall verification with zero-topic-skipping curriculum coverage.

Built as a [Claude Skill](https://docs.claude.com) (`SKILL.md`) that turns Claude into an operational study strategist — not a tutor. It decides *what* to study today, *how much time* to spend on it, and *verifies* it was actually learned.

---

## What it does

- **Daily study briefs** ranked by time-ROI: hours are allocated proportionally by topic weight/complexity, never split evenly.
- **Parallel multidisciplinary pacing**: 2–3 subject blocks per day, synchronized to the active curriculum cycle — not studied subject-by-subject in isolation.
- **100% coverage mandate**: no topic is ever skipped or deleted. Time pressure changes hours allocated per topic, never which topics get studied.
- **Weekly burn-down tracking**: compares planned vs. actual hours invested and flags drift ("you're X hours behind schedule") instead of hiding it.
- **Active-recall verification**: closes every study block with a Feynman-style explanation check and a clinical vignette — no block is marked `dominado` (mastered) on hours alone.
- **Cross-topic integration questions**: once 2+ related topics are mastered, the brief forces a question connecting them.
- **Anki/AnKing workflow support**: generates a ready-to-paste prompt to locate the exact tag deck for the day's topic instead of hardcoding tags that go stale.
- **Context memory logging**: every session (videos watched, articles read, QBank results, weak points) gets logged in a dated format and reviewed against the last 14 days when building the next brief.
- **Dr. House tone**: the daily opener is written in English, in character — sharp, clinically grounded, zero artificial motivation.

## Daily brief structure

Every brief follows the same 12-section order:

1. House-style opener (English)
2. Countdown & burn-down status
3. Calendar availability
4. Weighted daily prescription (2–3 parallel blocks)
5. Reference resources & QBank strategy
6. Anki tag-search prompt
7. Step-by-step execution protocol for the session
8. Mnemonic / clinical analogy + compression equation
9. Feynman mechanism check + House-style clinical question + English term of the day
10. Integration question (cross-topic)
11. Block-by-block reporting & Feynman verification
12. Self-verification checklist

## Requirements (external, not included in this repo)

This skill assumes — but does **not** bundle — the following data sources:

- A **master topic-tracking sheet** (subject, topic, USMLE weight, estimated hours, deadline, status, hours invested).
- A **curriculum schedule source** (official weekly syllabus) to sequence new content pedagogically.
- A **context memory document** (cloud-based session log) for the 14-day lookback and pattern detection.
- Calendar/email access as the source of truth for available study windows.

None of these are personal data and none are included here — you connect your own.

## Known gaps / limitations

- Resource fallback map is generic by default; some subjects (e.g. those without a standardized high-yield pathway) need a manually defined resource before the skill can prescribe them correctly.
- Without a curriculum schedule source connected, the skill falls back to sheet row order with no pedagogical sequencing guarantee.
- Without a connected context memory document, the 14-day lookback and repeated-pattern detection sections cannot function.

## Usage

Copy `SKILL.md` into your Claude Skills directory (or upload it via Claude.ai's skill upload flow). Once installed, ask Claude for your daily study brief, report a completed block, or ask it to log a study session — the skill triggers automatically.

## Attribution

Methodology named after the "Foreman method," combining active-recall protocols, progressive summarization, and ROI-weighted scheduling for board-exam-oriented medical study.

## License

No license — personal-use project, not intended for redistribution.
