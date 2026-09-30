# messages — 私信消息表

存储所有用户间私信。

## 字段
- id: UUID
- conversation_id: 会话ID（双方ID排序拼接）
- sender_id: 发送者ID
- peer_id: 接收者ID
- type: 消息类型（text/image/video）
- content: 消息内容
- recalled: 是否撤回
- time_ms: 发送时间（毫秒）

## API调用
- 读: GET /data/messages/messages.json
- 写: PUT /data/messages/messages.json