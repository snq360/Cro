# 流光 ShortFlow 数据库

仓库即数据库。所有数据以JSON文件存储在 `data/` 目录下。

## 目录结构

| 目录 | 用途 | 主文件 |
|------|------|--------|
| users/ | 用户账号 | users/users.json |
| videos/ | 视频作品 | videos/videos.json |
| comments/ | 评论 | comments/comments.json |
| messages/ | 私信 | messages/messages.json |
| follows/ | 关注关系 | follows/follows.json |
| likes/ | 点赞记录 | likes/likes.json |
| notifications/ | 通知 | notifications/notifications.json |
| devices/ | 设备注册记录（防刷） | devices/devices.json |
| drafts/ | 草稿自动保存 | drafts/<uid>.json |
| media/ | 媒体文件索引（实际文件在Releases） | media/README.md |
| _index/ | 全局索引 | _index/*.json |
| endpoints.json | 机器可读接口定义 | endpoints.json |

## 认证方式
```
Authorization: token ghp_xxx
Accept: application/vnd.github.v3+json
User-Agent: ShortFlow-App
```

## 读写协议
1. GET 文件 → 拿到 content(base64) + sha
2. base64 decode → 改JSON
3. base64 encode → PUT 写回（带sha）
4. 409冲突 → 重新GET → merge → 重试最多5次

## GitHub限制（2026年实测）
- 仓库推荐大小：10GB
- Contents API单文件：≤1MB
- 仓库单文件硬限：100MB
- Releases单文件：≤2GiB，无总量限制，无带宽限制
- API限速：认证后5000次/小时
- Push大小：≤2GB

## 视频存储
视频本体存 GitHub Releases，JSON只存下载URL。
