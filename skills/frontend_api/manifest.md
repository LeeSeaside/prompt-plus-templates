# Skill Manifest: Frontend API Integration

## 技能描述
根据后端接口文档，生成前端 API 调用代码、对接到页面组件、并生成测试验证。

## 核心职责
1. 生成 API 调用代码和类型定义
2. 将 API 对接到已有页面组件
3. 生成接口调用测试，验证对接完整性

## 执行协议

### 1. Context Check (上下文检查)
- 读取 `context.md` 获取前端项目配置
- 如果未初始化，**终止任务**并提示："请先执行项目初始化扫描"

### 2. Input Acquisition (获取需求)
- 从 `skills/frontend_api/input/` 读取接口文档
- 支持格式：
    - Swagger JSON / OpenAPI YAML
    - Markdown 接口列表
    - **backend_api 输出的 `api-spec-*.md`**（推荐）
- 同时读取 `input/` 中的**页面路径信息**（如有）

### 3. Code Generation (代码生成)

#### 3.1 类型定义生成
- 根据 `context.md` 中的 Types Path 定位存放位置
- 生成请求参数类型（XxxParams / XxxReq）
- 生成响应数据类型（XxxResult / XxxRes）
- 复用项目的通用类型（分页、响应包装等）

#### 3.2 API 函数生成
- 根据 `context.md` 中的 API Path 定位存放位置
- 遵循项目的命名规范（getXxxList / fetchXxx）
- 使用项目的 HTTP 客户端封装
- 包含完整的 TypeScript 类型标注

```typescript
// 生成的 API 文件示例
import request from '@/utils/request'
import type { UserParams, UserResult } from './types'

/** 获取用户列表 */
export function getUserList(params: UserParams) {
  return request.get<UserResult>('/api/user', { params })
}

/** 新增用户 */
export function createUser(data: CreateUserReq) {
  return request.post('/api/user', data)
}
```

### 4. Page Integration (页面对接)

#### 4.1 识别目标页面
- 根据 `input/` 中的页面路径信息，或根据模块名推断页面位置
- 参考 `context.md` 中的 Pages Path

#### 4.2 对接到页面
- 在页面中导入生成的 API 函数
- 替换页面中的 mock 数据或占位调用
- 对接列表查询、表单提交、删除等操作

```typescript
// 页面对接示例
import { getUserList, createUser, deleteUser } from '@/api/user'

// 列表查询
const loadData = async () => {
  const res = await getUserList(queryParams)
  tableData.value = res.data.list
  total.value = res.data.total
}

// 表单提交
const handleSubmit = async () => {
  await createUser(formData)
  message.success('创建成功')
  loadData()
}
```

#### 4.3 处理加载状态和错误
- 添加 loading 状态控制
- 添加错误处理和提示

### 5. Test Generation (测试生成)

#### 5.1 生成 API 调用测试
在 `skills/frontend_api/output/` 生成 `api-test-[模块名].md`：

```markdown
# [模块名] 接口对接测试清单

## 测试环境
- [ ] 后端服务已启动
- [ ] 接口地址配置正确

## 接口测试

### 1. 获取列表 - getUserList
- [ ] 无参数查询正常
- [ ] 分页参数正常
- [ ] 搜索条件正常
- [ ] 空数据处理正常

### 2. 新增 - createUser
- [ ] 必填字段校验
- [ ] 提交成功提示
- [ ] 列表自动刷新

### 3. 更新 - updateUser
- [ ] 数据回显正确
- [ ] 更新成功提示

### 4. 删除 - deleteUser
- [ ] 确认弹窗显示
- [ ] 删除成功提示
- [ ] 列表自动刷新

## 页面功能验证
- [ ] 列表加载正常
- [ ] 分页切换正常
- [ ] 搜索功能正常
- [ ] 新增弹窗正常
- [ ] 编辑弹窗正常
- [ ] 删除功能正常
```

### 6. Documentation Output (文档输出)

在 `skills/frontend_api/output/` 生成：

#### 6.1 execution_log.md
- 生成的文件列表
- 修改的页面文件
- 接口对照表

#### 6.2 api-test-[模块名].md
- 接口测试清单
- 页面功能验证清单

## 约束条件
- 严格遵循项目的 API 封装方式
- 类型定义要完整准确
- 复用项目现有的通用类型
- **必须对接到页面**（如提供了页面路径）
- **必须生成测试清单**
