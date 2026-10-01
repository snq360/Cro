# devices — 设备注册记录（防僵尸注册）

## 路径
`devices/devices.json`

## 字段
| 字段 | 类型 | 说明 |
|------|------|------|
| device_hash | string | SHA-256不可逆哈希（设备型号+Android ID+随机salt） |
| uid | string | 绑定的用户ID |
| first_seen | long(ms) | 首次出现时间 |
| last_seen | long(ms) | 最近出现时间 |
| reg_count | int | 注册次数 |
| status | string | normal/suspect/banned |
| note | string | 备注 |

## 规则
1. 同一 device_hash 只能绑定一个 uid
2. 同设备24h内注册尝试 > 3次 → status 改为 suspect
3. 重复注册返回错误码 4031 + 文案：「该设备已注册过账号，一个设备只能注册一个账号」
4. 注销后设备记录保留90天用于风控，之后删除

## 客户端上报时机
- 注册时上报 device_hash
- 登录时上报 device_hash
- 每次启动时更新 last_seen

## 隐私
- 只存不可逆哈希，无法反推设备信息
- 用途：防批量注册、防刷量
- 保留期限：账号注销后90天
