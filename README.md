## 获取auth token 接口

- 请求方式: POST
- 请求地址: /admin/login

- 请求参数:

  | 参数名      | 参数说明 | 备注 |
  |----------|------|----|
  | email    | 用户邮箱 | 必填 |
  | password | 用户密码 | 必填 |

- 请求示例:
```json
{
  "email":"zhangsan@126.com",
  "password":"1234"
}
```
- 响应参数:

  | 参数名   | 参数说明    | 备注     |
  |-------|---------|--------|
  | token | 认证token | 用于后续请求 |

- 响应示例:
```json
{
    "code": 10000,
    "msg": "success",
    "data": {
        "id": 9,
        "phone": "18500516066",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJVc2V123",
        "username": "张三"
    },
    "count": 1,
    "date_time": "2024-12-15 22:08:24"
}
```