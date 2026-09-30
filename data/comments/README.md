# comments — 评论表

存储所有视频评论。

## 字段说明

### 基础字段
| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 评论ID |
| video_id | string | 所属视频ID |
| user_id | string | 评论者ID |
| username | string | 评论者名 |
| content | string | 评论内容 |
| time_ms | long | 评论时间(ms) |

### 预设字段
| 字段 | 类型 | 默认值 | 用途 |
|------|------|--------|------|
| reply_to_id | string | "" | 回复哪条评论 |
| likes_count | int | 0 | 评论点赞数 |
| deleted | bool | false | 是否被删除 |

## API调用
- 读: GET /data/comments/comments.json
- 写: PUT /data/comments/comments.json
