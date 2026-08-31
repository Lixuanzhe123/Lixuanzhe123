<div align="center">

# Hi, I'm 李轩喆 👋

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=23&pause=1000&center=true&vCenter=true&width=720&lines=AI+Application+%26+Full-Stack+Engineer;Python+Backend+%7C+RAG+%7C+LangGraph+Agents;Building+Reliable+AI+Products;CS+Student+%40+Zhaoqing+University)](https://git.io/typing-svg)

[![GitHub](https://img.shields.io/badge/GitHub-Lixuanzhe123-181717?logo=github)](https://github.com/Lixuanzhe123)
[![Email](https://img.shields.io/badge/Email-2857259523%40qq.com-2b6cb0?logo=gmail&logoColor=white)](mailto:2857259523@qq.com)

</div>

## About Me

- 🎓 肇庆学院计算机科学与技术本科生（2023.09 - 2027.07）。
- 💼 AI 应用 / 全栈工程师，具备 Python 后端、LLM 应用、RAG、Agent 工作流与前后端分离项目经验。
- 🧠 关注可落地的 AI 系统：知识检索、工具调用、任务编排、可观测性、异常降级与人工审核闭环。
- 🛠️ 熟悉 FastAPI、Django、Flask、Tornado、PostgreSQL、MySQL、Redis、Vue、React 与 Docker。
- 🚀 能够独立完成需求拆解、数据建模、API 设计、前后端开发、部署及线上问题排查。

## Internship Experience

### 广东马可文化有限公司 · AI 全栈开发工程师

`2026.06 - 2026.09` · **马可 AI 内容创作与运营系统**

面向电商内容团队的视频创作与 B站运营平台，覆盖选品、脚本生成、视频制作、账号数据分析及评论互动。我主要负责 B站运营、RAG 评论回复和权限管理模块的设计与全栈开发。

- **评论运营自动化**：将“逐账号登录 → 逐视频巡检 → 复制评论 → 调用 AI”的人工流程，改造成“定时增量抓取 → RAG 检索 → 批量生成草稿 → 人工审核发布”的自动化链路；按同等业务量测算，巡检与草稿生成耗时预计降低约 **80%**，单人处理能力提升约 **4 倍**。
- **LangGraph Agent**：基于 LangGraph（DeepAgents）拆分策略加载、知识检索、草稿生成、规则校验和审核入队节点；通过条件分支处理已回复、知识不足及模型失败等场景，确保单条异常不阻塞批量任务，且模型不能绕过人工审核直接发布。
- **分层 RAG**：基于 PostgreSQL + pgvector 构建全局、账号、视频三级知识库，使用 Qwen Embedding 完成向量化和余弦 Top-K 检索，再向 DeepSeek 注入可核验上下文，降低跨账号回复泛化和事实错误。
- **可观测与降级**：通过 Langfuse 记录节点调用、检索命中、Prompt 版本、模型耗时、Token 消耗及异常；向量或检索服务不可用时降级为基础回复流程，并保留完整失败原因。
- **数据同步与权限安全**：使用 APScheduler、Redis 分布式锁、账号级并发槽位、断点续跑和风控熔断保障多账号同步；设计四级角色体系、前后端一致鉴权与数据范围隔离，并使用 Fernet 保护 Cookie 和模型密钥。

**Tech:** `FastAPI` · `PostgreSQL` · `pgvector` · `Redis` · `APScheduler` · `LangGraph` · `DeepAgents` · `Langfuse` · `RAG` · `DeepSeek` · `React` · `Docker`

## Featured Projects

### [Forum System：带 AI Agent 的智能论坛](https://github.com/Lixuanzhe123/Forum_System)

前后端分离的智能论坛，包含用户认证、帖子、评论、收藏、关注、搜索、分类及后台管理，并集成中文 AI Agent“小轩”。

- Agent 可根据自然语言调用论坛数据工具或 RAG 知识库，完成个人数据查询、热门内容推荐、规则问答及受控发帖。
- 当前公开版本注册 **10 个工具**，支持匿名问答、JWT 身份传递和最近 20 轮窗口记忆。
- RAG 使用智谱 Embedding + Chroma 检索论坛规则，帖子和评论写入前接入 AI 内容安全审核。
- 建立普通用户、管理员和超级管理员三级权限模型，并实现多级评论、递归删除和内容所有权校验。

**Tech:** `Python` · `Tornado` · `Peewee` · `MySQL` · `Redis` · `Vue 2` · `JWT` · `LangChain` · `RAG` · `Chroma` · `ChatZhipuAI`

### [AIwuliu：软硬件一体化智能物流系统](https://github.com/Lixuanzhe123/AIwuliu)

将计算机视觉、机械臂、BLE 智能小车、STM32 固件、物流数据库与 Flask Web 看板整合为完整业务闭环。

- 使用 OpenCV 在 HSV 色彩空间识别红、蓝、绿货物，并根据网格坐标和颜色优先级生成抓取任务。
- 通过 PCA9685 控制机械臂关节与夹爪，利用 BLE 与智能小车同步装载、运输和到达状态。
- `CoreController` 编排“识别 → 抓取 → 装车 → 运输 → 库存更新”流程，SQLite 保存设备与物流记录。
- Flask 看板展示设备状态、库存和物流记录，并支持分页、删除、CSV 导出及出库操作。

**Tech:** `Python` · `OpenCV` · `Flask` · `SQLite` · `BLE` · `STM32` · `PCA9685` · `Embedded C`

### [Flask Ecommerce Admin：电商后台管理系统](https://github.com/Lixuanzhe123/Flask_Ecommerce_Admin)

基于 Flask REST API 与 Vue 3 的前后端分离管理系统，覆盖用户、角色、菜单、商品、订单和数据看板。

- 实现 JWT 登录认证、角色授权、菜单权限、用户管理与密码重置。
- 支持商品分类、属性维护、图片上传、富文本编辑、订单详情和物流信息查询。
- 使用 ECharts 展示首页业务数据，并通过 Vue Router 与 Axios 封装前端路由和请求链路。

**Tech:** `Flask` · `Flask-RESTful` · `SQLAlchemy` · `MySQL` · `JWT` · `Vue 3` · `Element Plus` · `ECharts` · `TinyMCE`

## Tech Stack

<div align="center">

[![My Skills](https://skillicons.dev/icons?i=python,fastapi,django,flask,postgres,mysql,redis,vue,react,js,html,css,docker,nginx,linux,git,github,vscode)](https://skillicons.dev)

</div>

| Area | Technologies |
| --- | --- |
| **Backend** | Python, FastAPI, Django, Flask, Tornado, RESTful API, ORM, Async Programming |
| **AI / Agent** | LangGraph, DeepAgents, LangChain, RAG, Tool Calling, Prompt Engineering, DeepSeek, Qwen Embedding, Langfuse |
| **Data** | PostgreSQL, pgvector, MySQL, Redis, SQLite, Chroma |
| **Frontend** | Vue 2/3, React, HTML, CSS, ES6+, Axios, Element Plus |
| **Engineering** | Docker, Nginx, APScheduler, Git, Linux, Tencent Cloud CVM |
| **Crawler** | Requests, Selenium, Scrapy, Data Parsing and Cleaning |

## Honors & Certifications

- 计算机软件著作权：生成式 AI 学习分析平台软件 V1.0（登记号：`2026SR0262670`）。
- 计算机设计大赛粤港澳大湾区赛三等奖。
- 广东省第十三届蓝桥杯全国软件大赛 C/C++ 程序设计大学 B 组三等奖。

## GitHub Stats

<div align="center">

![Lixuanzhe123's GitHub stats](https://github-readme-stats-one-bice.vercel.app/api?username=Lixuanzhe123&show_icons=true&theme=transparent&hide_border=true)

![Top Languages](https://github-readme-stats-one-bice.vercel.app/api/top-langs/?username=Lixuanzhe123&layout=compact&theme=transparent&hide_border=true)

</div>

## Current Focus

- 构建具备知识检索、工具调用、条件分支、人工审核和失败降级能力的 Agent 工作流。
- 提升 RAG 的检索质量、事实一致性、可观测性与多租户数据隔离能力。
- 持续完善 Python 后端、全栈工程化、服务部署和系统稳定性实践。

---

<div align="center">

**Thanks for visiting. Feel free to explore my repositories or contact me by email.**

</div>
