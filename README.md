# 🤖 AI Agent 实战指南

> 从零开始，用 TypeScript 手搓一个能干的 Agent——不抄论文，只讲干货。

---

## 🎯 这本书在讲什么？

市面上的 Agent 教程要么太学术（公式满天飞），要么太浅（调个 API 就说学会了）。

这本书走**中间路线**：
- **理论：** 够用就行，不搞数学公式轰炸
- **代码：** 每章都有**完整可运行的 TypeScript 项目**
- **实战：** 从零手搓，不依赖 LangChain 黑箱

---

## 🗂️ 目录（原创结构）

### 第一阶段：理解 Agent（What & Why）

**第1章：Agent 不是套壳 Chatbot**
- 1.1 从"问答"到"行动"：Agent 的核心差异
- 1.2 一个最小 Agent 长什么样？（50 行代码跑起来）
- 1.3 主流 Agent 框架对比：LangChain / AutoGen / 手搓
- **代码案例：** `minimal-agent/` — 不用任何框架，纯 SDK 调用

**第2章：Agent 的三大件——Memory / Tool / Planner**
- 2.1 Memory：让 Agent 记住上一句说了啥
- 2.2 Tool：让 Agent 能"动手"查天气、跑代码、搜网页
- 2.3 Planner：让 Agent 会"思考"下一步干什么
- **代码案例：** `three-parts-agent/` — 把三大件拆开写，看懂每一行

---

### 第二阶段：单智能体实战（Single Agent）

**第3章：Function Calling 完全指南**
- 3.1 Tool Schema 怎么写才不报错？
- 3.2 并行调用多个 Tool（天气+搜索一起跑）
- 3.3 Tool 执行失败怎么办？（重试 + 降级策略）
- **代码案例：** `weather-agent/` — 查天气 + 推荐穿衣，完整可运行

**第4章：ReAct —— 让 Agent 学会"思考-行动-观察"**
- 4.1 ReAct 论文精华（不读论文也能懂）
- 4.2 手搓 ReAct Loop（不用 LangChain）
- 4.3 如何控制 Agent 别"死循环"？
- **代码案例：** `react-agent/` — 实现一个完整的 Thought→Action→Observation 循环

**第5章：Memory 系统——让 Agent 有"记性"**
- 5.1 短期记忆：Message 历史怎么管？
- 5.2 长期记忆：把对话存进向量数据库（pgvector）
- 5.3 Memory 压缩：Token 不够用时怎么办？
- **代码案例：** `memory-agent/` — 带记忆的聊天机器人，重启不忘记

---

### 第三阶段：多智能体协作（Multi-Agent）

**第6章：为什么需要多个 Agent？（分工原理）**
- 6.1 一个 Agent 干所有活 vs 各司其职
- 6.2 Multi-Agent 的三种模式：Handoff / Routing / Orchestrator
- 6.3 通信方式：消息传递 vs 共享状态
- **代码案例：** `multi-agent-intro/` — 一个 Orchestrator 调度两个 Worker

**第7章：手搓 Multi-Agent 系统（不依赖框架）**
- 7.1 Agent 注册与发现
- 7.2 消息总线设计
- 7.3 错误处理：某个 Agent 挂了怎么办？
- **代码案例：** `mini-autogen/` — 200 行代码实现一个迷你版 AutoGen

**第8章：生产级 Multi-Agent 架构**
- 8.1 用 Claude Code SDK 搭建 Agent 集群
- 8.2 状态持久化（Agent 宕机不丢进度）
- 8.3 监控与调试（怎么知道哪个 Agent 在摸鱼？）
- **代码案例：** `production-multi-agent/` — 完整可部署的多 Agent 系统

---

### 第四阶段：进阶技术（RAG / Evaluation / Safety）

**第9章：RAG + Agent —— 让 Agent 有"外脑"**
- 9.1 RAG 基本原理（不搞玄学）
- 9.2 Agent 主动决定"要不要查知识库"
- 9.3 向量数据库选型：pgvector / Pinecone / Weaviate
- **代码案例：** `rag-agent/` — 让 Agent 能查你的私有文档

**第10章：如何评估 Agent 好不好用？（Evaluation）**
- 10.1 为什么准确率不适合 Agent？
- 10.2 用 LLM 评估 LLM（LLM-as-Judge）
- 10.3 构建测试集：人工标注 vs 自动生成
- **代码案例：** `agent-eval/` — 一个完整的 Agent 评估框架

**第11章：Agent 安全——别让它删你数据库**
- 11.1 Tool 权限控制（沙箱执行）
- 11.2 Prompt 注入防护
- 11.3 敏感操作二次确认（Human-in-the-loop）
- **代码案例：** `safe-agent/` — 带权限控制的 Agent 模板

---

### 第五阶段：落地实战（Case Studies）

**第12章：案例1——智能客服 Agent**
- 需求分析：多轮对话 + 查订单 + 改地址
- 架构设计：Router + Specialist Agents
- 完整代码 + 部署方案

**第13章：案例2——代码审查 Agent**
- 需求分析：自动 Review PR + 给出修改建议
- 架构设计：Git Webhook + Agent 触发
- 完整代码 + GitHub Actions 集成

**第14章：案例3——研究团队 Agent**
- 需求分析：自动搜索论文 + 生成周报
- 架构设计：Crawler Agent + Summarizer Agent + Writer Agent
- 完整代码 + 定时任务配置

---

### 附录

- **附录A：TypeScript 类型定义大全** — 所有 Tool / Message / AgentState 的类型
- **附录B：常用 Tool 实现** — 搜索 / 爬虫 / 代码执行 / 数据库查询
- **附录C：部署 Checklist** — 从本地到生产的环境变量、监控、日志
- **附录D：论文速查表** — ReAct / CoT / ToT 核心思想一句话总结

---

## 🛠️ 技术栈

| 类别 | 选择 | 原因 |
|------|------|------|
| **语言** | TypeScript | 类型安全 + 代码提示友好 |
| **LLM SDK** | Claude Code SDK | 本书主角，深度讲解 |
| **向量数据库** | pgvector | 免费 + 不用新装服务 |
| **部署** | Vercel / Docker | 前端用 Vercel，后端用 Docker |

---

## 📊 进度

- [x] 第1章：Agent 不是套壳 Chatbot（撰写中）
- [ ] 第2章：Agent 的三大件
- [ ] 第3章：Function Calling 完全指南
- [ ] ...

---

**最后更新：** 2026-05-28
