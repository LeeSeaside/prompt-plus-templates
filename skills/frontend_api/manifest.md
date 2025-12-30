# Skill Manifest: Frontend API Integration

## 技能描述
根据后端接口文档，生成前端 API 调用代码和 TypeScript 类型定义

## 核心职责
解析 Swagger/OpenAPI 文档或接口列表，生成符合项目规范的 API 调用代码。

## 执行协议

### 1. Context Check (上下文检查)
- 读取 `context.md` 获取前端项目配置
- 如果未初始化，**终止任务**并提示："请先执行项目初始化扫描"

### 2. Input Acquisition (获取需求)
- 从 `skills/frontend_api/input/` 读取接口文档
- 支持格式：
    - Swagger JSON / OpenAPI YAML
    - Markdown 接口列表
    - **backend_api 输出的 `api-spec-*.md`**（推荐，可直接从 `skills/backend_api/output/` 复制）

### 3. Code Generation (代码生成)

#### 3.1 类型定义生成
- 根据 `context.md` 中的 Types Path 定位存放位置
- 生成请求参数类型（XxxParams / XxxReq）
- 生成响应数据类型（XxxResult / XxxRes）
- 复用项目的通用类型（分页、响应包装等）

#### 3.2 API 函数生成
- 根据 `context.md` 中的 API Path 定位存放位置
- 遵循项目的命名规范（getXxxList / fetchXxx）
- 使用项目的 HTTP 客户端封装
- 包含完整的 TypeScript 类型标注

#### 3.3 代码示例
```typescript
// 生成的 API 文件示例
import request from '@/utils/request'
import type { XxxParams, XxxResult } from './types'

/** 获取列表 */
export function getXxxList(params: XxxParams) {
    return request.get<XxxResult>('/api/xxx', { params })
}
```

### 4. Documentation Output (文档输出)
在 `skills/frontend_api/output/` 生成对接文档，记录：
- 生成的文件列表
- 接口对照表（后端接口 → 前端函数）
- 类型定义说明

## 约束条件
- 严格遵循项目的 API 封装方式
- 类型定义要完整准确
- 复用项目现有的通用类型
