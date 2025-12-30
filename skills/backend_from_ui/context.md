# Backend from UI - Project Context

> ⚠️ 此文件需要初始化。请使用初始化提示词让 AI 扫描并填充。

## Tech Stack
- **Framework**: <!-- Vue / React / Angular -->
- **UI Library**: <!-- Element Plus / Ant Design / Vuetify -->
- **State Management**: <!-- Pinia / Vuex / Redux -->
- **Router**: <!-- Vue Router / React Router -->

## Directory Mapping
- **Pages Path**: <!-- src/views / src/pages -->
- **Components Path**: <!-- src/components -->
- **Router Config**: <!-- src/router/index.ts -->
- **API Path**: <!-- src/api -->

## Page Structure

### 列表页面模式
- 表格组件: <!-- el-table / a-table -->
- 列定义方式: <!-- columns 数组 / template 插槽 -->
- 分页组件: <!-- el-pagination / a-pagination -->

### 表单页面模式
- 表单组件: <!-- el-form / a-form -->
- 字段定义方式: <!-- formItems 数组 / template -->
- 校验方式: <!-- rules 对象 -->

### 弹窗模式
- 弹窗组件: <!-- el-dialog / a-modal -->
- 触发方式: <!-- visible 控制 -->

## Data Patterns

### 列表查询
```typescript
// 查询参数结构示例
interface QueryParams {
  page: number
  pageSize: number
  // ...搜索字段
}
```

### 分页响应
```typescript
// 分页响应结构示例
interface PageResult<T> {
  list: T[]
  total: number
}
```
