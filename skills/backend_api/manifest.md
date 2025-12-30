# Skill Manifest: Backend API Development

## 技能描述
生成完整后端接口开发代码（Entity + Service + Controller 三层架构），并输出前端对接文档。

## 核心职责
根据 API 需求文档，在项目中生成符合规范的 Entity、Service、Controller 代码，同时生成供前端对接的接口文档。

## 执行协议

### 1. Context Check (上下文检查)
- 读取 `context.md` 获取项目配置
- 如果未初始化，**终止任务**并提示："请先执行项目初始化扫描"

### 2. Input Acquisition (获取需求)
- 扫描 `skills/backend_api/input/` 目录
- 读取 API 需求文档（接口定义、数据模型等）

### 3. Code Generation (代码生成)
按以下顺序生成代码：

#### 3.1 Entity 实体层
- 根据 `context.md` 中的 Entity Path 定位存放位置
- 遵循项目的实体命名规范
- 包含：主键、字段映射、关联关系、通用字段（创建时间等）

#### 3.2 Service 服务层
- 生成 Service 接口和实现类
- 遵循项目的依赖注入方式
- 包含：CRUD 方法、事务管理、异常处理

#### 3.3 Controller 控制层
- 生成 RESTful 接口
- 遵循项目的响应包装规范
- 包含：路由定义、参数校验、Swagger 文档注解

### 4. Documentation Output (文档输出)

#### 4.1 执行日志
在 `skills/backend_api/output/` 生成 `execution_log.md`，记录：
- 新增的文件列表
- 数据库表结构变更
- 注意事项

#### 4.2 前端对接文档（重要）
在 `skills/backend_api/output/` 生成 `api-spec-[模块名].md`，格式如下：

```markdown
# [模块名] 接口文档

## 基础信息
- Base URL: /api/v1/[模块]
- 生成时间: [时间]

## 数据模型

### [实体名]
| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| id | number | - | 主键 |
| name | string | ✓ | 名称 |
| ... | ... | ... | ... |

## 接口列表

### 1. 获取列表
- **URL**: GET /api/v1/[模块]
- **Query 参数**:
  | 参数 | 类型 | 必填 | 说明 |
  |------|------|------|------|
  | page | number | ✗ | 页码 |
  | pageSize | number | ✗ | 每页数量 |
- **响应**:
  ```json
  {
    "code": 200,
    "data": {
      "list": [...],
      "total": 100
    }
  }
  ```

### 2. 获取详情
- **URL**: GET /api/v1/[模块]/:id
- **响应**: ...

### 3. 新增
- **URL**: POST /api/v1/[模块]
- **Body 参数**: ...
- **响应**: ...

### 4. 更新
- **URL**: PUT /api/v1/[模块]/:id
- **Body 参数**: ...
- **响应**: ...

### 5. 删除
- **URL**: DELETE /api/v1/[模块]/:id
- **响应**: ...
```

> 💡 此文档可直接复制到 `skills/frontend_api/input/` 供前端对接使用

## 约束条件
- 严格遵循 `context.md` 中定义的目录结构和代码风格
- 禁止臆造依赖库
- 复用现有项目结构
- **必须生成前端对接文档**
