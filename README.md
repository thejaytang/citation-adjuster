# Citation Adjuster

`citation-adjuster` 是一个 Codex skill，用于审查和调整学术正文中的 **citation** 插入方式。它主要解决 AI 生成或重写后的论文段落中常见的问题：一句话末尾堆积很多文献、引文和论断对应不清、引用位置过远、用参考文献给笼统表述“兜底”、以及 **literature review** 中缺少真正的 **synthesis**。

这个 skill 的目标不是增加引用数量，而是提高 **citation integrity**：每个引用都应服务于一个明确、局部、可核查的正文论断。

## 推荐使用新版

如果你需要更完整、更稳定的论文引文与参考文献审查流程，建议优先使用 [`supercite-through-zotero`](https://github.com/thejaytang/supercite-through-zotero)。

`supercite-through-zotero` 在 `citation-adjuster` 的正文引文审查基础上，进一步加入了 **Zotero-first** workflow、正文引用和 **reference list** 一致性检查、参考文献真实性审查、**BibTeX/BibLaTeX** cite key 匹配，以及面向 Zotero 的导入和插入建议。它更适合需要系统核查论文引用、参考文献条目和 Zotero library 的场景。

## 功能

- 审查论文、课程论文、thesis、dissertation、grant text 和 **literature review** 中的正文引文。
- 标记 **citation dumping**，也就是多个文献堆在一句宽泛或多论断句子末尾。
- 检查 **claim-source alignment**，判断引文是否贴近并服务于具体论断。
- 识别过度引用、远距离引用、缺少 citation anchor、弱 **synthesis** 等问题。
- 在不新增文献的前提下，给出最小改写版。
- 支持 APA/Harvard 作者年份格式、数字编号格式和脚注式引文的共同判断逻辑。

## 不做什么

- 不编造文献、发现、页码、样本、方法或结论。
- 在没有来源内容时，不声称某篇文献实际支持某个论断。
- 不把所有多文献引用都判为错误。若多篇文献支持同一个精确论断，或在综述中被清楚分组，多文献引用可以保留。
- 不自动转换引文格式，除非用户明确要求。

## 安装

把仓库克隆到 Codex skills 目录：

```bash
git clone https://github.com/thejaytang/citation-adjuster.git ~/.codex/skills/citation-adjuster
```

安装后，如果你的环境不会自动刷新 skills，重启 Codex 或重新加载 skills。

## 使用方式

显式调用：

```text
Use $citation-adjuster to audit and revise citation placement in this manuscript.
```

常用请求：

```text
Use $citation-adjuster to check whether these references are piled up incorrectly.
```

```text
Use $citation-adjuster to revise the citation placement in this literature review paragraph.
```

```text
Use $citation-adjuster to separate claims and citations without adding new sources.
```

也可以直接中文调用：

```text
用 $citation-adjuster 检查这段论文正文里的引文是否堆砌，并给出最小改写版。
```

## 输入建议

最适合提供：

- 需要审查的正文段落或章节。
- 当前已有的正文引文。
- reference list，如果有。
- 文献摘要、阅读笔记、PDF 或来源总结，如果你希望检查真实来源支持关系。

如果只提供正文，skill 只会判断可见的引文结构、插入位置和表面对应关系。对于来源内容无法确认的问题，它会标记为 `needs source check`，而不是假装已经核查过文献。

## 输出格式

默认输出通常包含：

- 整体判断。
- 按位置列出的审查表格。
- 风险等级、置信度、问题、原因、建议和最小改写版。
- 当缺少来源内容时，明确标记无法验证的支持关系。

风险等级：

| Risk | 含义 |
|---:|---|
| 0 | 引文插入基本合理。 |
| 1 | 轻微冗余、位置略远或可以更清楚。 |
| 2 | 明显 **citation dumping**、多论断共用一组引文，或来源角色不清。 |
| 3 | 高风险错配、伪支撑，或把未核查的来源当成已核查支持。 |

## 示例

问题句：

```text
Digital feedback improves motivation, self-regulation, engagement, and achievement (A, 2019; B, 2020; C, 2021; D, 2022; E, 2023).
```

问题：

- 一个句子包含 motivation、self-regulation、engagement 和 achievement 多个论断。
- 所有文献集中在句末，读者无法判断哪篇支持哪一点。
- 如果没有来源内容，不能确认每篇文献是否都支持整句话。

可能的最小改写：

```text
Digital feedback has been associated with higher student motivation in several classroom studies (A, 2019; B, 2020). Work on self-regulated learning links feedback timing to planning and monitoring behaviors (C, 2021). Evidence for achievement gains is more mixed, with D (2022) reporting short-term test improvements and E (2023) finding no durable effect.
```

## 仓库结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── citation-rubric.md
```

`SKILL.md` 包含核心工作流。`references/citation-rubric.md` 包含详细评分规则、多文献引用判断规则和三类引文格式示例。
