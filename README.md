# SEU XiaoBao LaTeX 模板

东南大学校庆研究生学术报告会论文 LaTeX 模板（非官方） 使用需谨慎！

本模板目前仍在持续迭代中，欢迎大家提交 Issue 和 PR，共同完善。

## 效果预览

编译 `template.tex` 即可查看完整排版效果，模板已按报告会征稿要求配置好页面、字体、页眉页脚、双栏、标题层级、图表标题、参考文献等格式。

## 项目结构

```
├── seu-report.cls          % 文档类（核心样式文件）
├── template.tex            % 模板示例（可直接修改使用）
├── figures/
│   ├── seu-color-logo.png  % 页眉校徽
│   └── seu-color-logo2.png % 示例插图
├── .latexmkrc              % latexmk 编译配置
└── .vscode/settings.json   % VS Code LaTeX Workshop 配置
```

## 快速开始

### 方式一：Overleaf（推荐）

1. 下载本项目 ZIP（GitHub 页面点击 Code → Download ZIP）
2. 打开 [Overleaf](https://www.overleaf.com)，点击 New Project → Upload Project
3. 上传 ZIP 文件
4. 在 Overleaf 左上角 Menu 中，将编译器设置为 **XeLaTeX**
5. 点击 Recompile 即可

### 方式二：本地编译

**环境要求：** 安装 TeX Live（2020+）或 MiKTeX，需包含 `xelatex` 和 CTeX 宏集。

**使用 latexmk（推荐）：**

```bash
latexmk template.tex
```

项目已配置 `.latexmkrc`，会自动使用 XeLaTeX 编译。

**手动编译：**

```bash
xelatex template.tex
xelatex template.tex   # 运行两次以生成正确的交叉引用
```

### 方式三：VS Code（推荐）

1. 安装 [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) 扩展
2. 打开项目文件夹，项目已包含 `.vscode/settings.json` 配置
3. 打开 `template.tex`，按 `Ctrl+Alt+B` 编译

## 使用说明

编辑 `template.tex`，修改以下元信息命令填入你的论文内容：

```latex
\cnTitle{中文标题}
\enTitle{English Title}
\cnAuthor{作者1\textsuperscript{1}，作者2\textsuperscript{2}}
\enAuthor{Author1\textsuperscript{1}, Author2\textsuperscript{2}}
\cnInstitute{（1.单位，城市，邮编；2.单位，城市，邮编）}
\enInstitute{(1. Department, City, Zip; 2. Department, City, Zip)}
\cnAbstract{中文摘要内容}
\enAbstract{English abstract content}
\cnKeywords{关键词1；关键词2；关键词3}
\enKeywords{Keyword1; Keyword2; Keyword3}
\authorInfo{作者简介：...}
\fundInfo{基金项目：...}       % 无基金可删除此行
```

正文在 `\begin{document}` 之后的双栏区域中编写，支持：

- 上标引用：`\upcite{ref1}` 或普通引用 `\cite{ref1}`
- 三线表：使用 `booktabs` 的 `\toprule`、`\midrule`、`\bottomrule`
- 表注：`\tabnote{注：...}`
- 插图：标准 `\includegraphics` + `\captionof{figure}{...}`

## 字体说明

模板使用以下字体：

| 用途 | 字体 |
|------|------|
| 英文正文 | Times New Roman |
| 中文宋体 | SimSun |

## License

本模板仅供学术交流使用，与东南大学官方无关。
