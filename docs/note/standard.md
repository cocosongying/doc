# 规范

## Git 提交规范

提交格式 `type(scope): subject`

!> `Type` - (必填) 提交的类型<br>
`Scope` - (可选) 提交影响的范围<br>
`Subject` - (必填) 简单描述提交的内容

| type | description |
| :---- | :----------- |
| feat | 新增功能 |
| fix | 修复 Bug |
| docs | 文档更新 |
| style | 不影响程序逻辑的代码修改 |
| refactor | 重构代码 |
| perf | 性能和体验优化 |
| test | 新增测试用例或是更新现有测试 |
| build | 主要目的是修改项目构建系统 |
| ci | 主要目的是修改项目继续集成流程 |
| chore | 不属于以上类型的其他类，比如构建流程, 依赖管理 |
| revert | 回滚某个更早之前的提交 |
