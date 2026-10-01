# 流光 ShortFlow 数据库

仓库即数据库。所有数据以JSON文件存储在 `data/` 目录下。

## 目录结构

| 目录/文件 | 用途 |
|-----------|------|
| users/ | 用户账号（含密码哈希、会员、封禁、重置码） |
| videos/ | 视频作品（URL在Releases，JSON存元数据） |
| comments/ | 评论 |
| messages/ | 私信消息 |
| follows/ | 关注关系 |
| likes/ | 点赞记录 |
| notifications/ | 通知（点赞/评论/关注/系统/举报） |
| devices/ | 设备注册记录（防僵尸注册，只存不可逆哈希） |
| drafts/ | 草稿自动保存（每用户一个JSON文件） |
| media/ | 媒体文件索引（实际文件在Releases） |
| _index/ | 全局索引（视频清单/聊天附件清单/用户统计缓存） |
| endpoints.json | 机器可读接口定义（含错误码、占位接口） |
| schema.json | 数据库schema版本 |

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
| 项目 | 数值 |
|------|------|
| 仓库推荐大小 | 10GB |
| Contents API单文件 | ≤1MB |
| 仓库单文件硬限 | 100MB |
| Releases单文件 | ≤2GiB，无总量/带宽限制 |
| API限速 | 认证后5000次/小时 |
| Push大小 | ≤2GB |
