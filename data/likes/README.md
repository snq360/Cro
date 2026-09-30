# likes — 点赞记录表

存储所有视频点赞记录。

## 字段说明

| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 点赞ID |
| user_id | string | 点赞者ID |
| video_id | string | 视频ID |
| created_at | long | 点赞时间 |

## API调用
- 读: GET /data/likes/likes.json
- 写: PUT /data/likes/likes.json
