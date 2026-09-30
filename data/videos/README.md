# videos — 视频作品表

存储所有发布的视频作品。

## 字段
- id: UUID
- user_id: 作者ID
- username: 作者名
- color: 作者头像色
- video_url: 视频文件地址（GitHub Releases）
- desc/description: 视频描述
- likes: 点赞数
- comments: 评论数
- created_at/time_ms: 发布时间（毫秒）

## API调用
- 读: GET /data/videos/videos.json
- 写: PUT /data/videos/videos.json