# 安全说明

## 令牌管理
- 使用最小权限 Personal Access Token（仅 contents 读写）
- 令牌不写入任何仓库文件
- 泄露后立即在 GitHub Settings → Developer settings → Tokens 吊销并重新生成
- 建议每90天轮换一次

## 数据安全
- 密码使用 PBKDF2WithHmacSHA1 10000次迭代，不存明文
- 手机号/邮箱只存哈希或留空（最小必要原则）
- 设备信息只存 SHA-256 不可逆哈希

## 合规
- 账号注销后15个工作日内删除或匿名化个人数据
- 数据不超期保存
- 用户可申请导出自己的数据
