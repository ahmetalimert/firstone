# Project context

This repository is a personal knowledge base for **refreshing geotechnical engineering knowledge** for job applications (foundations, deep excavations, cut-and-cover, tunnels, site investigation, soil behaviour, rock mechanics).

## Files
- `geotech/SOURCES.md` — **the running source library. It is meant to accumulate over time.**
- `geotech/STUDY_GUIDE.md` — quick study guide, practice questions, newer topics, case histories.

## Conventions for adding sources (follow every session)
1. **Add sources; don't remove them.** Put each new source in the right numbered section of `geotech/SOURCES.md`. If a source is superseded (for example a new GEC edition), keep the row and mark it "superseded by …".
2. Each row has: linked title (with edition, year, and report number), **Access** (🟢 free / 🟡 free with registration or a paid certificate / 🔴 paid), short notes, and **Status** (`✔ (YYYY-MM)` if you checked it online, `◻` if added from memory).
3. Prefer primary or official sources: FHWA, USACE, ITA-AITES, ISSMGE, ISRM, CIRIA, BTS, CEN/BSI/ASTM, university OCW, peer-reviewed papers. Avoid random PDF mirror sites unless no official copy exists (and say so).
4. Add a dated line to the **Changelog** at the bottom of `SOURCES.md` for every update.
5. When a new topic is studied, extend `STUDY_GUIDE.md` (refresh points, key numbers, practice questions) and link it to its sources.

## Study app
- `geotech/app/geotech-ground-truth.html` is the interactive study app. Its data lives in the inline `SRC`, `M` (modules → lessons) and `THREADS` arrays.
- When adding a lesson: give it a unique `id` ("module-n"), `links` to existing ids, `src` keys present in `SRC`, and at least one quiz item. Then republish the same artifact so its link stays the same.
