# 后端 + Agent 实习学习路线图

## 📅 阶段一：后端基础夯实 (1-2 周)
**目标**: 掌握构建稳定后端服务所需的核心技能

### 1.1 编程语言深度
- [ ] **Python 高级特性**
  - 异步编程 (`asyncio`, `aiohttp`, `FastAPI` 异步接口)
  - 装饰器、上下文管理器、元类
  - 类型提示 (`typing` 模块) 与 Pydantic 数据验证
- [ ] **Go 语言基础 (可选但加分)**
  - Goroutine 与 Channel 并发模型
  - Gin/Echo 框架基础

### 1.2 Web 框架与 API 设计
- [ ] **FastAPI / Flask**
  - 路由、依赖注入、中间件
  - 请求/响应模型定义
  - 自动文档生成 (Swagger/ReDoc)
- [ ] **API 设计规范**
  - RESTful 最佳实践 (资源命名、状态码、版本控制)
  - GraphQL 基础 (Schema, Resolvers, Apollo Server)
  - gRPC 基础 (Protocol Buffers, 服务定义)

### 1.3 数据库与存储
- [ ] **关系型数据库 (PostgreSQL)**
  - SQL 进阶 (窗口函数、CTE、索引优化)
  - ORM 使用 (SQLAlchemy / Prisma)
  - 事务管理与连接池
- [ ] **NoSQL 与缓存**
  - Redis 数据结构与应用场景 (缓存、消息队列、分布式锁)
  - MongoDB 基础 (文档模型、聚合管道)

---

## 🤖 阶段二：Agent 核心架构 (2-3 周)
**目标**: 理解并实现基于 LLM 的智能代理系统

### 2.1 LLM 交互基础
- [ ] **Prompt Engineering**
  - Zero-shot / Few-shot Prompting
  - Chain of Thought (CoT)
  - ReAct (Reasoning + Acting) 模式
  - Structured Output (JSON Mode, Function Calling)
- [ ] **LLM API 集成**
  - OpenAI SDK / Anthropic SDK
  - 流式响应处理 (SSE)
  - Token 计费与限流策略

### 2.2 Agent 框架实战
- [ ] **LangChain 核心概念**
  - Chains (Sequential, Router, Transform)
  - Agents (Tool calling, ReAct Agent)
  - Memory (ConversationBuffer, VectorStoreRetrieverMemory)
  - Callbacks (日志、监控、调试)
- [ ] **LangGraph (状态机工作流)**
  - State Graph 定义
  - Condition Edges (条件分支)
  - Human-in-the-loop (人工介入)
  - 持久化检查点 (Checkpointer)
- [ ] **LlamaIndex (可选)**
  - 数据连接器 (Loaders)
  - 索引策略 (Vector, Keyword, Tree)
  - 查询引擎 (Query Engines)

### 2.3 工具调用 (Function Calling)
- [ ] **自定义工具开发**
  - 定义 Tool Schema
  - 错误处理与重试机制
  - 多工具协同调度
- [ ] **内置工具集成**
  - 搜索工具 (Tavily, SerpAPI)
  - 代码解释器 (Sandbox 环境)
  - 文件操作 (PDF 解析、Excel 处理)

---

## 🔍 阶段三：RAG 与知识库系统 (2 周)
**目标**: 构建基于私有数据的企业级问答系统

### 3.1 向量数据库
- [ ] **主流向量库选型**
  - PostgreSQL + pgvector (推荐，易部署)
  - Qdrant / Milvus / Weaviate (专用向量库)
  - Chroma (轻量级，适合原型)
- [ ] **向量操作**
  - Embedding 模型选择 (text-embedding-3-small, m3e, bge)
  - 相似度计算 (Cosine, Dot Product, L2)
  - 混合检索 (Hybrid Search: 向量 + 关键词)
  - 元数据过滤 (Metadata Filtering)

### 3.2 RAG 流水线构建
- [ ] **数据预处理**
  - 文档加载 (PDF, Word, Markdown, HTML)
  - 文本分块 (Chunking 策略: 固定大小、递归、语义分块)
  - 数据清洗 (去噪、格式化)
- [ ] **检索增强生成**
  - 检索器优化 (Multi-query, Hypothetical Questions)
  - 重排序 (Rerank: Cohere, BGE-Reranker)
  - 上下文压缩 (Contextual Compression)
  - 引用溯源 (Citation Tracking)

### 3.3 高级 RAG 技巧
- [ ] **优化策略**
  - Parent Document Retriever
  - Self-RAG (自我反思检索)
  - Agentic RAG (用 Agent 控制检索流程)
- [ ] **评估指标**
  - 检索准确率 (Recall@K, MRR)
  - 生成质量 (Faithfulness, Answer Relevance)
  - 使用 RAGAS / TruLens 进行自动化评估

---

## 🛠️ 阶段四：工程化与部署 (1-2 周)
**目标**: 将原型转化为生产级应用

### 4.1 测试与质量保障
- [ ] **单元测试**
  - pytest / unittest
  - Mock LLM 响应 (避免真实调用)
  - 测试 Agent 决策逻辑
- [ ] **集成测试**
  - E2E 测试流程
  - 评估集构建 (Golden Dataset)

### 4.2 可观测性
- [ ] **日志与追踪**
  - LangSmith / LangFuse 集成
  - OpenTelemetry 标准
  - 结构化日志 (JSON Log)
- [ ] **监控告警**
  - 延迟监控 (P95, P99)
  - Token 消耗统计
  - 错误率追踪

### 4.3 容器化与部署
- [ ] **Docker**
  - 多阶段构建优化镜像大小
  - Docker Compose 编排 (App + DB + VectorStore)
- [ ] **Kubernetes 基础**
  - Deployment, Service, ConfigMap
  - HPA (自动扩缩容)
- [ ] **CI/CD**
  - GitHub Actions 自动化测试与部署

---

## 🚀 阶段五：实战项目 (2-3 周)
**目标**: 完成一个完整的端到端项目，作为简历亮点

### 项目选题建议
1. **企业知识库问答机器人**
   - 支持多格式文档上传
   - 混合检索 + Rerank
   - 多轮对话记忆
   - 引用溯源展示

2. **智能数据分析 Agent**
   - 自然语言转 SQL (Text-to-SQL)
   - 自动生成图表 (Matplotlib/Plotly)
   - 数据洞察报告生成

3. **多 Agent 协作系统**
   - 角色分工 (研究员、写作者、审核员)
   - LangGraph 状态机编排
   - 人工审核节点

### 项目要求
- [ ] 代码规范 (PEP8, Type Hints)
- [ ] 完整 README (架构图、部署指南、API 文档)
- [ ] 单元测试覆盖率 > 70%
- [ ] 部署到云端 (AWS/GCP/Azure 或 Vercel/Railway)
- [ ] 性能优化 (缓存、异步、并发)

---

## 📚 推荐学习资源

### 官方文档
- FastAPI: https://fastapi.tiangolo.com/
- LangChain: https://python.langchain.com/
- LangGraph: https://langchain-ai.github.io/langgraph/
- LlamaIndex: https://docs.llamaindex.ai/
- pgvector: https://github.com/pgvector/pgvector

### 在线课程
- DeepLearning.AI: "LangChain for LLM Application Development"
- Coursera: "Generative AI with Large Language Models"

### 开源项目参考
- langchain-ai/langchain
- langchain-ai/langgraph
- run-llama/llama_index
- vllm-project/vllm

### 面试准备
- 系统设计: 如何设计一个高并发 RAG 系统？
- 代码考核: 实现一个简单的 ReAct Agent
- 场景题: 如何处理 RAG 中的幻觉问题？

---

## ✅ 学习检查清单

| 模块 | 关键技能 | 掌握程度 |
|------|----------|----------|
| 后端基础 | FastAPI, PostgreSQL, Redis | ⬜⬜⬜⬜⬜ |
| LLM 交互 | Prompt Engineering, Function Calling | ⬜⬜⬜⬜⬜ |
| Agent 框架 | LangChain, LangGraph | ⬜⬜⬜⬜⬜ |
| RAG 系统 | 向量数据库, 检索优化, Rerank | ⬜⬜⬜⬜⬜ |
| 工程化 | Docker, 测试, 可观测性 | ⬜⬜⬜⬜⬜ |
| 实战项目 | 完整端到端项目 | ⬜⬜⬜⬜⬜ |

---

**💡 学习建议**:
1. **边学边做**: 每个知识点都要配合代码实践，不要只看不练
2. **由简入繁**: 先实现最小可行产品 (MVP)，再逐步添加高级功能
3. **重视文档**: 养成良好的注释和文档习惯
4. **关注社区**: 订阅 LangChain Blog, Hugging Face Daily Paper
5. **准备作品集**: 将项目代码整理到 GitHub，撰写技术博客

**🎯 下一步行动**:
选择一个感兴趣的项目方向，开始第一阶段的学习！
