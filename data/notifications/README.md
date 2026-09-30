# notifications — 通知表

存储所有用户通知（点赞/评论/关注/系统广播）。

## 字段
- id: UUID
- user_id: 接收者ID
- type: 通知类型（like/comment/follow/broadcast）
- title: 通知标题
- body: 通知内容
- is_read: 是否已读
- time_ms: 通知时间（毫秒）

## API调用
- 读: GET /data/notifications/notifications.json
- 写: PUT /data/notifications/notifications.json