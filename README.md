# cs-learning-notes
My personal knowledge base for computer science, covering core subjects, interview preparation, and hands-on projects.

> Notes and project files are written in Chinese; this index is in English.

## Notes

- [Day 01](notes/day01-学习笔记.md) — the note template: what I studied, what blocked me, how I got past it.

## Projects

- [hs-title-cls](projects/hs-title-cls.md) — Chinese product-title text classification demo, fine-tuning `bert-base-chinese` across four one-way layers: data processing → training → inference → HTTP API. The dataset is randomly generated rather than real, so its accuracy figures are not meaningful — see the project file before reading anything into them. Code: [github.com/cresh0011/hs-title-cls](https://github.com/cresh0011/hs-title-cls)

## How this repo is organised

Three things live here, and nothing else:

```
.
├── README.md      # this index — the only file that sits at the root
├── notes/         # daily study notes
└── projects/      # one file per project
```

**`notes/`** — one file per day, named `dayNN-<topic>.md` with a two-digit day number (`day01`, `day02`, …). Keep one day per file rather than merging several days together; the timeline is the whole point. If this ever grows past ~50 files, split it by month into `notes/2026-09/`.

**`projects/`** — one file per project, named after its repository (`hs-title-cls.md`). **Source code does not live in this repo** — every project keeps its own repository. These files are for what a repo README can't say: what I actually built, what tripped me up, and what I'd do differently next time.

A new project file starts from this shape:

```
# <project-name>

- **Repo**: <url>
- **Local path**: <path>
- **Status**: in progress / done / abandoned

## What it is

## Gotchas

## Next
```
