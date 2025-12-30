## 技能包仓库格式

如果你想创建自己的技能包仓库，请按以下格式组织：

```
your-repo/
└── skills/
    ├── backend_api/
    │   ├── manifest.md      # 执行流程和规范（必需）
    │   ├── context.md       # 项目配置模板（必需）
    │   ├── input/           # 输入文档目录
    │   │   └── .gitkeep
    │   ├── output/          # 输出文档目录
    │   │   └── .gitkeep
    │   └── tools/           # 提示词工具
    │       ├── init.md      # 初始化提示词
    │       └── dev.md       # 开发提示词
    ├── frontend_api/
    │   ├── manifest.md
    │   ├── context.md
    │   └── ...
    └── another_skill/
        └── ...
```

### manifest.md 格式

```markdown
# Skill Manifest: 技能名称

## 技能描述
简要说明这个技能包的用途。

## 执行协议
定义 AI 执行任务的步骤流程。

### 1. Context Check (上下文检查)
...

### 2. Input Acquisition (获取需求)
...

### 3. Code Generation (代码生成)
...

### 4. Documentation Output (文档输出)
...

## 约束条件
- 约束 1
- 约束 2
```

### context.md 格式

```markdown
# Project Context Configuration

> ⚠️ 此文件需要初始化

## Tech Stack
- **Framework**: <!-- 待填充 -->
- **ORM**: <!-- 待填充 -->

## Directory Mapping
- **Controller Path**: <!-- 待填充 -->
- **Service Path**: <!-- 待填充 -->

## Code Style
- **Naming Convention**: <!-- 待填充 -->
```

### tools/init.md 格式

```markdown
# 技能名 - 初始化提示词

## 使用方法
复制以下内容发送给 AI

---

\`\`\`
请执行 xxx 技能初始化：
1. 扫描项目结构
2. 识别技术栈
3. 将结果写入 context.md
\`\`\`
```

---