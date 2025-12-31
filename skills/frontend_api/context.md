# Frontend API - Project Context

> ⚠️ 此文件需要初始化。请使用初始化提示词让 AI 扫描并填充。

## Tech Stack
- **Framework**: <!-- Vue 3 / React / Angular -->
- **HTTP Client**: <!-- axios / fetch / ky -->
- **TypeScript**: <!-- 是否使用 TS -->
- **UI Library**: <!-- Element Plus / Ant Design / Vuetify -->

## Directory Mapping
- **API Path**: <!-- src/api -->
- **Types Path**: <!-- src/api/types / src/types -->
- **Request Utils**: <!-- src/utils/request.ts -->
- **Pages Path**: <!-- src/views / src/pages -->
- **Components Path**: <!-- src/components -->

## Naming Convention

### 文件命名
- API 文件: <!-- xxxApi.ts / xxx.api.ts / xxx.ts -->
- 类型文件: <!-- xxx.d.ts / types.ts -->

### 函数命名
- 查询列表: <!-- getXxxList / fetchXxxList -->
- 查询详情: <!-- getXxxDetail / getXxxById -->
- 新增: <!-- createXxx / addXxx -->
- 更新: <!-- updateXxx / editXxx -->
- 删除: <!-- deleteXxx / removeXxx -->

### 类型命名
- 请求参数: <!-- XxxParams / XxxReq / XxxQuery -->
- 响应数据: <!-- XxxResult / XxxRes / XxxVO -->

## Code Style

### 导出方式
<!-- 命名导出 / 默认导出 -->

### 请求封装
```typescript
// 项目的请求封装示例
import request from '@/utils/request'

export function getXxx(params: XxxParams) {
  return request.get<Result<XxxVO>>('/api/xxx', { params })
}
```

### 通用类型
```typescript
// 项目的通用类型定义
interface Result<T> {
  code: number
  message: string
  data: T
}

interface PageResult<T> {
  list: T[]
  total: number
}
```

## Page Patterns

### 列表页面模式
```typescript
// 列表数据加载模式
const loading = ref(false)
const tableData = ref([])
const total = ref(0)

const loadData = async () => {
  loading.value = true
  try {
    const res = await getXxxList(queryParams)
    tableData.value = res.data.list
    total.value = res.data.total
  } finally {
    loading.value = false
  }
}
```

### 表单提交模式
```typescript
// 表单提交模式
const handleSubmit = async () => {
  await formRef.value.validate()
  if (isEdit) {
    await updateXxx(formData)
  } else {
    await createXxx(formData)
  }
  message.success('操作成功')
  dialogVisible.value = false
  loadData()
}
```

### 删除操作模式
```typescript
// 删除操作模式
const handleDelete = async (id: number) => {
    await MessageBox.confirm('确认删除？')
    await deleteXxx(id)
    message.success('删除成功')
    loadData()
}
```
