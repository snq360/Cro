# users — 用户账号表

存储所有注册用户的账号信息。

## 字段
- id: UUID
- username: 登录用户名（唯一）
- nickname: 显示昵称
- avatar_color: 头像背景色
- bio: 个人简介
- salt: 密码盐
- password_hash: PBKDF2哈希
- is_admin: 是否管理员
- is_vip: 是否会员
- banned: 是否封禁
- created_at: 注册时间（毫秒）
- last_seen: 最后在线时间

## API调用
- 读: GET /data/users/users.json
- 写: PUT /data/users/users.json（带sha）