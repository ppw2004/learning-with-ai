# 🧠 learning-with-ai

> **与 AI 一同成长：面向生产级智能体工程的“活教材”与评测基准**

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-Strict-blue)
![Docker](https://img.shields.io/badge/Docker-Sandbox-2496ED)
![Neo4j](https://img.shields.io/badge/GraphDB-Neo4j-008CC1)
![Environment](https://img.shields.io/badge/Environment-Ubuntu%20%7C%20ROCm-green)

## 📌 核心愿景 (Vision)

人工智能科班出身的开发者在迈向真实生产环境时，往往面临软件工程（SWE）壁垒。传统的开发教程要么过于偏向 CRUD 业务，要么停留在静态的纯文本概念科普。

`learning-with-ai` 试图打破这一现状。这不仅是一本写给人类开发者的硬核软件工程百科，更是一个**机器可读（Machine-Readable）**、**可交互（Interactive）**、**可自动化评测（Auto-Eval）**的动态图谱系统。

我们将高并发调度、异步 I/O、状态机管理、分布式微服务等底层架构知识，转化为大模型可以直接理解、检索并用于自我纠错的“工程原语”。在这里，人类补齐系统架构短板，AI 练就极客级别的工程直觉。

## 🧩 “六位一体”的知识范式 (The 6-Dimensional Schema)

本项目摒弃了传统的扁平化文档，每一个工程节点均遵循极其严格的 Schema 进行原子化封装。无论是人类阅读还是 GraphRAG 提取，都保持高度的一致性：

1. **核心解释与拓扑定位 (Metadata & Concept):** 带有 YAML Frontmatter 的硬核原理解析，明确该节点在全局知识图谱中的依赖关系。跳过基础废话，直击工程痛点。
2. **可视化运行样例 (Production-grade Example):** 严格遵守开闭原则、强类型提示（Type Hinting）与模块化设计的最佳实践代码（Python/TypeScript）。
3. **错误代码样例 (Anti-Pattern / The Trap):** 刻意构造的高危代码（如：Event Loop 阻塞、状态机死锁），作为评测 AI 的“靶场”。
4. **指导 AI 作业的方法 (Agentic Workflow):** 针对该漏洞的修复策略（Zero-shot / 引入外部图谱上下文 / Chain-of-Thought Prompting）。
5. **AI 实操结果与自动化评分 (Execution Sandbox & Eval):** 基于 Docker 强隔离环境的闭环测试脚本，捕获 `stdout/stderr` 与资源开销，生成客观的 Benchmark 分数。
6. **图谱检索节点 (Graph Integration):** 所有数据无缝接入 Neo4j，支持复杂业务约束下的多跳逻辑关联检索。

## 📂 目录结构 (Directory Structure)

```text
learning-with-ai/
├── 001_concurrency_async_loop/       # 示例：并发与异步状态机死锁
│   ├── README.md                     # 元数据、核心定义与前置依赖
│   ├── example_optimal.py            # 生产级最佳实践 (强类型定义)
│   ├── trap_deadlock.py              # 高频反面教材 (测试靶点)
│   ├── prompt_strategy.txt           # 针对该场景的 RAG/CoT 注入策略
│   └── eval_sandbox/                 # 容器化评测组件
│       ├── Dockerfile
│       └── score_reporter.sh
├── 002_pattern_observer_streaming/   # 示例：观察者模式与大模型流式拦截
├── core_engine/                      # 基础设施与调度器
│   ├── graph_builder/                # Markdown to Neo4j 自动化注入器
│   └── eval_pipeline/                # 沙盒执行与评分引擎
└── docs/                             # 整体知识图谱可视化