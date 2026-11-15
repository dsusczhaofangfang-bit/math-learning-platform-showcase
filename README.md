# math-learning-platform-showcase
# 数学学习协作平台

**An Independent Educational Technology Project | 独立教育科技项目**

A collaborative learning platform designed to connect university mathematics courses, learning resources, and students.

一个面向大学数学课程的学习协作平台，旨在连接课程教学进度、数学题目资源与学生之间的交流。

<p align="center">
  <strong>Learn Together. Share Knowledge. Build Connections.</strong>
</p>

---

## 01. Overview | 项目概述

### English

The Mathematics Learning Collaboration Platform is an independent educational technology project designed for university students.

The platform aims to provide a shared space where students from different classes can:

- Share and explore mathematics course progress.
- Collect and organize mathematical problems.
- Discuss mathematical questions and learning experiences.
- Review course materials and prepare for examinations collaboratively.

The project focuses on improving information sharing and peer-to-peer learning within university mathematics courses.

### 中文

数学学习协作平台是一个面向大学生的独立教育科技项目。

项目希望建立一个跨班级的数学学习协作空间，让学生能够：

- 共享和查看不同班级的数学课程教学进度。
- 收集、整理和交流数学题目。
- 围绕数学问题开展在线讨论。
- 协同整理课程资料，进行复习与备考。

项目希望通过数字化工具改善大学数学课程中的信息共享与学生协作学习体验。

---

## 02. Motivation | 项目背景

University mathematics courses often involve multiple classes studying the same subjects, while course progress, problem resources, and learning discussions may remain scattered across different communication channels.

大学数学课程通常涉及多个教学班级，但不同班级的教学进度、题目资源和学习讨论往往分散在不同的信息渠道中。

This project explores how a centralized collaborative platform can help students:

- Understand the learning progress of different classes.
- Build a shared collection of mathematical problems.
- Exchange solutions and learning experiences.
- Develop a more organized approach to collaborative review.

本项目尝试通过统一的协作平台，让学生更方便地了解不同班级的教学进度、积累数学题目、交流解题思路，并形成更加系统的协作复习方式。

---

## 03. Core Modules | 核心模块

The platform is designed around four major functional areas.

平台围绕以下四个核心模块进行规划。

| Module | Description |
|---|---|
| Course Progress | 课程教学进度共享 |
| Problem Collection | 数学题目收集与整理 |
| Online Discussion | 数学问题交流与讨论 |
| Collaborative Review | 课程复习与知识协作 |

**Note:** These describe the platform's intended functional scope. They should not be interpreted as confirmation that every module is already fully implemented.

**说明：** 上述内容描述的是平台的目标功能范围，并不代表所有模块均已完成开发。

---

## 04. Technical Architecture | 技术架构

### Backend Architecture | 后端架构

The backend adopts a modular architecture based on Node.js, TypeScript, and Fastify.

后端采用基于 Node.js、TypeScript 和 Fastify 的模块化架构。

```text
Backend Application
│
├── Authentication
│   ├── User Authentication
│   ├── Password Hashing
│   └── Server-side Sessions
│
├── Course Module
│   └── Course-related Routes
│
├── Problem Module
│   └── Problem-related Routes
│
├── Database Layer
│   ├── Drizzle ORM
│   ├── Schema Definitions
│   └── Database Migrations
│
└── Database
    ├── PGlite (Local Mode)
    └── PostgreSQL (Production-oriented Option)
```

### Architecture Design

The backend separates authentication, course-related operations, problem-related operations, and database access into distinct modules.

后端将用户认证、课程相关操作、题目相关操作和数据库访问划分为不同模块，以提高系统的可维护性和扩展能力。

---

## 05. Technology Stack | 技术栈

| Category | Technology |
|---|---|
| Runtime | Node.js |
| Programming Language | TypeScript |
| Backend Framework | Fastify 5 |
| ORM | Drizzle ORM |
| Password Hashing | Argon2id |
| Session Management | Server-side Database Sessions |
| Local Database | PGlite |
| PostgreSQL Support | PostgreSQL via DATABASE_URL |
| Database Management | Schema & Migrations |

### Technical Decisions | 技术选型

**TypeScript**

Provides static typing and improves maintainability as the backend grows.

提供静态类型支持，提高后端代码的可维护性。

**Fastify 5**

Provides a lightweight and modular backend framework.

提供轻量化、模块化的后端开发基础。

**Drizzle ORM**

Used for database schema definitions and database operations.

用于数据库结构定义和数据操作。

**Argon2id**

Used for password hashing rather than storing plaintext passwords.

用于密码哈希处理，避免明文存储用户密码。

**PGlite & PostgreSQL**

The database layer supports local file-based PGlite mode and can switch to PostgreSQL through the `DATABASE_URL` configuration.

数据库层支持基于本地文件的 PGlite 模式，并可以通过 `DATABASE_URL` 配置切换至 PostgreSQL。

---

## 06. Security & Authentication | 安全与用户认证

Security is considered during backend architecture design.

项目在后端架构设计中考虑了基础安全机制。

Implemented design elements include:

- Argon2id password hashing.
- Server-side database-backed sessions.
- Separation of authentication-related routes.
- Database-backed session management.

目前已采用的安全设计包括：

- 使用 Argon2id 进行密码哈希。
- 使用服务端数据库 Session 管理会话。
- 将认证相关路由独立组织。
- 通过数据库管理服务端会话状态。

These mechanisms provide a foundation for further security improvements.

这些机制为后续完善权限管理、会话安全和接口访问控制提供了基础。

---

## 07. Database Design | 数据库设计

The backend currently includes seven database tables.

后端目前包含七张数据库表。

The project uses Drizzle ORM to manage database schemas and migrations.

项目通过 Drizzle ORM 管理数据库 Schema 和迁移。

Database configuration supports two modes:

| Mode | Description |
|---|---|
| Local | PGlite file-based database |
| PostgreSQL | Configurable through `DATABASE_URL` |

The migration and seed-data workflows are included in the backend development process.

项目包含数据库迁移和初始数据准备相关流程。

*Detailed database diagrams and table descriptions can be added here after sensitive implementation details have been reviewed.*

---

## 08. Personal Contributions | 个人贡献

As the project developer, my work has focused on backend architecture and implementation.

作为项目开发者，我主要围绕后端架构设计与工程实现开展工作。

My contributions include:

1. **Backend Architecture**
   - Designed the modular backend structure.
   - Organized authentication, courses, and problems routes.

2. **Database Engineering**
   - Designed and implemented the database schema.
   - Integrated Drizzle ORM.
   - Established database migration workflows.
   - Implemented support for PGlite and PostgreSQL configuration.

3. **Authentication & Security**
   - Integrated Argon2id password hashing.
   - Implemented server-side database session management.

4. **Development & Validation**
   - Built and validated the backend using a temporary project copy.
   - Tested the local database configuration and backend structure.

个人主要负责：

1. **后端架构设计**
   - 设计模块化后端结构。
   - 组织认证、课程和题目相关路由。

2. **数据库工程**
   - 设计并实现数据库结构。
   - 集成 Drizzle ORM。
   - 建立数据库迁移流程。
   - 实现 PGlite 与 PostgreSQL 配置切换支持。

3. **用户认证与安全**
   - 集成 Argon2id 密码哈希。
   - 实现服务端数据库 Session 管理。

4. **开发与验证**
   - 使用临时项目副本搭建并验证后端。
   - 测试本地数据库配置与后端结构。

---

## 09. Development Status | 项目进度

**Current Status: Backend Implemented, Platform Development Ongoing**

**当前状态：后端已完成阶段性实现，平台整体仍在开发中。**

| Component | Status |
|---|---|
| Backend Architecture | Implemented |
| Authentication Module | Implemented |
| Course Routes | Implemented |
| Problem Routes | Implemented |
| Database Schema | Implemented |
| Database Migrations | Implemented |
| PGlite Local Mode | Implemented |
| PostgreSQL Configuration | Supported |
| Complete Frontend Integration | Ongoing / To be verified |
| Full Platform Deployment | Not yet claimed |

The project has established a working backend foundation. Further development is required to complete and validate the full platform experience.

项目已经建立可运行的后端基础，但完整平台的功能集成、部署和整体验证仍需要进一步推进。

---

## 10. Project Preview | 项目展示

Screenshots and diagrams will be added after reviewing and removing any sensitive information.

项目截图与架构图将在完成敏感信息检查后添加。

Suggested materials:

- System architecture diagram
- Backend module overview
- Database relationship diagram
- Application interface screenshots
- Development demonstration video

建议展示：

- 系统总体架构图
- 后端模块结构图
- 数据库关系图
- 应用界面截图
- 项目开发演示视频

---

## 11. Future Work | 后续规划

Potential development directions include:

- Completing frontend and backend integration.
- Improving course progress collaboration.
- Expanding the mathematical problem management system.
- Developing discussion and interaction features.
- Improving access control and permission management.
- Completing deployment and end-to-end testing.

后续计划包括：

- 完善前后端集成。
- 完善课程教学进度协作功能。
- 扩展数学题目管理系统。
- 开发在线讨论与互动功能。
- 完善访问控制与权限管理。
- 完成系统部署和端到端测试。

---

## 12. Privacy & Source Code | 隐私与源代码

This repository is a public project showcase.

The actual application source code is maintained separately in a private repository and is intentionally not published here.

本仓库仅用于公开展示项目背景、技术架构和开发成果。

实际应用源代码独立保存在私有仓库中，不在此公开。

This repository does not grant access to the private implementation.

本仓库不提供私有项目源代码的访问权限。

---

## 13. Disclaimer | 声明

This is an independent student-developed project. It is not an official system of Sun Yat-sen University.

本项目为独立开发的学生项目，并非中山大学官方系统。

---

**Built with curiosity, engineering, and a passion for collaborative learning.**

**以好奇心为起点，以工程实践为方法，让学习连接彼此。**
