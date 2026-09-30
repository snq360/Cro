# messages — 私信消息表

存储所有用户间私信。

## 字段说明

### 基础字段
| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 消息ID |
| conversation_id | string | 会话ID(双方ID排序拼接) |
| sender_id | string | 发送者ID |
| peer_id | string | 接收者ID |
| type | string | text/image/video |
| content | string | 消息内容 |
| recalled | bool | 是否撤回 |
| time_ms | long | 发送时间(ms) |

### 预设字段
| 字段 | 类型 | 默认值 | 用途 |
|------|------|--------|------|
| attachment_url | string | "" | 附件URL |
| delivered | bool | true | 是否已送达 |
| read_at | long | 0 | 已读时间 |

## API调用
- 读: GET /data/messages/messages.json
- 写: PUT /data/messages/messages.json
