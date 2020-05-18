### 用户信息表
`user_info`

| 名称 | 类型 | 描述 |
| :-- | :-- | :-- |
| id | int | 用户ID |
| username | varchar(50) | 登录名 |
| password | varchar(128) | 密码 |
| nickname | varchar(50) | 昵称 |
| description | varchar(300) | 简介 |
| avatar | varchar(200) | 头像 |
| role | tinyint | 角色 |
| active | tinyint | 是否有效 |
| menu | text | 菜单权限 |
| createTime | bigint | 创建时间 |
| updateTime | bigint | 修改时间 |
| lastLogin | bigint | 上次登录 |
