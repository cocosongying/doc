### 登录接口
+ 根据用户名密码验证
+ 验证通过返回用户基本信息和登录令牌
+ 登录令牌用来调用其他需要验证身份的接口使用
+ 验证失败返回错误码

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/login` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| username | string | 是 | - | 登录名 |
| password | string | 是 | - | 密码 |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |
| data | json | 返回值 |
| data.userInfo | json | 用户基本信息 |
| data.token | string | 登录token |

data.userInfo

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| userId | int | 用户ID |
| username | string | 登录名 |
| nickname | string | 昵称 |
| description | string | 描述 |
| avatar | string | 头像地址 |
| role | int | 角色 |
| menu | string | 菜单权限 |
| active | int | 是否有效 |

### 新增用户接口
+ 仅管理员可以新增用户
+ 录入基本信息成功后返回
+ 用户名已存在返回错误信息

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/add` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| token | string | 是 | - | 用户token |
| username | string | 是 | - | 登录名 |
| nickname | string | 是 | - | 昵称 |
| description | string | 否 | - | 描述 |
| avatar | string | 否 | - | 头像地址 |
| menu | string | 否 | - | 菜单权限 |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |

### 修改用户接口
+ 管理员可以修改所有用户信息
+ 用户自己可以修改自己的信息
+ 管理员可以通过此接口修改用户有效性

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/updateById` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| token | string | 是 | - | 用户token |
| id | string | 是 | - | 用户ID |
| nickname | string | 否 | - | 昵称 |
| description | string | 否 | - | 描述 |
| avatar | string | 否 | - | 头像地址 |
| menu | string | 否 | - | 菜单权限 |
| active | string | 否 | - | 是否有效 |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |

### 获取用户信息
+ 用户可查询自己的基本信息
+ 管理员可指定用户ID进行查询

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/getById` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| token | string | 是 | - | 用户token |
| id | int | 否 | - | 用户ID |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |
| data | json | 返回值 |
| data.userInfo | json | 用户信息 |

data.userInfo

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| id | int | 用户ID |
| username | string | 登录名 |
| nickname | string | 昵称 |
| description | string | 描述 |
| avatar | string | 头像地址 |
| role | int | 角色 |
| menu | string | 菜单权限 |
| active | int | 是否有效 |
| lastLogin | int | 上次登录时间戳 |

### 获取用户列表
+ 仅管理员可以获取
+ 支持分页查询

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/list` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| token | string | 是 | - | 用户token |
| pageStart | int | 否 | 0 | 起始页码 |
| pageSize | int | 否 | 10 | 每页条数 |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |
| data | json | 返回值 |
| data.total | int | 总条数 |
| data.list | array | 用户信息列表 |

data.list[]

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| id | int | 用户ID |
| username | string | 登录名 |
| nickname | string | 昵称 |
| role | int | 角色 |
| active | int | 是否有效 |
| lastLogin | int | 上次登录时间戳 |

### 重置用户密码
+ 仅管理员可以操作
+ 对传入用户ID重置密码为123456

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/resetPasswd` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| token | string | 是 | - | 用户token |
| id | int | 是 | - | 用户ID |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |

### 修改用户密码
+ 先验证旧密码
+ 再验证输入的两次新密码是否一致
+ 验证通过更新自己的密码为新密码

**接口**

| 请求地址 | 请求类型 |
| :-- | :--: |
| `/user/modifyPasswd` | POST |

**入参**

| 名称 | 类型 | 必须 | 缺省值 | 描述 |
| :-- | :--: | :--: | :--: | :-- |
| token | string | 是 | - | 用户token |
| oldpassword | string | 是 | - | 旧密码(加密) |
| newpassword | string | 是 | - | 新密码(加密) |
| newpassword2 | string | 是 | - | 再确认新密码(加密) |

**出参**

| 名称 | 类型 | 描述 |
| :-- | :--: | :-- |
| code | int | 返回码 |
