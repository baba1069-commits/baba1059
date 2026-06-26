# UBC Faculty Literature Vault

An Obsidian-friendly, linked-note version of the UBC faculty research material. This vault is a **reusable structure** — it does not replace the dated Layer 2/3/4 files (`2026-06-25_Faculty_Research_Map.md`, `Faculty_Literature_Notes/`); it re-expresses the same verified facts as linked notes so the relationships between professors, publications, themes, and Jiecheng's internship work are visible in Obsidian's Graph View.

## Folder structure

```
Faculty_Literature_Vault/
├── README.md                  — this file
├── 00_Faculty_Index.md        — master list of professors, linked, with status
├── 01_Professors/             — one note per professor
├── 02_Publications/           — one note per verified publication
├── 03_Themes/                 — research themes + Jiecheng's project nodes
├── 04_Graph_Data/             — CSV edge lists (for tools other than Obsidian's native graph)
└── 99_Needs_Verification/     — anything that could not be confirmed from an official/primary source
```

## How to use with Obsidian

1. Clone or sync this GitHub repo to your computer.
2. Open Obsidian → "Open folder as vault" → select this repo (or this `Faculty_Literature_Vault/` folder).
3. Open Graph View. Because every note uses `[[wiki links]]`, Obsidian draws the relationships automatically — e.g. `Harper_B_Keenan → 2017_Keenan_Unscripting_Curriculum → LGBTQ_Family_Resources → Parkdale_Parent_Resources_Project`.

## Collection policy (do not over-collect)

This vault is built in stages, not all at once:

1. **Stage 1 (current pass):** 5–8 representative works per professor, just enough to cover the theme. This pass has far fewer than that for most professors, because most publication titles beyond what's already verified in `2026-06-25_Faculty_Research_Map.md` could not be confirmed from an accessible primary source — see `99_Needs_Verification/`.
2. **Stage 2 (later, high-match professors only):** a full 5–10 year publication list — planned for Keenan, Hare, and Ford specifically, once Jiecheng is closer to choosing UBC as a target school. Not done in this pass.
3. **Stage 3 (application season):** narrow down to the 3–5 academic concepts actually worth citing in a statement of purpose — not the full reading list.

## Evidence rules (carried over from the rest of this repo)

- No invented publications. If a title, journal, or publication could not be verified from an official or primary academic source, it goes in `99_Needs_Verification/`, not in `01_Professors/` or `02_Publications/`.
- No professor is described as "accepting students" unless their official UBC page states it. Every professor note's accepting-students field is "Needs Verification" unless a primary source says otherwise.
- This vault inherits the privacy/sourcing rules in the repo-root `00_READ_FIRST_GitHub_Whiteboard_Boundary.md`.

## Source of this first pass

Converted from `../2026-06-25_Faculty_Research_Map.md` and `../Faculty_Literature_Notes/2026-06-25_Keenan_Literature_Note.md` (both already evidence-checked). No new research was performed to build this vault — it is a re-structuring of already-verified material into linked notes.
