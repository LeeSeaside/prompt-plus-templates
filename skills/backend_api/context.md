# Backend API - Project Context

> ⚠️ 此文件需要初始化。请使用初始化提示词让 AI 扫描并填充。

## Tech Stack
- **Framework**: <!-- Spring Boot / Express / NestJS -->
- **ORM**: <!-- JPA / MyBatis / TypeORM / Prisma -->
- **Database**: <!-- MySQL / PostgreSQL / MongoDB -->
- **Build Tool**: <!-- Maven / Gradle / npm -->

## Directory Mapping

### Entity Layer
- **Path**: 
- **Naming**: <!-- XxxEntity / Xxx -->
- **Base Class**: <!-- BaseEntity (如有) -->

### Service Layer
- **Interface Path**: 
- **Impl Path**: 
- **Naming**: <!-- XxxService / XxxServiceImpl -->

### Controller Layer
- **Path**: 
- **Naming**: <!-- XxxController -->
- **Base Path**: <!-- /api/v1 -->

## Code Style

### Entity 规范
- 主键策略: 
- 字段注解: 
- 通用字段: <!-- createTime, updateTime, deleted -->

### Service 规范
- 依赖注入: <!-- @Autowired / 构造器注入 -->
- 事务注解: 
- 异常处理: 

### Controller 规范
- 响应包装类: <!-- Result<T> / ResponseEntity -->
- 参数校验: <!-- @Valid / @Validated -->
- 文档注解: <!-- @Api / @Operation -->
