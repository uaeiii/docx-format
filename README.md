# docx-format — Claude Code Skill

A **Claude Code** skill for automatically generating Word documents formatted according to the **Fuzhou University Undergraduate Graduation Thesis (Project) Writing Specification** (《福州大学本科生毕业设计（论文）撰写规范》, 福大教〔2019〕37号).

## Features

- **Page Setup** — A4 paper with exact margins (top 25mm, bottom 20mm, left 25mm, right 20mm)
- **Font Mapping** — Correct fonts and sizes for all heading levels (SimHei/SimSun for titles/bodies)
- **Heading Hierarchy** — Supports both science/engineering and humanities/management heading styles
- **Line Spacing** — Fixed 20pt line spacing for body text as required
- **Headers & Footers** — Odd/even page headers (thesis title / university name) with page numbers
- **Tables** — No left/right borders, captions above
- **Figures** — Figure numbers below with chapter-based numbering (e.g., 图2-5)
- **Equations** — Centered with right-aligned numbered references
- **References** — GB/T 7714-2015 compliant citation format with examples for all document types
- **Chapter Breaks** — Automatic page breaks between chapters

## How It Works

This skill follows a structured workflow when generating thesis documents:

1. **Collect Info** — Prompts for thesis type, title, author info, section content, and references
2. **Configure Page** — Sets A4 page, margins, headers/footers with alternating odd/even headers
3. **Build Sections** — Generates cover → Chinese abstract → English abstract → TOC → body → references → appendix → acknowledgments
4. **Apply Formatting** — Applies all font, size, spacing, and layout rules from the specification
5. **Verify Formatting** — Checks all formatting requirements against the specification checklist

## File Structure

| File | Description |
|------|-------------|
| `SKILL.md` | Main skill definition with instructions, code templates, and formatting rules |
| `README.md` | This file — English overview |
| `README_CN.md` | Chinese overview |
| `manifest.yaml` | Skill metadata |
| `CHANGELOG.md` | Version history |
| `docs/` | Reference materials |

## Installation

```bash
# Clone or download this repository
git clone https://github.com/uaeiii/docx-format.git

# Copy the skill directory to Claude Code's skills folder
cp -r docx-format ~/.claude/skills/
```

Or create a symlink (recommended for easy updates):

```bash
ln -s "$(pwd)/docx-format" ~/.claude/skills/docx-format
```

## Usage

Once installed, the skill activates automatically when you mention:

- Creating or generating a graduation thesis / dissertation
- Formatting a paper for Fuzhou University
- Needing a thesis template
- "毕业设计说明书" or "毕业论文"
- Any reference to the Fuzhou University writing specification

## Specification Reference

The skill implements: **《福州大学本科生毕业设计（论文）撰写规范》（福大教〔2019〕37号）**

Key formatting requirements:
- Paper: A4 (210×297mm)
- Margins: Top 25mm, Bottom 20mm, Left 25mm, Right 20mm
- Body text: SimSun (宋体) 12pt, fixed line spacing 20pt
- Chapter titles: SimHei (黑体) 18pt, space after 30-36pt, centered
- Section 1 titles: SimHei 16pt, space after 18-24pt
- Section 2 titles: SimHei 15pt, space after 12-15pt
- Section 3 titles: SimHei 12pt, space after 6-9pt
- References: GB/T 7714-2015 format

## Requirements

- Python 3.6+
- python-docx library (`pip install python-docx`)
- Claude Code CLI

## License

MIT
