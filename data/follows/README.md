# follows — 关注关系表

存储用户间的关注关系。

## 字段说明

### 基础字段
| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 关系ID |
| follower_id | string | 关注者ID |
| followee_id | string | 被关注者ID |
| created_at | long | 关注时间 |

### 预设字段
| 字段 | 类型 | 默认值 | 用途 |
|------|------|--------|------|
| notify_enabled | bool | true | 是否开启新作品通知 |

## API调用
- 读: GET /data/follows/follows.json
- 写: PUT /data/follows/follows.json
