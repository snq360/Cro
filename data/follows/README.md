# follows — 关注关系表

存储用户间的关注关系。

## 字段
- id: UUID
- follower_id: 关注者ID
- followee_id: 被关注者ID
- created_at: 关注时间（秒）

## API调用
- 读: GET /data/follows/follows.json
- 写: PUT /data/follows/follows.json