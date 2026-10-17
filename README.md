# academic-template

Reusable academic research template：跨课程、跨学期复用的学术研究仓库模板。用于保存教师要求、文献证据、提纲、推导、数据、计算与论文版本；不预设具体课程、期刊或研究结论。

## 创建课程仓库

1. 仓库所有者在 GitHub 的 **Settings → General → Template repository** 勾选模板选项。本次仅配置仓库文件，尚未验证或启用该设置。
2. 在仓库主页选择 **Use this template → Create a new repository**，按课程与学期命名，并根据材料保密要求选择可见性。
3. 将教师的原始任务书、评分标准和补充通知存入 `requirements/`，保留原件，再填写 [COURSE_SPEC.md](requirements/COURSE_SPEC.md)。未知项保持“待确认”。
4. 如教师要求期刊格式，将官方指南和模板存入 `journal-template/`，记录来源、版本和获取日期。
5. 先确认研究问题和方法，再进行文献核验、提纲、研究和写作；提交前完成 [学术审计清单](requirements/ACADEMIC_AUDIT.md)。

本 README 和 [AGENTS.md](AGENTS.md) 是通用规则；课程事实和约束写入 `requirements/COURSE_SPEC.md`，不要把某门课程的规则回写为通用模板默认值。教师原始要求具有权威性，课程配置是其可追溯摘要。

## 目录与记录

| 路径 | 用途 |
| --- | --- |
| [requirements/](requirements/README.md) | 教师原件、课程配置与提交前审计 |
| [journal-template/](journal-template/README.md) | 官方作者指南、样文与 Word/LaTeX 模板 |
| [literature/](literature/README.md) | 文献笔记、导出元数据与核验记录 |
| [outlines/](outlines/README.md) | 研究问题、证据映射和提纲 |
| [drafts/](drafts/README.md) | 论文草稿、修订说明和人工复核项 |
| [models/](models/README.md) | 假设、变量、数学推导和均衡验证 |
| [data/](data/README.md) | 有权存储的数据、输入、来源与处理记录 |
| [scripts/](scripts/README.md) | 可复现计算、绘图与验证脚本及依赖说明 |
| [outputs/](outputs/README.md) | 生成结果、运行记录及交付版本 |
| [references.bib](references.bib) | 初始为空的 BibTeX 文献库，不含示例或虚构条目 |

## 必须履行的核验义务

- 所有引用必须对应真实、可识别的出版物。优先向出版商、期刊、Crossref、DOI 注册记录和可靠学术数据库核验元数据；AI 回答本身不是文献真实性证据。无法独立核验的来源标为“未核实”，不得描述为已验证。
- 元数据核验、全文获取、相关章节阅读和论点支持核验分别记录。不能仅凭摘要或元数据声称读过全文；引文、页码、作者、DOI 和其他书目信息不得编造。每个实质性引用需支持相邻论点，并可追溯到核验来源与状态。
- 推导明确假设、变量和适用条件，检查代数、微分、优化及均衡条件。博弈模型核对参与者、策略、收益、均衡概念、最佳反应与边界，区分必要条件和充分条件；不以数值证据代替证明。
- 计算和论文数值关联到 `scripts/`、`models/`、`data/` 与 `outputs/`。记录参数、方法、数据来源、软件环境、依赖和适用的随机种子。禁止为迎合结论修改或伪造经验数据。
- “已验证”必须有实际执行的检查和证据；保留失败与未完成项。提交前审计覆盖参考文献、元数据、引用支持、引文页码、推导、数值、复现、教师要求、期刊格式和未解决事项。缺失必要证据时不得宣称通过。

完整的强制规范见 [AGENTS.md](AGENTS.md)；每门课程复制使用的审计清单见 [ACADEMIC_AUDIT.md](requirements/ACADEMIC_AUDIT.md)。脚本可辅助检查数值、路径与引用键，但文献对论点的支持、证明完整性、数据合法性和课程要求的解释通常仍需阅读原始材料并由人复核。

## 协作与版本管理

ChatGPT Work 可解释任务、阅读资料、制定提纲和协助修改；Codex Cloud 可组织文件、编写计算脚本、核对模型和生成产物。分工可按任务调整。两者均应读取仓库要求，以已提交文件作为共享上下文；**ChatGPT Work 的 GitHub 读写权限必须单独实测**，本环境的 Git 访问不证明它具有相同权限。

开始前同步分支并检查未提交改动；同一文件避免同时编辑。大改动使用分支和 PR，小步提交并说明原因。其他会话不会自动获得未提交内容或聊天记录；交接时记录文件路径、提交、已完成检查和待决问题。遇到并发修改先比较差异，不覆盖未审阅工作；二进制文件需协调编辑。提交前核对凭据、个人信息、数据许可与课程的 AI 使用和披露要求。

## Zotero 与计算环境

Zotero 可作为外部文献库，将 BibTeX 导出至 `references.bib`，或将 CSL JSON 导出到 `literature/`。稳定维护正文引用键、Zotero item key（若可用）和 DOI 的映射，导入时检查重复、缺失字段和核验状态。导出或成功解析不等于已核验，也不等于可访问全文。不要提交 Zotero 数据库或本机附件绝对路径；本模板不安装集成、不请求 API 密钥，不假定已连接 Zotero 或 Google Drive。

本模板不强制安装计算依赖。课程确需计算时，在 `scripts/` 记录运行命令、软件版本和依赖锁定方式；虚拟环境和本地密钥不入库。研究文件（PDF、DOCX、CSV、Markdown、LaTeX 和正式输出）不会被通配忽略，提交前需逐项审核是否适合共享。
