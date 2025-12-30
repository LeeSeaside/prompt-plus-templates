# Frontend API - 开发提示词

## 使用方法
1. 将后端接口文档放入 `skills/frontend_api/input/`
2. 复制以下提示词发送给 AI

---

## 快速版
```
使用 frontend_api 技能，读取 input 目录的接口文档，生成前端 API 代码和类型定义。
```

## 详细版
```
请执行 frontend_api 对接任务：

1. 加载技能包 `.ai-workspace/skills/frontend_api/`
2. 读取 `input/` 目录中的接口文档
3. 生成代码：
   - TypeScript 类型定义（请求参数、响应数据）
   - API 调用函数（遵循项目命名规范）
4. 在 `output/` 目录生成对接文档

对接文档包含：生成的文件列表、接口对照表。
```
