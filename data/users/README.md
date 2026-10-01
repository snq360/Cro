# users — 用户账号表

存储所有注册用户的账号信息。

## 字段说明

### 基础字段（客户端正在使用，不可改名）
| 字段 | 类型 | 单位 | 说明 |
|------|------|------|------|
| id | string(UUID) | - | 用户唯一ID |
| username | string | - | 登录用户名（唯一） |
| nickname | string | - | 显示昵称 |
| avatar_color | int | ARGB | 头像背景色 |
| bio | string | - | 个人简介 |
| salt | string | - | 密码盐 |
| password_hash | string | - | PBKDF2哈希 |
| is_admin | bool | - | 是否管理员 |
| is_vip | bool | - | 是否会员 |
| banned | bool | - | 是否封禁 |
| created_at | long | **秒** | 注册时间（旧字段，单位秒） |

### 新增字段（只增不改）
| 字段 | 类型 | 单位 | 默认值 | 说明 |
|------|------|------|--------|------|
| registered_at | long | **毫秒** | created_at×1000 | 注册时间（新统一单位） |
| account_no | string | - | "" | 流光ID（用户号） |
| birthday | string | - | "" | 生日 |
| anniversary | string | - | "" | 纪念日预留 |
| active_days | int | 天 | 0 | 活跃天数 |
| last_active_at | long | 毫秒 | 0 | 最后活跃时间 |
| register_source | string | - | "app" | 注册来源 |
| register_device_hash | string | - | "" | 注册设备哈希 |
| account_status | string | - | "active" | active/risk/banned/deleted |
| reset_code_hash | string | - | "" | 重置码哈希（不存明文） |
| reset_attempts | int | 次 | 0 | 重置码错误次数 |
| reset_cooldown_until | long | 毫秒 | 0 | 重置冷却截止时间 |
| phone | string | - | "" | 手机号（仅哈希或空） |
| email | string | - | "" | 邮箱（仅哈希或空） |
| avatar_url | string | - | "" | 图片头像URL |
| cover_url | string | - | "" | 主页背景图 |
| gender | string | - | "unknown" | male/female/unknown |
| location | string | - | "" | 所在地 |
| status | string | - | "offline" | online/offline |
| login_count | int | 次 | 0 | 登录次数 |
| last_login_at | long | 毫秒 | 0 | 最后登录时间 |
| follower_count | int | - | 0 | 粉丝数（缓存） |
| following_count | int | - | 0 | 关注数（缓存） |
| video_count | int | - | 0 | 作品数（缓存） |
| total_likes | int | - | 0 | 获赞总数（缓存） |
| last_seen | long | - | - | 最后在线 |

## 时间单位注意
- `created_at` 是**秒**（旧），`registered_at` 是**毫秒**（新）
- 换算：`registered_at = created_at × 1000`
- 校验：任何时间戳 < 1e11 视为秒，需 ×1000

## API调用
- 读: GET /data/users/users.json
- 写: PUT /data/users/users.json（必须带sha）
