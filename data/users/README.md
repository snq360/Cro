# users — 用户账号表

存储所有注册用户的账号信息。

## 字段说明

### 基础字段（已有）
| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 用户唯一ID |
| username | string | 登录用户名（唯一） |
| nickname | string | 显示昵称 |
| avatar_color | int | 头像背景色(ARGB) |
| bio | string | 个人简介 |
| salt | string | 密码盐 |
| password_hash | string | PBKDF2哈希 |
| is_admin | bool | 是否管理员 |
| is_vip | bool | 是否会员 |
| banned | bool | 是否封禁 |
| created_at | long | 注册时间 |

### 预设字段（新增，未来扩展用）
| 字段 | 类型 | 默认值 | 用途 |
|------|------|--------|------|
| phone | string | "" | 绑定手机号 |
| email | string | "" | 绑定邮箱 |
| avatar_url | string | "" | 图片头像URL（目前用颜色，未来支持） |
| cover_url | string | "" | 主页背景图 |
| gender | string | "unknown" | male/female/unknown |
| location | string | "" | 所在地 |
| status | string | "offline" | online/offline/busy |
| login_count | int | 0 | 登录次数 |
| last_login_at | long | 0 | 最后登录时间(ms) |
| follower_count | int | 0 | 粉丝数(缓存) |
| following_count | int | 0 | 关注数(缓存) |
| video_count | int | 0 | 作品数(缓存) |
| total_likes | int | 0 | 获赞总数(缓存) |
| last_seen | long | - | 最后在线时间 |

## API调用
- 读: GET /data/users/users.json
- 写: PUT /data/users/users.json（必须带sha）
