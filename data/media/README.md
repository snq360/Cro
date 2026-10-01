# media — 媒体文件归档目录

本目录用于记录媒体文件的**路径索引**，实际二进制文件存放在 GitHub Releases。

## 目录规范
```
media/videos/<uid>/<YYYY-MM>/<videoId>.mp4    ← 视频成品（实际在Releases，这里记录索引）
media/covers/<uid>/<YYYY-MM>/<videoId>.jpg    ← 封面图
media/chat/<a_uid>__<b_uid>/<YYYY-MM>/<msgId>_<type>.<ext>  ← 聊天附件
media/avatars/<uid>.<ext>                      ← 用户头像
```

## 命名规则
- 会话目录：两个UID按字典序排序后用 `__` 连接（如 `a1b2__c3d4`）
- 月份目录：`YYYY-MM` 格式（如 `2026-10`）
- 文件命名：`{资源ID}_{类型}.{扩展名}`

## 注意
- 二进制文件**不直接存入仓库**（仓库正文单文件限1MB，push限2GB）
- 视频/图片本体上传到 GitHub Releases，JSON里存 browser_download_url
- 本目录只放索引文件（manifest），记录谁在何时传了什么
