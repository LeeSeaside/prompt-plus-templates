# Backend API - 开发提示词

## 使用方法
1. 将接口文档放入 `skills/backend_api/input/`
2. 复制以下提示词发送给 AI

---

## 快速版
```
使用 backend_api 技能，读取 input 目录文档，生成 Entity + Service + Controller 代码。
```

## 详细版
```
请执行 backend_api 开发任务：

1. 加载技能包 `.ai-workspace/skills/backend_api/`
2. 读取 `input/` 目录中的接口文档
3. 按照 manifest.md 流程生成代码：
   - Entity 实体类（含注解、字段映射）
   - Service 接口和实现类（含事务、异常处理）
   - Controller 控制器（含路由、参数校验、Swagger）
4. 在 `output/` 目录生成 execution_log.md

完成后列出所有变更文件。
```
