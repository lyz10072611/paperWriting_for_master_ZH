# paper-writing4master

> 中文硕士毕业论文一体式写作 **Cursor Skill**：写作流程（风格迁移、错题本、长期记忆）+ 硕士论文格式规范 + 去 AI 味（reduce-ai_ZH）。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 功能概览

| 模块 | 说明 |
|------|------|
| **写作流程** | 风格迁移、错题本（error_log）、长期记忆（hard/soft/reference），配合 Prompts 解析格式、建章、起草、一致性检查 |
| **硕士论文格式** | 章节结构、引用与图表规范、方法与数据章节写作要求（保留因果链与复现信息） |
| **去 AI 味（reduce-ai_ZH）** | 24 种 AI 写作模式、学术禁用表达与结构、润色检查清单，兼顾自然语言与学术规范 |

详见根目录 **SKILL.md**（Cursor 会据此加载本 Skill）。

---

## 安装（作为 Cursor Skill）

1. 克隆到本地：

```bash
git clone https://github.com/lyz10072611/paperWriting_for_master_ZH.git
```

2. 放入 Cursor 的 skills 目录（二选一）：
   - **推荐**：复制整个文件夹到  
     `C:\Users\<你的用户名>\.cursor\skills\paper-writing4master\`
   - 或通过 Cursor 设置中配置的 Skill 目录，将仓库克隆到该目录下。

3. 在 Cursor 中撰写/润色论文时，可直接引用本 Skill；Agent 会按 SKILL.md 与 `.ai_context` 中的规则执行。

---

## 快速使用

- **解析格式规范**：请解析 `资料/01_格式要求/毕业论文格式要求.pdf`
- **提取写作风格**：请提取 `资料/03_我的内容/` 和 `资料/04_我的小论文/` 中的写作风格
- **构建章节框架**：根据参考论文创建 chapters 框架
- **起草某章**：按 `chapters/method_1.tex` 的大纲起草正文
- **检查一致性**：请检查全文术语与格式一致性
- **去 AI 味润色**：按 paper-writing4master 规则润色某段/某节，保留方法说明与数据信息

---

## 论文项目结构（使用本 Skill 时）

以**论文中文名称**为根目录：

```
<论文中文名称>/
├── main.tex
├── chapters/           # 各章 .tex
├── .ai_context/        # 从本 Skill 复制 .ai_context 模板
│   ├── style_profile.md
│   ├── error_log.md
│   ├── custom_specs.md
│   └── memory/
└── 资料/
    ├── 01_格式要求/     # 毕业论文格式规范 PDF
    ├── 02_参考毕业论文/ # 他人已通过论文
    ├── 03_我的内容/     # 中期报告、初审稿等
    ├── 04_我的小论文/   # 小论文（可扩写为毕业论文）
    └── 提取/            # parse_pdf 输出
```

详见 `.ai_context/project_structure.md`。

---

## 核心 Prompts（.ai_context/prompts/）

| 文件 | 作用 |
|------|------|
| `0_pdf_reader.md` | 读取 PDF，提取证据入库 |
| `1_format_spec_reader.md` | 解析格式规范 PDF → hard_memory |
| `2_style_extractor.md` | 资料 → style_profile |
| `3_section_builder.md` | 参考论文 → chapters 框架 |
| `4_subsection_builder.md` | 生成章节内小标题结构 |
| `5_content_writer.md` | 按大纲起草正文 |
| `6_consistency_checker.md` | 术语 / 格式一致性审计 |
| `7_error_logger.md` | 纠正 → error_log + 重写 |

去 AI 味规则与 24 种模式见 **SKILL.md** 第六节及 `.ai_context/reduce-ai_ZH_patterns.md`。

---

## 仓库结构

```
paper-writing4master/
├── README.md           # 本文件
├── SKILL.md            # Cursor Skill 主入口（能力与规范）
├── LICENSE
├── .gitignore
├── .ai_context/
│   ├── reduce-ai_ZH_patterns.md   # 去 AI 味 24 种模式详解
│   ├── style_profile.md         # 风格模板
│   ├── error_log.md
│   ├── custom_specs.md
│   ├── project_structure.md
│   ├── memory/                  # hard/soft/reference 模板
│   ├── prompts/                 # 0–7 号 prompts
│   └── scripts/
│       ├── parse_pdf.py
│       └── create_placeholder_image.py
└── .agents/workflows/           # 可选工作流
```

---

## 致谢与参考

- 写作流程与 Prompts 结构参考 [Chinese-Dissertation-Writing-Skill](https://github.com/junkzhu/Chinese-Dissertation-Writing-Skill) 与 [AI-Vibe-Writing-Skills](https://github.com/donghuixin/AI-Vibe-Writing-Skills)。
- 去 AI 味规则（reduce-ai_ZH）参考 [Humanizer-zh](https://github.com/op7418/Humanizer-zh)，并融合中文学术论文补充。

---

## License

MIT License
