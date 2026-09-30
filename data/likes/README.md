# likes — 点赞记录表

存储所有视频点赞记录。

## 字段
- id: UUID
- user_id: 点赞者ID
- video_id: 视频ID
- created_at: 点赞时间（秒）

## API调用
- 读: GET /data/likes/likes.json
- 写: PUT /data/likes/likes.json