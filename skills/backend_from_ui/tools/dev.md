# Backend from UI - 开发提示词

## 使用方法
1. 在 `input/` 目录放入页面路径清单，或直接告诉 AI 页面路径
2. 复制以下提示词发送给 AI

---

## 快速版
```
使用 backend_from_ui 技能，分析 [src/views/xxx/index.vue] 页面，生成后端接口需求文档。
```

## 详细版
```
请执行 backend_from_ui 分析任务：

1. 加载技能包 `.ai-workspace/skills/backend_from_ui/`
2. 分析指定的前端页面文件
3. 提取信息：
   - 表格列定义 → 字段列表
   - 搜索表单 → 查询参数
   - 操作按钮 → 接口需求
   - 表单字段 → 数据模型
4. 在 `output/` 目录生成接口需求文档

文档格式包含：数据模型、接口列表、业务规则、字典数据。
```
