# comments — 评论表

存储所有视频评论。

## 字段
- id: UUID
- video_id: 所属视频ID
- user_id: 评论者ID
- username: 评论者名
- content: 评论内容
- time_ms: 评论时间（毫秒）

## API调用
- 读: GET /data/comments/comments.json
- 写: PUT /data/comments/comments.json