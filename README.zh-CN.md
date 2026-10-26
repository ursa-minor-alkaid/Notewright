<p align="center">
  <img src="muses-helicon@3x.png" alt="Notewright" width="100%">
</p>

<h1 align="center">Notewright</h1>

<p align="center">
  <img alt="Agent Plugins 1.0" src="https://img.shields.io/badge/Agent%20Plugins-1.0-2f6feb">
  <img alt="版本 1.0.0" src="https://img.shields.io/badge/version-1.0.0-3fb950">
  <img alt="4 个技能" src="https://img.shields.io/badge/skills-4-8957e5">
  <img alt="3 条命令" src="https://img.shields.io/badge/commands-3-d29922">
</p>

<p align="center"><a href="README.md">English</a> | 简体中文</p>

笔记全流程插件，按 Agent Plugins 1.0 的通用目录组织。四个技能覆盖提取、整理、结构、绘图，三条命令处理翻译、书面化与图片链接。

## 组件

### 技能

| 技能 | 用途 | 入口 |
|---|---|---|
| ordinote-organizer | 通用笔记整理：提取、去噪、规范化、添加、补充、导出 | `skills/ordinote-organizer/SKILL.md` |
| resenote-organizer | 实验笔记与文献阅读：protocol、速读、精读、文献补充、预习 | `skills/resenote-organizer/SKILL.md` |
| textura-nexus | 目录结构整理、去重、AI 长文压缩 | `skills/textura-nexus/SKILL.md` |
| ars-graphica | 文字描述或图片转独立静态 SVG | `skills/ars-graphica/SKILL.md` |

### 命令

| 命令 | 用途 | 文件 |
|---|---|---|
| img-format | 整理图片与 SVG 链接，重命名并统一为 `<img>` | `commands/img-format.md` |
| note-trans | 就地翻译，并标注术语英文 | `commands/note-trans.md` |
| note-written | 就地书面化，去除口癖 | `commands/note-written.md` |

Agent Plugins 1.0 只定义技能与 MCP 两类组件，`commands/` 不属于通用层。支持命令的客户端可直接使用这三条命令，其他客户端只加载四个技能。

## 目录

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

## 使用

支持 Agent Plugins 1.0 的客户端可直接将本目录作为插件载入：读取根目录 `plugin.json`，扫描 `skills/` 的直接子目录，每个含 `SKILL.md` 的目录视为一个技能。

## 依赖

- `extract_pdf_pptx.py`：PyMuPDF、python-pptx
- `extract_docx.py`：python-docx
- `md2pdf.py`：markdown-it-py、Markdown Preview Enhanced 扩展、Chrome 或 Edge
- `md2docx.py`：python-docx、markdown-it-py
- `mineru_api.py`：仅标准库，需要环境变量 `MINERU_API_TOKEN`
