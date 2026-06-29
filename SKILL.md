---
name: docx-format
description: 福州大学本科生毕业设计（论文）撰写规范——按福大教〔2019〕37号格式要求自动生成规范化docx文档，含图片插入防遮挡方案
metadata:
  type: workflow
  domain: document
  triggers-on:
    - 毕业论文 docx
    - 毕业设计 docx
    - 福州大学论文
    - 福大论文格式
    - 论文模板 docx
    - 制作论文
    - 生成论文
    - 毕业论文格式
    - 毕业设计说明书
    - 学位论文
    - 论文排版
    - fzu thesis
    - 福州大学 毕业设计
    - 按规范生成论文
    - 撰写规范
    - 福大教2019
    - 插入图片
    - 添加图片
    - 报告插图
    - 图片嵌入
    - EMF图片
    - 文档插图
---

# 福州大学本科生毕业设计（论文）撰写规范 - FZU Thesis Format

## 概述

本 Skill 依据 **《福州大学本科生毕业设计（论文）撰写规范》（福大教〔2019〕37号）** 文件，自动生成符合学校规范的毕业论文/设计说明书 .docx 文档。

**核心依据文件：** E:\ClaudeWorkSpace\20.福州大学本科生毕业设计（论文）撰写规范.doc

当用户要求制作**毕业论文、毕业设计说明书、学位论文**的 Word 文档时，**必须按本规范中的所有格式要求执行**，包括页面设置、字体字号、标题层次、段落间距、页眉页码、参考文献格式等全部细节。

## 一、页面设置

| 项目 | 要求 |
|------|------|
| 纸张 | A4 (210 x 297 mm) |
| 上边距（天头） | 25 mm |
| 下边距（地脚） | 20 mm |
| 左边距（订口） | 25 mm |
| 右边距（切口） | 20 mm |

## 二、字体字型号对照表

### 字体规则（核心）

> **所有中文字体使用宋体/黑体，同一段落中的英文、数字、公式及标点符号使用 Times New Roman。**（摘要部分除外，摘要按各自指定字体执行。）
>
> 实现方式：在 python-docx 中，设置 run 的 `font.name = 'Times New Roman'`（西文字体），同时设置 `w:eastAsia = '宋体'` 或 `'黑体'`（东亚字体）。Word 会自动将中文匹配到东亚字体，英文/数字匹配到西文字体。

### 正文字体对照

| 用途 | 中文字体 | 英文/数字字体 | 字号 | 行距 | 段后间距 |
|------|---------|-------------|------|------|---------|
| 论文题目（封面） | 黑体 | Times New Roman | 三号（16pt） | - | - |
| 封面信息 | 宋体 | Times New Roman | 四号（14pt） | - | - |
| **大标题（章标题）** | **黑体** | **Times New Roman** | **小二号（18pt）** | **-** | **30-36pt** |
| **一级节标题（1.1）** | **黑体** | **Times New Roman** | **三号（16pt）** | **-** | **18-24pt** |
| **二级节标题（1.1.1）** | **黑体** | **Times New Roman** | **小三号（15pt）** | **-** | **12-15pt** |
| **三级节标题（1.1.1.1）** | **黑体** | **Times New Roman** | **小四号（12pt）** | **-** | **6-9pt** |
| **正文** | **宋体** | **Times New Roman** | **小四号（12pt）** | **20pt固定值** | - |
| 表题与图题 | 宋体 | Times New Roman | 五号（10.5pt） | - | - |
| 附图说明 | 宋体 | Times New Roman | 小五号（9pt） | - | - |
| 参考文献及篇眉 | 宋体 | Times New Roman | 五号（10.5pt） | 17pt固定值，段前加3pt | - |
| **公式** | — | **Times New Roman** | 与上下文一致 | 与上下文一致 | - |

### 中文摘要字体（摘要部分例外，不强制 Times New Roman）

| 用途 | 中文字体 | 英文/数字字体 | 字号 | 行距 |
|------|---------|-------------|------|------|
| 论文题目（居中） | 黑体 | 可随中文 | 小二号（18pt） | 30磅 |
| 中文摘要标题（居中） | 黑体 | 可随中文 | 四号（14pt） | 24磅 |
| 摘要正文（限一页） | 宋体 | 可随中文 | 小四号（12pt） | 20磅 |
| 关键词（3-5个） | 黑体 | 可随中文 | 小四号（12pt） | 16磅 |

### 英文摘要字体（摘要部分例外，按各自指定字体）

| 用途 | 字体 | 字号 | 行距 |
|------|------|------|------|
| ENGLISH TITLE | Arial Black | 小三号（15pt） | 24磅 |
| Abstract标题 | Arial Black | 四号（14pt） | 24磅 |
| 摘要正文 | Times New Roman | 小四号（12pt） | 16磅 |
| Key words | Arial Black | 小四号（12pt） | 16磅 |

## 三、标题层次

### 理工类标题层次

- 第1章 XXXXXX（居中书写，大标题）
- 1.1 XXXXXX（顶格书写，一级节标题）
- 1.1.1 XXXXXX（空两格，二级节标题）
- 1.1.1.1 XXXXXX（空两格，三级节标题）

规则：
- 分级数字编号，两级之间用下角圆点隔开，末尾不加标点
- 各层标题均单独占行书写
- 标题字数一般在15个之内
- **每章应另起一页**
- 正文中分项采用 (1)(2)(3)，小项采用 ①②③

### 文法经管类标题层次

- 一、XXXX（居中书写）
- （一）XXXX（顶格）
- 1．XXXX（空两格）
- （1）XXXX（空两格）

## 四、段落与行间距

- **正文段落和标题一律取固定行间距20pt**
- **参考文献正文：** 固定行距17pt，段前加间距3pt
- **注意：** 不要在一篇参考文献段落的中间换页

### 段后间距

| 标题级别 | 段后间距 |
|---------|---------|
| 大标题（章标题） | 30 ~ 36pt |
| 一级节标题 | 18 ~ 24pt |
| 二级节标题 | 12 ~ 15pt |
| 三级节标题 | 6 ~ 9pt |
| 参考文献标题 | 30 ~ 36pt |

### 章节间间距规则

> **同级/上下级小节之间：** 每个小节（含各级小节）的正文末尾若下一行紧接着下一个小节（不论比它大一级、同级还是小一级），需空一行。
>
> **例外情况：**
> - 若跨页后紧接下一个小节 → 不需要空行
> - 若末尾后无内容（即进入下一章） → 不需要空行
>
> 实现方式：判断小节末尾的下一段是否为另一个标题（通过段落样式或文本特征），若是则在中间插入一个空行段落；但若该标题位于下一页首或属于下一章，则跳过空行插入。

## 五、页眉和页码

### 页眉（从第一章开始，宋体五号居中，下加横线）

| 页面 | 页眉内容 |
|------|---------|
| 奇数页 | 毕业设计（论文）的题目 |
| 偶数页 | 福州大学本科生毕业设计（论文） |

### 页码

| 部分 | 页码格式 |
|------|---------|
| 前置部分（摘要/目录） | 罗马数字 i, ii, iii... |
| 正文（绪论开始） | 阿拉伯数字 1, 2, 3... |
| 位置 | 页面底端，居中书写 |

## 六、图表公式规范

### 图
- 图随文给出，先见文后见图
- 图序及图名置于图的下方，居中排写
- 图序采用分章编号：图2-5
- **图注必须与对应图片在同一页，不允许图注跨页。** 若图片恰好位于页末导致图注跨页，应在图片前加分页符或将图片整体移至下一页。
- **避免大面积留白。** 若图片面积过大导致上一页出现 ≥ 1/3 页面空白，应适当缩小图片尺寸，使图片+图注刚好填满上一页；若缩放后效果不佳，则将图片移至对应文字段落的中部或上方，而非段落后紧接。

### 表
- 表序及表名置于表的上方，居中排写
- **表格不加左右边线**
- 表中参数应标明量和单位的符号
- **表格尽量不跨页。** 若跨页且行数 ≤ 5 行，可在表格前添加适量空行（换行符）将表格推至下一页，利用少量留白避免跨页。若表格过长（如超过一页）等实在无法避免的情况，允许跨页。

### 公式
- 公式居中书写，编号用括号括起写在右边行末
- 编号采用分章编号：公式（5-1）

### 图表与正文间距
- **图、表、公式的上下各空一行**（与正文之间保持一行的间距），但如果刚好遇到跨页（如图表位于页首或页末），则跨页侧不需要空行。

## 七、参考文献格式

按 **GB/T 7714-2015** 执行。作者姓名写到第三位，余者写"，等"或"，et al."。

**文献类型标识：** [M]专著 [C]论文集 [J]期刊 [D]学位论文 [R]报告 [S]标准 [P]专利 [N]报纸

**示例：**
- 图书：[1] 陈登原. 国史旧闻：第1卷[M]. 北京：中华书局，2000：29.
- 期刊：[1] VATSALA A, NOVA R, et al. Elastoplastic model for cemented soils[J]. Journal of Geotechnical and Geoenvironmental Engineering, 2001, 127(8)：679-687.
- 学位论文：[1] 马欢. 人类活动影响下海河典型水循环变化分析[D]. 北京：清华大学，2011：27.
- 会议：[1] GRUBER P, et al. Automatic denoising... [C]//Proceedings of EIS 2004. Portugal：[s.n.], 2004：255-260.
- 专利：[1] 张凯军. 轨道火车紧急安全制动辅助装置：201220158825.2[P]. 2012-04-05.
- 标准：[1] GB/T 3792.4-2009[S]. 北京：中国标准出版社，2010：3.
- 报告：[1] 中华人民共和国国务院新闻办公室. 国防白皮书[R/OL]. (2013-04-16)[2014-06-11].
- 报纸：[1] 丁文祥. 数字革命与竞争国际化[N]. 中国青年报，2000-11-20(15).

## 八、论文结构

一份完整的毕业设计（论文）应包括：封面、中文摘要（500-800字，限一页）、英文摘要（400实词，限一页）、目录、正文（绪论+主体+结论，结论单独一章不加章号）、参考文献、附录、致谢。

### 各类要求

| 类型 | 字数 | 参考文献 |
|------|------|---------|
| 工程设计类 | 8000字以上 | >= 10篇，外文 >= 2篇 |
| 试验研究类 | 8000字以上 | >= 15篇，外文 >= 2篇 |
| 计算机软件类 | 8000字以上 | >= 10篇，外文 >= 2篇 |
| 经管文科类 | 10000字以上 | >= 15篇，外文1-2篇 |

## 九、使用步骤

1. **确认论文类型**
2. **收集信息：** 题目、作者、学院、专业、指导教师、章节内容、参考文献
3. **按规范生成 .docx 文件**
4. **逐一验证格式要求**

### 格式验证清单

- [ ] A4纸，上25mm下20mm左25mm右20mm
- [ ] 正文宋体小四号（12pt），固定行距20pt
- [ ] 大标题黑体小二号（18pt），段后30-36pt，居中
- [ ] 一级节标题黑体三号（16pt），段后18-24pt
- [ ] 二级节标题黑体小三号（15pt），段后12-15pt
- [ ] 三级节标题黑体小四号（12pt），段后6-9pt
- [ ] 正文、标题、图表、页眉中的英文和数字使用 Times New Roman（摘要部分除外）
- [ ] 公式中的英文和数字使用 Times New Roman
- [ ] 每章另起一页
- [ ] 奇偶页页眉（题目/福州大学本科生毕业设计（论文）），宋体五号
- [ ] 页码底端居中（前置罗马数字，正文阿拉伯数字）
- [ ] 参考文献 GB/T 7714-2015 格式
- [ ] 表格不加左右边线
- [ ] 图题在图下方居中，表题在表上方居中
- [ ] 公式居中编号右对齐
- [ ] 图片段落行距为 SINGLE（非 EXACTLY），避免文字遮挡
- [ ] EMF 图片已注册 image/x-emf 内容类型到 [Content_Types].xml
- [ ] 表格尽量不跨页（≤5行小表格用换行符推至下一页，超长表格可跨页）
- [ ] 图注与对应图片在同一页，不跨页
- [ ] 图片未造成大面积留白（≤1/3页空白，否则缩放图片或调整位置）
- [ ] 图表上下各空一行（跨页时跨页侧不空行）
- [ ] 各级小节正文末尾与下一个小节之间空一行（跨页/进下一章时不空行）

## 十、python-docx 代码片段

### 页面设置

```python
from docx import Document
from docx.shared import Cm, Pt
from docx.enum.text import WD_ALIGN_PARAGRAPH, WD_LINE_SPACING
from docx.oxml.ns import qn, nsdecls
from docx.oxml import parse_xml

doc = Document()
section = doc.sections[0]
section.page_width = Cm(21.0)
section.page_height = Cm(29.7)
section.top_margin = Cm(2.5)
section.bottom_margin = Cm(2.0)
section.left_margin = Cm(2.5)
section.right_margin = Cm(2.0)
```

### 设置双语文档字体（中文用宋体/黑体，英文/数字用 Times New Roman）

```python
def set_font(run, cn_font='宋体', en_font='Times New Roman', font_size=Pt(12), bold=False):
    """设置双语字体：中文用 cn_font，英文/数字用 en_font"""
    run.font.name = en_font
    run.font.size = font_size
    run.bold = bold
    rPr = run._r.get_or_add_rPr()
    rFonts = rPr.find(qn('w:rFonts'))
    if rFonts is None:
        rFonts = parse_xml(f'<w:rFonts {nsdecls("w")} />')
        rPr.insert(0, rFonts)
    rFonts.set(qn('w:ascii'), en_font)
    rFonts.set(qn('w:hAnsi'), en_font)
    rFonts.set(qn('w:eastAsia'), cn_font)
```

### 正文段落

```python
para = doc.add_paragraph('正文')
para.paragraph_format.line_spacing_rule = WD_LINE_SPACING.EXACTLY
para.paragraph_format.line_spacing = Pt(20)
para.paragraph_format.first_line_indent = Pt(24)
for run in para.runs:
    set_font(run, cn_font='宋体', en_font='Times New Roman', font_size=Pt(12))
```

### 一级节标题

```python
para = doc.add_paragraph('1.1 标题')
para.alignment = WD_ALIGN_PARAGRAPH.LEFT
para.paragraph_format.space_after = Pt(24)
para.paragraph_format.line_spacing_rule = WD_LINE_SPACING.EXACTLY
para.paragraph_format.line_spacing = Pt(20)
for run in para.runs:
    set_font(run, cn_font='黑体', en_font='Times New Roman', font_size=Pt(16), bold=True)
```

### 页眉设置

```python
section.different_first_page_header_footer = True
section.odd_and_even_pages_header_footer = True

odd_header = section.odd_header
odd_header.is_linked_to_previous = False
p = odd_header.paragraphs[0]
p.text = '论文题目'
p.alignment = WD_ALIGN_PARAGRAPH.CENTER
for run in p.runs:
    set_font(run, cn_font='宋体', en_font='Times New Roman', font_size=Pt(10.5))

even_header = section.even_header
even_header.is_linked_to_previous = False
p2 = even_header.paragraphs[0]
p2.text = '福州大学本科生毕业设计（论文）'
p2.alignment = WD_ALIGN_PARAGRAPH.CENTER
for run in p2.runs:
    set_font(run, cn_font='宋体', en_font='Times New Roman', font_size=Pt(10.5))
```

### 表格去左右边线

```python
from docx.oxml import OxmlElement
table = doc.add_table(rows=3, cols=4)
table.style = 'Table Grid'
tbl = table._tbl
tblPr = tbl.tblPr if tbl.tblPr is not None else OxmlElement('w:tblPr')
borders = tblPr.find(qn('w:tblBorders'))
if borders is None:
    borders = OxmlElement('w:tblBorders')
    tblPr.append(borders)
for bn in ['left', 'right']:
    b = borders.find(qn(f'w:{bn}'))
    if b is None:
        b = OxmlElement(f'w:{bn}')
        borders.append(b)
    b.set(qn('w:val'), 'none')
    b.set(qn('w:sz'), '0')
    b.set(qn('w:space'), '0')
    b.set(qn('w:color'), 'auto')
```

### 插入图片（防遮挡方案）

**核心规则：图片段落禁止使用固定行距（EXACTLY），必须使用单倍行距（SINGLE），否则图片高度会被行距限制而遮挡。**

```python
def add_image(doc, img_path, width_cm=14):
    """插入图片，段落行距使用SINGLE（禁止EXACTLY）"""
    para = doc.add_paragraph()
    para.alignment = WD_ALIGN_PARAGRAPH.CENTER
    para.paragraph_format.space_before = Pt(6)
    para.paragraph_format.space_after = Pt(6)
    para.paragraph_format.line_spacing_rule = WD_LINE_SPACING.SINGLE  # 关键：单倍行距
    run = para.add_run()
    run.add_picture(img_path, width=Cm(width_cm))
    return para


def add_image_caption(doc, text):
    """图题：宋体五号(10.5pt)，居中"""
    para = doc.add_paragraph()
    para.alignment = WD_ALIGN_PARAGRAPH.CENTER
    para.paragraph_format.space_before = Pt(3)
    para.paragraph_format.space_after = Pt(6)
    para.paragraph_format.line_spacing_rule = WD_LINE_SPACING.EXACTLY
    para.paragraph_format.line_spacing = Pt(16)
    run = para.add_run(text)
    set_font(run, '宋体', 'Times New Roman', Pt(10.5), False)
    return para
```

### 插入 EMF 矢量图（从已有 docx 提取时用）

python-docx 不支持直接插入 EMF/WMF 格式。解决方案：两步法。

**第一步：在文档中放白色不可见占位符**

```python
def add_emf_placeholder(doc, marker_id):
    """为稍后替换的EMF图片添加白色不可见占位符"""
    from docx.shared import RGBColor
    para = doc.add_paragraph()
    para.alignment = WD_ALIGN_PARAGRAPH.CENTER
    para.paragraph_format.space_before = Pt(6)
    para.paragraph_format.space_after = Pt(6)
    para.paragraph_format.line_spacing_rule = WD_LINE_SPACING.SINGLE
    run = para.add_run(f'[EMF_PLACEHOLDER_{marker_id}]')
    set_font(run, '宋体', 'Times New Roman', Pt(1), False, RGBColor(255, 255, 255))
    return para
```

**第二步：文档保存后，打开 ZIP 替换占位符为 EMF 图片**

手动嵌入 EMF 的核心步骤：
1. 用 zipfile 打开已保存的 docx
2. 解析 `word/document.xml` 找到占位符段落并替换为 EMF 的 drawing XML
3. 将 EMF 文件写入 `word/media/`
4. 在 `word/_rels/document.xml.rels` 添加图片关系
5. 在 `[Content_Types].xml` 注册 `image/x-emf` 内容类型
6. EMF 图片段落的 XML 中 `lineRule` 必须设为 `auto`（不能是 `exact`）

详细代码模板参见本项目对话历史中的 `embed_emf_after_save` 函数实现。

---

## 参考资料

- 规范原文：E:\ClaudeWorkSpace\20.福州大学本科生毕业设计（论文）撰写规范.doc
- GB/T 7714-2015《信息与文献 参考文献著录规则》
- python-docx 官方文档：https://python-docx.readthedocs.io/
