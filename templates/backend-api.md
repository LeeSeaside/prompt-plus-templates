---
name: backend-api
description: 生成完整后端接口开发提示词（Entity + Service + Controller）
category: backend
outputFileName: backend-api-prompt.md
---

# 后端接口开发提示词生成器

## 任务
请分析当前项目的代码结构和规范，生成一份完整的后端接口开发提示词，涵盖 Entity、Service、Controller 三层。

---

## 第一部分：项目整体分析

### 1.1 技术栈识别
- 框架：Spring Boot / Express / NestJS / 其他
- ORM：JPA / MyBatis / MyBatis-Plus / TypeORM / Prisma
- 数据库类型
- 构建工具

### 1.2 项目结构
- 各层代码存放位置
- 包/模块命名规范
- 配置文件位置

---

## 第二部分：Entity 实体层分析

### 2.1 代码位置与命名
- Entity 存放路径
- 类命名规范（如：XxxEntity / Xxx）
- 表名映射规则

### 2.2 注解规范
- 主键注解与生成策略
- 字段映射注解
- 关联关系注解

### 2.3 通用字段（基类）
- 是否有 BaseEntity
- 创建时间、更新时间
- 创建人、更新人
- 逻辑删除、乐观锁

---

## 第三部分：Service 服务层分析

### 3.1 代码位置与命名
- Service 接口存放路径
- Service 实现类存放路径
- 命名规范（XxxService / XxxServiceImpl）

### 3.2 代码风格
- 依赖注入方式
- 事务管理方式
- 方法命名规范

### 3.3 业务规范
- 异常处理方式
- 日志记录规范
- DTO 与 Entity 转换方式

---

## 第四部分：Controller 控制层分析

### 4.1 代码位置与命名
- Controller 存放路径
- 类命名规范
- 路径命名风格

### 4.2 注解规范
- 类级别注解
- 方法级别注解
- 参数注解（@RequestBody, @PathVariable 等）

### 4.3 响应规范
- 统一响应包装类
- 成功/失败响应格式
- 分页响应格式

### 4.4 其他
- Swagger/OpenAPI 文档注解
- 参数校验方式
- 权限控制注解

---

## 输出要求

请根据以上分析，生成一份完整的后端接口开发提示词，格式如下：

```markdown
# [项目名] 后端接口开发规范

## 项目信息
- 框架：xxx
- ORM：xxx
- 数据库：xxx

## 一、Entity 开发规范

### 存放位置
xxx

### 命名规范
xxx

### 代码模板
[提供标准 Entity 模板]

## 二、Service 开发规范

### 存放位置
xxx

### 命名规范
xxx

### 代码模板
[提供标准 Service 接口和实现类模板]

## 三、Controller 开发规范

### 存放位置
xxx

### 命名规范
xxx

### 代码模板
[提供标准 Controller 模板，包含 CRUD 接口]

## 四、开发流程

1. 创建 Entity
2. 创建 Service 接口和实现
3. 创建 Controller
4. 添加 Swagger 文档
5. 编写单元测试（可选）

## 五、使用示例

当需要开发 [用户管理] 接口时：
1. ...
2. ...
```

## 保存位置

请将生成的正式提示词保存到: `.prompts/generated/backend-api.md`

---
请开始分析当前项目，生成具体的后端接口开发提示词。
