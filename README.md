# Notewright

<p>
  <img alt="Agent Plugins 1.0" src="https://img.shields.io/badge/Agent%20Plugins-1.0-2f6feb">
  <img alt="version 1.0.0" src="https://img.shields.io/badge/version-1.0.0-3fb950">
  <img alt="4 skills" src="https://img.shields.io/badge/skills-4-8957e5">
  <img alt="3 commands" src="https://img.shields.io/badge/commands-3-d29922">
</p>

English | [简体中文](README.zh-CN.md)

A full-cycle note plugin organized around the Agent Plugins 1.0 layout. Four skills cover extraction, organization, structure, and diagramming; three commands handle translation, formal rewriting, and image links.

## Components

### Skills

| Skill | Purpose | Entry point |
|---|---|---|
| ordinote-organizer | General note organization: extraction, denoising, standardization, merging, enrichment, export | `skills/ordinote-organizer/SKILL.md` |
| resenote-organizer | Lab notes and literature reading: protocols, skimming, close reading, literature enrichment, experiment preparation | `skills/resenote-organizer/SKILL.md` |
| textura-nexus | Directory structure cleanup, deduplication, AI long-text compression | `skills/textura-nexus/SKILL.md` |
| ars-graphica | Text descriptions or images to standalone static SVG | `skills/ars-graphica/SKILL.md` |

### Commands

| Command | Purpose | File |
|---|---|---|
| img-format | Normalize image and SVG links, rename files, unify markup as `<img>` | `commands/img-format.md` |
| note-trans | In-place translation with English terminology annotations | `commands/note-trans.md` |
| note-written | In-place formal rewriting, removing verbal tics | `commands/note-written.md` |

Agent Plugins 1.0 defines only two component types, skills and MCP servers; `commands/` does not belong to the common layer. Clients that support commands can use these three directly; other clients load only the four skills.

## Layout

```text
Notewright/
├── plugin.json
├── skills/
│   ├── ordinote-organizer/
│   │   ├── SKILL.md
│   │   ├── references/
│   │   └── scripts/
│   ├── resenote-organizer/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── textura-nexus/
│   │   ├── SKILL.md
│   │   └── references/
│   └── ars-graphica/
│       ├── SKILL.md
│       ├── references/
│       └── assets/examples/
├── commands/
├── README.md
├── README.zh-CN.md
├── CHANGELOG.md
└── .gitignore
```

## Usage

Clients that support Agent Plugins 1.0 can load this directory as a plugin: read `plugin.json` at the root, scan the direct subdirectories of `skills/`, and treat every directory containing `SKILL.md` as a skill.

## Dependencies

- `extract_pdf_pptx.py`: PyMuPDF, python-pptx
- `extract_docx.py`: python-docx
- `md2pdf.py`: markdown-it-py, Markdown Preview Enhanced extension, Chrome or Edge
- `md2docx.py`: python-docx, markdown-it-py
- `mineru_api.py`: standard library only; requires the `MINERU_API_TOKEN` environment variable
