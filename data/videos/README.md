# videos — 视频作品表

存储所有发布的视频作品。

## 字段说明

### 基础字段（已有）
| 字段 | 类型 | 说明 |
|------|------|------|
| id | string(UUID) | 作品唯一ID |
| user_id | string | 作者ID |
| username | string | 作者名 |
| color | int | 作者头像色 |
| video_url | string | 视频下载地址(GitHub Releases) |
| desc | string | 视频描述 |
| likes | int | 点赞数 |
| comments | int | 评论数 |
| time_ms | long | 发布时间(ms) |

### 预设字段（新增）
| 字段 | 类型 | 默认值 | 用途 |
|------|------|--------|------|
| duration | int | 0 | 视频时长(秒) |
| width | int | 0 | 视频宽度 |
| height | int | 0 | 视频高度 |
| thumbnail_url | string | "" | 封面图URL |
| status | string | "public" | public/private/draft |
| tags | array | [] | 话题标签 |
| location | string | "" | 发布位置 |
| share_count | int | 0 | 分享数 |
| favorite_count | int | 0 | 收藏数 |
| view_count | int | 0 | 播放数 |

## API调用
- 读: GET /data/videos/videos.json
- 写: PUT /data/videos/videos.json
