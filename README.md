<div align="center">

# 杨琪俊 · Nicholas Zhao

**大模型应用工程 ｜ LLM Agent · RAG · 非结构化数据处理**

北京科技大学 · 人工智能 · 硕士在读 · 北京

📧 **15623221569@163.com** 　·　 🐙 **[github.com/NicholasZhao-zhenglin](https://github.com/NicholasZhao-zhenglin)** 　·　 🌐 **你的个人主页**

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

## 工程与实习经历

**水木分子 · 算法实习生** — 基于 LLM 从文献 PDF 中抽取疾病–通路关系，构建生物医学知识图谱；负责抽取模块的 prompt 设计与多模型对比评估。

**文档解析方案选型** — 对 MinerU / DeepDoc 等本地 PDF 解析方案做效果对比与选型评估，用于金融文档问答场景。

**模型服务线上验证** — 参与视觉识别服务的线上验证：阈值调优、配置变更的生效验证与指标回归，按确定的判据（配置校验 + 指标对比）判断改动是否达标，而非凭观感。

**专利文本工具** — 专利披露材料生成工具，多项目并行，接入自建模型端点。

---

## 技术栈

**语言**　Python · JavaScript / TypeScript · SQL · HTML/CSS

**大模型**　LLM Agent 设计 · RAG（混合检索 / RRF 融合 / 重排）· Prompt Engineering · 多模型评估 · OpenAI 兼容接口

**框架**　FastAPI · Flask · LangGraph · PyTorch

**数据**　Milvus · Elasticsearch · MemGraph · PostgreSQL / Supabase

**工程**　Git · Docker · Linux · 单元测试与回归测试 · 配置管理与灰度验证

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

- **Algorithm Intern, ShuiMuFenZi (AI drug discovery)** — LLM-based relation extraction from literature PDFs into a biomedical knowledge graph; prompt design and multi-model evaluation.
- **Document-parsing benchmark** — Comparative evaluation of local PDF-parsing pipelines (MinerU, DeepDoc) for a financial document QA scenario.
- **Production model validation** — Online validation of a vision service: threshold tuning, verifying config rollouts took effect, and metric regression against defined criteria.
- **Patent disclosure tooling** — Generation tool for patent disclosure drafts, multi-project, self-hosted model endpoint.

---

**Skills**

Python · JavaScript/TypeScript · SQL ｜ LLM Agents · RAG (hybrid retrieval, RRF, reranking) · Prompt Engineering · Multi-model Evaluation ｜ FastAPI · Flask · LangGraph · PyTorch ｜ Milvus · Elasticsearch · MemGraph · PostgreSQL/Supabase ｜ Git · Docker · Linux · Testing & Regression

</details>
