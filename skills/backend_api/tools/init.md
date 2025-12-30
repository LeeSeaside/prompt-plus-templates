# Backend API - 初始化提示词

## 使用方法
复制以下内容发送给 AI，初始化后端项目配置。

---

```
请执行 backend_api 技能初始化：

1. 扫描项目结构（pom.xml / build.gradle / package.json）
2. 识别技术栈：框架、ORM、数据库
3. 分析三层架构：
   - Entity 层：路径、命名规范、基类、注解
   - Service 层：接口路径、实现路径、依赖注入方式
   - Controller 层：路径、响应包装类、文档注解
4. 将结果写入 `.ai-workspace/skills/backend_api/context.md`

完成后回复："✅ backend_api 初始化完成"
```
