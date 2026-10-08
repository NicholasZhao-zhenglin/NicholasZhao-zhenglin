<div align="center">

# 杨琪俊 · Nicholas Zhao

**大模型应用工程 ｜ LLM Agent · RAG · 非结构化数据处理**

北京科技大学 · 人工智能 · 硕士在读 · 北京

📧 **15623221569@163.com** 　·　 🐙 **[github.com/NicholasZhao-zhenglin](https://github.com/NicholasZhao-zhenglin)**

</div>

---

## 关于我

我做的是**把大模型从能跑通的 demo，推进到能用的系统**这一层——检索增强生成、Agent 的记忆与规划、以及支撑这些的非结构化数据处理。

工程上偏好把系统拆成可独立验证的模块，每层都有明确的测试和判据，而不是靠肉眼判断「看起来对了」。系统能跑起来只是起点，能说清它为什么对、以及错在哪，才算做完。

**当前关注：** LLM Agent 的长期状态建模、混合检索（BM25 + 向量 + RRF 融合）、复杂 PDF 的结构化解析。

---

## 代表项目

<table>
<tr>
<td width="50%" valign="top">

### 🧠 [adaptive-english-speaking-agent](https://github.com/NicholasZhao-zhenglin/adaptive-english-speaking-agent)

**自适应学习 Agent** — 把「学习目标 → 掌握度 → 错因 → 练习」做成长期状态，由系统自主决定下一轮学什么。

`Python` `Flask` `LLM`

- 表达级掌握度与错因持久化，间隔复习 1 / 3 / 7 / 14 / 30 天
- 近 5 次正确率 <60% 强化复习，≥85% 增加新内容
- 确定性调度器 + LLM 内容生成，决策可解释

</td>
<td width="50%" valign="top">

### 🗣 [ENGLISH-SPEAKING](https://github.com/NicholasZhao-zhenglin/ENGLISH-SPEAKING)

**全栈口语训练应用** — 语音跟读 + AI 对话 + 云端多端同步。

`JavaScript` `Supabase` `Edge Functions`

- 课程结构：18 单元 × (1 母句 + 3 迁移题)，强制语音作答
- 语音链路双通道：浏览器实时识别 + 录音送多模态模型
- 无 JWT 场景下以 SECURITY DEFINER RPC 收敛数据入口，同步码即唯一凭据

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 📚 [cnipa-ipc-dataset](https://github.com/NicholasZhao-zhenglin/cnipa-ipc-dataset)

**IPC 专利分类表结构化数据集** — 国知局原始 PDF → 可直接检索的层级数据。

`Python` `数据工程`

- 1,890 页 / 34 MB PDF → **78,449 个节点**，8 部 / 130 大类 / 649 小类
- 中文标题零乱码，父子层级与父链路径完整重建
- 62 MB 产物 gzip 至 3.2 MB，解包仅用标准库

</td>
<td width="50%" valign="top">

### 🧩 [leetcode-hot100](https://github.com/NicholasZhao-zhenglin/leetcode-hot100)

**离线算法题解手册** — 100 道热题 · 17 个分类，单文件零依赖。

`HTML` `JavaScript`

- 分类目录 / 搜索 / 难度筛选 / 收藏 / 学习进度
- 题目描述 + 思路 + 代码 + 复杂度 + 知识点
- [在线浏览 →](https://nicholaszhao-zhenglin.github.io/leetcode-hot100/)

</td>
</tr>
</table>

---

## 工程经历

> **关于链接**：以下项目位于公司内部 GitLab / 私有仓库，涉及公司资产，**不提供公开链接**。
> 项目结构、代码与设计细节可在面试中当面说明。

### 📜 中国专利智能撰写系统 · OpenPatent-CN

把「一段技术描述」推进到「一份可提交的中国专利申请文件」的 LLM Agent 流水线：
技术事实提取 → 创新点挖掘 → 权利要求书 + 六章技术交底书 → 审查模拟 → 多格式导出。

`Python` `Flask` `LLM Agent` `docx / PDF` 　·　 119 个源文件 / 42 次提交

- **技术事实层（FactStore）**：所有 Agent 只能引用 FactStore 中可验证的事实，**从架构上禁止编造数据**；Claim → Experiment / Benchmark 形成可追溯的证据链，审查答复时可一键回溯「依据是什么」。
- **保护范围自博弈**：Generalize → Expand → Narrow 迭代搜索「最大保护范围」与「可授权边界」的平衡点。
- **审查员模拟**：按中国专利三步法（确定最接近现有技术 → 区别技术特征 → 显而易见性判断）自动生成审查意见并回检。
- **联网查新**：接入 CNIPA / Google Patents / ArXiv / Semantic Scholar 做真实检索，而不是依赖模型内部记忆。
- **输出闭环**：Markdown / DOCX / PDF 导出，交底书含可交互流程图（可拖拽缩放、PNG/PDF 导出）。

### 📊 专利材料自动评测服务 · Patent Agent Eval

**刻意不用 LLM 打分**的规则评测体系 —— 因为模型评分不可复现、漂移难解释；
改用确定性规则后，**每一分都能定位到触发它的那句原文**。

`Python` `规则引擎` `HTTP 服务` 　·　 44 个源文件 / 19 次提交

- 三套判定体系（说明书 / 权利要求书 / 摘要）+ 三性总评（新颖性 / 创造性 / 实用性），逐维度带权重。
- **硬闸门设计**：如摘要超过 300 字直接封顶 59 分 —— 结构性违规不允许被其他维度的高分稀释。
- 输出结构化评分卡 `scorecard.json` + 中文报告，含逐维度得分与扣分原因。
- 以 HTTP 服务形式接入撰写流水线，形成「生成 → 评测 → 回改」的闭环。

### 🔬 其他工程与实习

- **水木分子 · 算法实习生** — 基于 LLM 从文献 PDF 中抽取疾病–通路关系，构建生物医学知识图谱；负责抽取模块的 prompt 设计与多模型对比评估。
- **文档解析方案选型** — 对 MinerU / DeepDoc 等本地 PDF 解析方案做效果对比与选型评估，用于金融文档问答场景。
- **模型服务线上验证** — 参与视觉识别服务的线上验证：阈值调优、配置变更的生效验证与指标回归。按确定的判据（配置校验 + 指标对比）判断改动是否达标，而非凭观感。
- **RAG 知识库服务（私有仓库 · 在研）** — FastAPI + pgvector + 异步 SQLAlchemy + 对象存储的检索服务骨架，含健康检查与容器化编排；检索与生成链路正在实现中，尚未达到可展示的完成度。

---

## 技术栈

**语言**　Python · JavaScript / TypeScript · SQL · HTML/CSS

**大模型**　LLM Agent 设计 · RAG（混合检索 / RRF 融合 / 重排）· Prompt Engineering · 多模型评估 · OpenAI 兼容接口

**框架**　FastAPI · Flask · LangGraph · PyTorch

**数据**　PostgreSQL / pgvector · Milvus · Elasticsearch · MemGraph · Supabase

**工程**　Git · Docker · Linux · 单元测试与回归测试 · 配置管理与灰度验证 · 规则化评测体系（可复现、可追溯）

---

## 教育

**北京科技大学** — 人工智能 · 硕士在读
**北京科技大学** — 本科

---

<details>
<summary><b>🇬🇧 English</b></summary>

<br>

### Yang Qijun · Nicholas Zhao

**LLM Application Engineering ｜ Agent · RAG · Unstructured Data**

M.S. in Artificial Intelligence, University of Science and Technology Beijing

📧 **15623221569@163.com** · 🐙 [github.com/NicholasZhao-zhenglin](https://github.com/NicholasZhao-zhenglin)

---

**About**

I work on the layer that turns an LLM demo into a system that actually holds up — retrieval-augmented generation, memory and planning for LLM agents, and the unstructured-data pipelines underneath them.

I prefer building systems as independently verifiable modules, each with its own tests and acceptance criteria, rather than judging correctness by eye.

**Focus:** long-term state modelling for LLM agents, hybrid retrieval (BM25 + dense + RRF), structured parsing of complex PDFs.

---

**Selected Projects**

| Project | What it is | Stack |
| --- | --- | --- |
| [adaptive-english-speaking-agent](https://github.com/NicholasZhao-zhenglin/adaptive-english-speaking-agent) | Adaptive learning agent with persistent mastery state, error-cause diagnosis and self-directed planning | Python · Flask · LLM |
| [ENGLISH-SPEAKING](https://github.com/NicholasZhao-zhenglin/ENGLISH-SPEAKING) | Full-stack speaking-practice app: speech scoring, AI dialogue, cross-device sync | JavaScript · Supabase · Edge Functions |
| [cnipa-ipc-dataset](https://github.com/NicholasZhao-zhenglin/cnipa-ipc-dataset) | Structured dataset built from the official IPC patent-classification PDFs — 78,449 nodes | Python |
| [leetcode-hot100](https://github.com/NicholasZhao-zhenglin/leetcode-hot100) | Offline problem-solving handbook, 100 problems across 17 categories | HTML · JavaScript |

---

**Experience**

> Projects below live in internal GitLab / private repositories and belong to the companies involved, so **no public links are provided**. Structure and implementation details available on request.

- **OpenPatent-CN — Chinese patent drafting system (LLM agent pipeline)** — Turns a technical description into a filing-ready Chinese patent application: fact extraction → novelty mining → claims + six-chapter disclosure → examiner simulation → multi-format export. 119 source files / 42 commits.
  - *FactStore layer*: every agent may only cite verifiable facts, so fabrication is blocked at the architecture level; Claim → Experiment evidence chains stay traceable.
  - *Scope self-play*: Generalize → Expand → Narrow search for the balance between maximum protection and allowable boundary.
  - *Examiner simulation*: automatic office-action drafts following China's three-step obviousness test.
  - *Live prior-art search* across CNIPA / Google Patents / ArXiv / Semantic Scholar.
- **Patent Agent Eval — rule-based evaluation service** — Deliberately **does not use an LLM as the grader**, because model scores drift and are hard to reproduce; deterministic rules mean every point maps back to the sentence that triggered it. 44 source files / 19 commits.
  - Three document rubrics (specification / claims / abstract) plus a novelty–inventiveness–utility assessment, each dimension weighted.
  - *Hard gates*: an abstract over 300 characters is capped at 59 regardless of other dimensions.
  - Structured `scorecard.json` + Chinese-language report; served over HTTP so the drafting pipeline can call it — closing the generate → evaluate → revise loop.
- **Algorithm Intern, ShuiMuFenZi (AI drug discovery)** — LLM-based relation extraction from literature PDFs into a biomedical knowledge graph; prompt design and multi-model evaluation.
- **Document-parsing benchmark** — Comparative evaluation of local PDF-parsing pipelines (MinerU, DeepDoc) for a financial document QA scenario.
- **Production model validation** — Online validation of a vision service: threshold tuning, verifying config rollouts took effect, and metric regression against defined criteria.
- **RAG knowledge-base service (private repo · in progress)** — FastAPI + pgvector + async SQLAlchemy + object storage; health checks and containerised orchestration in place, retrieval and generation pipeline still being implemented — not yet at a demonstrable state.

---

**Skills**

Python · JavaScript/TypeScript · SQL ｜ LLM Agents · RAG (hybrid retrieval, RRF, reranking) · Prompt Engineering · Multi-model Evaluation ｜ FastAPI · Flask · LangGraph · PyTorch ｜ PostgreSQL/pgvector · Milvus · Elasticsearch · MemGraph · Supabase ｜ Git · Docker · Linux · Testing & Regression · Rule-based evaluation (reproducible & traceable)

</details>
