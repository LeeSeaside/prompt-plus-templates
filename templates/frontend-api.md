---
name: frontend-api
description: 生成前端API对接开发提示词
category: frontend
outputFileName: frontend-api-prompt.md
---

# 前端API对接提示词生成器

## 任务
请分析当前前端项目的代码结构和规范，生成一份用于前端 API 对接开发的提示词。

---

## 分析步骤

### 1. 项目结构分析
- API 文件存放位置
- HTTP 客户端（axios / fetch / ky 等）
- 请求封装方式
- 类型定义文件位置

### 2. 代码风格分析
- 文件命名规范（如：xxxApi.ts / xxx.api.ts）
- 函数命名规范（如：getXxxList / fetchXxx）
- TypeScript 类型定义方式
- 导出方式（命名导出 / 默认导出）

### 3. 请求配置分析
- baseURL 配置方式
- 请求拦截器逻辑
- 响应拦截器逻辑
- Token 处理方式
- 错误处理方式

### 4. 类型定义规范
- 请求参数类型命名（如：XxxParams / XxxReq）
- 响应数据类型命名（如：XxxResult / XxxRes）
- 通用响应包装类型
- 分页类型定义

---

## 输出要求

请根据以上分析，生成一份完整的前端 API 对接提示词，格式如下：

```markdown
# [项目名] 前端API对接开发规范

## 项目信息
- HTTP客户端：[axios/fetch/ky]
- API目录：[路径]
- 类型定义目录：[路径]

## 命名规范
- 文件命名：[规范]
- 函数命名：[规范]
- 类型命名：[规范]

## 代码模板

### API 文件模板
[提供标准 API 文件模板]

### 类型定义模板
[提供标准类型定义模板]

## 使用说明

当需要对接后端接口时，请提供接口文档（Swagger/接口列表），我将：
1. 根据接口文档生成 API 调用代码
2. 生成对应的 TypeScript 类型定义
3. 生成对接文档保存到 `docs/api/[模块名].md`
```

## 保存位置

请将生成的正式提示词保存到: `.prompts/generated/frontend-api.md`

---
请开始分析当前前端项目，生成具体的 API 对接开发提示词。
