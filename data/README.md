# 流光 ShortFlow 数据库

仓库即数据库。所有数据以JSON文件存储在 data/ 目录下。

## 目录结构

| 文件夹 | 内容 | API路径 |
|--------|------|---------|
| users/ | 用户账号 | data/users/users.json |
| videos/ | 视频作品 | data/videos/videos.json |
| comments/ | 评论 | data/comments/comments.json |
| messages/ | 私信 | data/messages/messages.json |
| follows/ | 关注关系 | data/follows/follows.json |
| likes/ | 点赞记录 | data/likes/likes.json |
| notifications/ | 通知 | data/notifications/notifications.json |

## 认证方式
所有请求需带 Header:
- Authorization: token ghp_xxx
- Accept: application/vnd.github.v3+json
- User-Agent: ShortFlow-App

## 读写协议
1. GET 文件 → 拿到 content(base64) + sha
2. base64 decode → 改JSON
3. base64 encode → PUT 写回（带sha）
4. 409冲突 → 重新GET → merge → 重试最多5次

## 视频文件
视频本体存在 GitHub Releases，JSON里只存下载URL。
