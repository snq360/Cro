# notifications — 通知表

存储所有用户通知。

## 字段说明

### 基础字段
| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 通知ID |
| user_id | string | 接收者ID |
| type | string | like/comment/follow/broadcast |
| title | string | 通知标题 |
| body | string | 通知内容 |
| is_read | bool | 是否已读 |
| time_ms | long | 通知时间(ms) |

### 预设字段
| 字段 | 类型 | 默认值 | 用途 |
|------|------|--------|------|
| read_at | long | 0 | 已读时间 |
| icon_url | string | "" | 通知图标 |

## API调用
- 读: GET /data/notifications/notifications.json
- 写: PUT /data/notifications/notifications.json
