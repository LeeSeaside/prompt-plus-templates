# Frontend API - 开发提示词

## 完整工作流

```
前端写页面（mock 数据）
    ↓
backend_from_ui 分析页面，生成 API 需求文档
    ↓
后端 backend_api 开发接口
    ↓
输出 api-spec-[模块].md
    ↓
复制到 frontend_api/input/
    ↓
frontend_api 生成 API 代码 + 对接页面 + 测试验证
    ↓
✅ 闭环完成
```

---

## 使用方法

### 步骤 1：准备输入文件
将以下文件放入 `skills/frontend_api/input/`：
- `api-spec-[模块].md` - 后端接口文档（必需）
- `pages.md` - 页面路径信息（可选，用于自动对接）

**pages.md 格式示例**：
```markdown
# 用户管理模块

## 页面路径
- 列表页: src/views/user/index.vue
- 表单组件: src/views/user/components/UserForm.vue
```

### 步骤 2：执行技能

---

## 快速版
```
使用 frontend_api 技能，读取 input 目录的接口文档，生成 API 代码并对接到页面。
```

## 标准版
```
请执行 frontend_api 对接任务：

1. 加载技能包 `.ai-workspace/skills/frontend_api/`
2. 读取 `input/` 目录中的接口文档和页面路径
3. 生成代码：
   - TypeScript 类型定义
   - API 调用函数
4. 对接到页面：
   - 导入 API 函数
   - 替换 mock 数据
   - 对接列表、表单、删除等操作
5. 生成测试清单到 `output/`
```

## 完整版（含测试验证）
```
请执行 frontend_api 完整对接任务：

1. 加载技能包并读取接口文档
2. 生成 API 代码和类型定义
3. 对接到指定页面：
   - 列表查询对接
   - 新增/编辑表单对接
   - 删除操作对接
   - 添加 loading 状态
   - 添加错误处理
4. 生成测试清单，包含：
   - 每个接口的测试用例
   - 页面功能验证点
5. 输出执行日志

完成后，请列出需要手动验证的测试项。
```

---

## 仅生成 API（不对接页面）
```
使用 frontend_api 技能，只生成 API 代码和类型定义，不对接页面。
```

## 仅对接页面（API 已存在）
```
使用 frontend_api 技能，将已有的 API 函数对接到 [src/views/user/index.vue] 页面。
```
