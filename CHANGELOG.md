# Changelog

## v1.2.0 (2026-06-29)

### Added
- **EMF image insertion support**: Complete solution for inserting EMF (Enhanced Metafile) vector images into docx documents
- **Image anti-occlusion**: Picture paragraphs use SINGLE line spacing instead of EXACTLY to prevent text/image overlapping
- **Content type registration**: Auto-registers `image/x-emf` content type in `[Content_Types].xml` for EMF support
- **Image section**: New documentation section covering image insertion patterns (inline, paragraph-level, table cell)
- **Trigger keywords**: Added 6 new trigger keywords for image-related tasks

### Changed
- Verification checklist expanded with 2 new image-related checks
- Skill description updated to reflect image insertion capabilities

## v1.1.0 (2026-06-29)

### Added
- **Times New Roman font rule**: All English text and numbers (including formulas) now use Times New Roman, while Chinese text uses SimHei/SimSun as specified
- **Bilingual font function**: `set_font(run, cn_font, en_font, ...)` replaces old `set_cn_font`, supporting separate Chinese and Western font settings
- **Font rule documentation**: New core font rule section explaining the Chinese/English font mixing approach
- Verification checklist updated with Times New Roman checks

### Changed
- `set_cn_font` renamed to `set_font` with `cn_font` and `en_font` parameters
- All code snippets updated to set `w:ascii` and `w:hAnsi` to Times New Roman
- Font table now shows separate columns for Chinese font and English/number font
- Abstract sections explicitly marked as exceptions to the Times New Roman rule

## v1.0.0 (2026-06-29)

### Added
- Initial release: complete Fuzhou University thesis formatting skill
- Full implementation of the writing specification (福大教〔2019〕37号)
- Page setup: A4, exact margins (top 25mm, bottom 20mm, left 25mm, right 20mm)
- Font mapping for all heading levels (SimHei/SimSun)
- Dual heading hierarchy (science/engineering + humanities/management)
- Odd/even page headers with alternating content
- GB/T 7714-2015 compliant reference format
- Bilingual README (EN + CN)
- Python-docx code templates for all formatting elements
- Format verification checklist
