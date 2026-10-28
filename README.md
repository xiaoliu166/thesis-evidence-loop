# Thesis Evidence Loop｜论文证据闭环

从企业真实问题到研究大纲与选题报告：用六个分块、14份模板，把问题、证据、方案与评价逐项对应。

An evidence-first Agent Skill for applied thesis research: connect research questions, evidence, interventions, and evaluation through six stages and fourteen templates.

这是一个以中文说明为主的 Agent Skill，适合工程管理类论文的选题、大纲、文献整理、选题报告及研究写作。它提供研究组织方法和模板；实际论文要求以使用者所在学校、专业及导师规定为准。

## 包含什么

| 分块 | 步骤 | 主要产出 |
|---|---|---|
| 前期准备 | 1—2 | 要求与数据清单、范文对比 |
| 确定论文框架 | 3—5 | 范文拆解、研究定位、大纲与对应表 |
| 文献准备 | 6—8 | 检索记录、题录核验、阅读卡与章节映射 |
| 结合文献修正 | 9 | 框架修订、研究设计与指标口径 |
| 选题报告与答辩 | 10—11 | 报告骨架、修改记录、PPT脚本与问答 |
| 研究与写作 | 12—14 | 实施评价、章节写作卡与提交复核 |

每步附有 Markdown 产出模板和人工核对事项。支持从已有进度续作，也可只完成其中一项任务。

## 安装与使用

### 在 Codex 中使用

仓库：[xiaoliu166/thesis-evidence-loop](https://github.com/xiaoliu166/thesis-evidence-loop) · [发布下载](https://github.com/xiaoliu166/thesis-evidence-loop/releases)

```bash
git clone https://github.com/xiaoliu166/thesis-evidence-loop.git
```

1. 下载仓库源码或克隆仓库，保留根目录 `SKILL.md` 与资源目录的相对关系。
2. 将整个文件夹放入本机技能目录，文件夹名为 `thesis-evidence-loop`。通常路径为 `~/.codex/skills/thesis-evidence-loop/`；若配置了 `CODEX_HOME`，使用其下的 `skills/thesis-evidence-loop/`。
3. 在新的会话中确认技能已被识别，然后用 `$thesis-evidence-loop` 调用。已有同名技能时先比较内容，避免直接覆盖个人修改。

示例：

> 使用 $thesis-evidence-loop，结合我提供的学校要求和已有材料，判断当前阶段，并帮我完成研究定位与粗大纲。

其他常见请求：

> 使用 $thesis-evidence-loop。我已有大纲，只核对研究问题、证据、改进措施和评价指标是否对应。

> 使用 $thesis-evidence-loop。只根据这些候选文献整理核验台账，无法核实的标为待核验。

### 在其他工具中使用

在支持 `SKILL.md` 的工具中，按该工具的本地安装方式加载文件夹。不同工具的目录约定和调用方式可能不同；本仓库没有对所有工具逐一测试。

也可直接阅读 [工作流](references/workflow.md) 并复制 [14份模板](assets/templates/)，无需安装插件。

## 开始前提供什么

- 本次要完成的任务，以及已有材料和当前有效版本。
- 学校或导师要求、报告模板、文献标准；缺失项可以暂留待确认。
- 研究对象、已有真实数据、访谈及试点条件。

可从 [空白项目配置](assets/project-config.md) 开始。文献篇数、英文比例、院校限制均不默认预设；[示例配置](examples/project-requirements-example.md) 仅演示格式。

## 工具与核验边界

- 技能本身为 Markdown 指令和模板，无运行时包依赖，不要求付费服务或特定翻译产品。
- 文献检索、PDF提取、翻译、Word与PPT生成，取决于运行环境实际提供的工具；不能完成时应如实报告，保留可用的文本产出。
- “题录已核验”“全文已取得”“已阅读全文”分别记录。没有原文时不编造页码；不能访问数据库时不声称完成核验。
- 人工核对事项说明谁核对、核对什么，不要求每步都由导师审批。详见 [人工核对事项](references/manual-checks.md)。
- 研究计划、模拟、回测与实测结果分别标记。范文可以学习论证方式，不得把他人研究对象、数据或结论替换名称后作为自己的结果。

## 仓库结构

```text
thesis-evidence-loop/
├── README.md
├── LICENSE
├── .gitignore
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── workflow.md
│   ├── requirements.md
│   └── manual-checks.md
├── assets/
│   ├── project-config.md
│   └── templates/step-01.md … step-14.md
└── examples/
    ├── project-requirements-example.md
    └── usage-scenarios.md
```

`examples/` 的情境均为明确标识的假设输入，不包含真实论文、企业台账、访谈或实验结果。

## 校验与贡献

基础检查包括技能元数据、相对链接、14份模板和敏感路径扫描。[使用情境](examples/usage-scenarios.md) 提供进一步验证的输入与验收点；它们不是已经对所有模型跑通的效果承诺。

欢迎提交流程改进、模板优化或匿名复现问题。请说明触发请求、预期行为、实际行为及必要的脱敏片段；不提交论文全文、企业资料、个人信息、账号凭据或未经授权的附件。项目使用者的材料建议存放在仓库之外，本地测试可放入被忽略的 `local/` 或 `private/`。

## 许可与署名

采用 [MIT License](LICENSE)，覆盖本仓库的技能说明与模板；使用者另行提供的论文、学校文件、数据及第三方材料不因此获得再分发许可。

当前以项目名义署名为 `thesis-evidence-loop contributors`，未公开个人身份信息。维护者可在发布前按实际权利归属调整署名。
