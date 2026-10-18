# justex2bachelor

江苏科技大学（JUST）本科毕业设计（论文）LaTeX 模板。

本项目基于《江苏科技大学本科学位论文撰写要求及格式规范》（2021.12 修订），
以精简、无冗余的代码结构实现完全符合学校规范的排版，
目标是：**严格合规、代码精简、高性能、快速编译、跨平台兼容**。

> 主控文件：`boyogala-main.tex`  
> 全局配置：`boyogala-setting.tex`  
> 编译引擎：`XeLaTeX` + `Biber`

---

## ✨ 特性

- **严格合规**：纸张、页边距、字号行距、页眉页脚、奇偶页双面装订、四级标题、目录缩进、公式/图表/算法按章编号、参考文献著录等指标均按学校规范实现。
- **代码精简**：主文件与配置文件逻辑内聚、层次清晰，去除历史模板中的无效注释、重复配置与冲突命令。
- **高性能编译**：
  - 移除与 `ctexbook` 冲突的 `titlesec`；
  - 移除破坏固定 20 磅行距的 `zhlineskip`；
  - 移除冗余的 `anyfontsize` / `calc`；
  - `fontset=none` 禁用系统/第三方字库探测，字体 100% 从本地 `font/` 目录加载。
- **字完备（Self-Contained）**：中西文、代码、数学字体全部本地化，零操作系统与第三方字库依赖。
- **现代数学排版**：采用 `unicode-math` + `STIX Two Math`，取代旧式 8-bit Type1 数学字体宏包。
- **国标参考文献**：基于 `biblatex` + `gb7714-2025.bbx/cbx`，符合 GB/T 7714-2025。
- **双语图题**：支持 `\bicaption` 同时输出中英文双行图/表题。
- **算法/代码**：`algorithm2e` + `listings`，支持行号、语法高亮与阴影外框。

---

## 📁 目录结构

```text
justex2bachelor/
├── boyogala-main.tex              # 模板主控文件（文档流与前/主体/后置调度）
├── boyogala-setting.tex           # 全局导言区配置（宏包、版心、样式、环境）
├── ref.bib                        # BibLaTeX 参考文献数据库
├── gb7714-2025.bbx               # 国标 GB/T 7714-2025 著录样式
├── gb7714-2025.cbx               # 国标 GB/T 7714-2025 引用标注样式
├── justbks.md                     # 详细规范与配置重构指南
├── readme.txt                     # 示例片段（环境/字体演示）
├── chapter/                       # 论文各部分章节源码
│   ├── boyogala1_cover.tex        # 外封面与内封（扉页）
│   ├── boyogala2_statement.tex    # 原创性声明、版权使用授权书
│   ├── boyogala3_abstract_cn.tex # 中文摘要与关键词
│   ├── boyogala4_abstract_en.tex # 英文摘要与关键词
│   ├── boyogala5_chapters.tex    # 正文各章
│   ├── boyogala6_conclusion.tex  # 结论
│   ├── boyogala7_reference.tex   # 参考文献输出
│   ├── boyogala8_Appendix.tex    # 附录
│   └── boyogala9_thanks.tex      # 致谢
├── figure/                        # 插图与封面底图
│   ├── cover1.pdf                 # 外封面底图（严禁篡改）
│   ├── cover2.pdf                 # 内封底图（严禁篡改）
│   ├── attention.png              # 示例插图
│   ├── model1_1000.png            # 示例插图
│   └── model1_10000.png           # 示例插图
└── font/                          # 本地字完备字体库（20 个字体文件）
    ├── NotoSerifCJKsc-*.otf       # 宋体（思源宋体）
    ├── SourceHanSansCN-*.otf      # 黑体（思源黑体）
    ├── LXGWWenKai-Regular.ttf     # 楷体（霞鹜文楷）
    ├── ZhuqueFangsong-Regular.ttf  # 仿宋（朱雀仿宋）
    ├── STIXTwoText-*.ttf          # 西文衬线（STIX Two Text）
    ├── SourceSans3-*.otf          # 西文无衬线（Source Sans 3）
    ├── JetBrainsMono-*.ttf        # 等宽（JetBrains Mono）
    ├── STIXTwoMath-Regular.ttf    # 数学（STIX Two Math）
    └── XITSMath-Bold.otf          # 粗体数学
```

> 注：`*.aux`、`*.log`、`*.pdf` 等编译产物已通过 `.gitignore` 忽略。

---

## 🧰 环境要求

| 项目 | 要求 |
|---|---|
| TeX 发行版 | TeX Live 2022+ 或 MiKTeX（需包含 `ctex`、`biblatex`、`unicode-math` 等宏包） |
| 编译引擎 | `XeLaTeX`（原生支持 UTF-8 与本地 OpenType/TrueType 字体） |
| 文献引擎 | `Biber`（配合 `biblatex` + `gb7714-2025` 样式） |
| 推荐工具 | TeXstudio / VS Code (LaTeX Workshop) / Overleaf（需上传 font/ 目录） |
| 操作系统 | Windows / macOS / Linux（字库已本地化，不依赖系统字体） |

---

## 🚀 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/aijunly/justex2bachelor.git
cd justex2bachelor
```

### 2. 编译（推荐 latexmk）

```bash
latexmk -xelatex -bibtex boyogala-main.tex
```

或手动四步编译：

```bash
xelatex boyogala-main.tex
biber boyogala-main
xelatex boyogala-main.tex
xelatex boyogala-main.tex
```

### 3. 查看输出

编译成功后生成 `boyogala-main.pdf`。

### 4. 清理中间文件

```bash
latexmk -c
```

---

## 📝 使用指南

### 基本信息填写

打开 `chapter/boyogala1_cover.tex` 与 `chapter/boyogala2_statement.tex`，
按模板占位符填入：论文题目、作者、学号、学院、专业、指导教师、日期等。

### 正文撰写

在 `chapter/boyogala5_chapters.tex` 中按 `\chapter{}` / `\section{}` / `\subsection{}` 组织内容。
模板已预置绪论与各章示例，可直接替换。

### 参考文献

1. 在 `ref.bib` 中按 BibLaTeX 格式添加条目；
2. 正文使用 `\cite{key}` 引用；
3. 编译时自动按 GB/T 7714-2025 格式输出。

### 插图

```latex
\includegraphics[width=0.8\textwidth]{figure/your_image.png}
```

支持 PDF / PNG / JPG。建议矢量图用 PDF，位图用 PNG。  
双语图题使用 `\bicaption{中文题}{English caption}`。

### 表格

使用标准 `tabular` + `booktabs` 三线表；跨页长表用 `longtable`。

### 数学公式

直接使用 `amsmath` 环境（`equation`、`align`、`gather` 等），数学字体为 STIX Two Math。

### 代码清单

使用 `listings` 环境，支持语法高亮与阴影外框。

### 算法伪代码

使用 `algorithm2e`，支持行号与按章编号。

---

## 🔤 字体说明

本模板 **100% 从 `font/` 目录加载字体**，不依赖操作系统或 TeX Live 字库：

| 用途 | 字体 | 文件 |
|---|---|---|
| 中文宋体 | 思源宋体 (Noto Serif CJK SC) | `NotoSerifCJKsc-*.otf` |
| 中文黑体 | 思源黑体 (Source Han Sans CN) | `SourceHanSansCN-*.otf` |
| 中文楷体 | 霞鹜文楷 (LXGW WenKai) | `LXGWWenKai-Regular.ttf` |
| 中文仿宋 | 朱雀仿宋 (Zhuque Fangsong) | `ZhuqueFangsong-Regular.ttf` |
| 西文衬线 | STIX Two Text | `STIXTwoText-*.ttf` |
| 西文无衬线 | Source Sans 3 | `SourceSans3-*.otf` |
| 等宽 | JetBrains Mono | `JetBrainsMono-*.ttf` |
| 数学 | STIX Two Math | `STIXTwoMath-Regular.ttf` |

> `font/` 目录约 100MB，已包含在仓库中以保证开箱即用。若需减小仓库体积，可改用系统字体并修改 `boyogala-setting.tex`。

---

## ⚠️ 注意事项

1. **编译器必须为 XeLaTeX**，pdfLaTeX 无法处理本地 OpenType 字体。
2. **文献引擎必须为 Biber**，不是 BibTeX。
3. 封面底图 `cover1.pdf` / `cover2.pdf` 为学校统一底图，**请勿篡改**。
4. 首次编译可能较慢（字体加载），后续编译会缓存。
5. 若出现 `File not found`，检查工作目录是否为项目根目录。

---

## ❓ 常见问题

| 问题 | 解决 |
|---|---|
| `Font not found` | 确认 `font/` 目录完整，且编译目录为项目根目录 |
| 参考文献不显示 | 确认使用 Biber 而非 BibTeX；运行完整四步编译 |
| 页眉/页脚异常 | 检查是否误删 `\pagestyle` / `\fancypagestyle` 相关命令 |
| 目录不更新 | 多编译一次，或执行 `latexmk -g` 强制重新生成 |
| 中文乱码 | 确认源文件为 UTF-8 编码，编译器为 XeLaTeX |

---

## 📜 许可证

本模板代码部分采用 [MIT License](LICENSE)。  
学校规范文档与封面底图版权归原作者/江苏科技大学所有，仅作学术用途。

---

## 🙏 致谢

- 江苏科技大学教务处《本科学位论文撰写要求及格式规范》（2021.12）
- CTeX 项目、biblatex-gb7714、unicode-math、STIX Fonts、Adobe Source Han / Noto CJK、霞鹜文楷、朱雀仿宋等开源项目

---

## 📮 联系

如有问题或建议，欢迎通过 GitHub Issues 反馈。
