# prompt-plus 官方模板仓库

这是 prompt-plus 的官方模板仓库，包含常用的提示词模板。

## 目录结构

```
templates/
├── README.md
├── backend-api.md         # 后端接口开发
├── frontend-api.md        # 前端API对接
└── backend-from-ui.md     # 根据前端页面生成后端接口需求
```

## 模板格式

每个模板是一个 Markdown 文件，使用 Front Matter 定义元信息：

```markdown
---
name: 模板名称
description: 模板描述
category: 分类（backend/frontend/fullstack）
outputFileName: 输出文件名.md
---

# 模板标题

模板内容...
```

## 自建模板仓库

1. Fork 本仓库或创建新仓库
2. 在 `templates/` 目录下添加 `.md` 模板文件
3. 使用 `prompt-plus repo add` 添加你的仓库

```bash
# 添加自定义仓库
prompt-plus repo add my-templates https://github.com/xxx/my-templates.git

# 同步模板
prompt-plus repo sync my-templates

# 使用模板
prompt-plus list -r my-templates
prompt-plus use my-template -r my-templates
```

## 贡献模板

欢迎提交 PR 贡献新模板！

### 模板编写规范

1. `name` - 简短的英文名，使用小写和连字符
2. `description` - 简洁的中文描述
3. `category` - 分类：backend / frontend / fullstack / devops / other
4. 内容应包含：
   - 任务说明
   - 分析步骤
   - 输出格式要求
   - 保存位置建议
