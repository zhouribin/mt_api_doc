## 项目说明
### HOST: http://mtopen.umember.cn

## 1:获取auth token 接口

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

  | 参数名   | 参数说明    | 备注                   |
  |-------|---------|----------------------|
  | token | 认证token | 用于后续请求头Authorization |

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


## 2:获取在售列表接口

- 请求方式: GET
- 请求地址: /admin/user/meituan/coupon/list
- 请求头: Authorization: token
- ⚠️注意 Authorization: token 前面不要带 Bearer
- 请求参数:

  | 参数名      | 参数说明 | 备注 |
  |----------|------|----|
  | store_id | 店铺id | 必填 |

- 请求示例:
- /admin/user/meituan/coupon/list?store_id=1

- 响应参数:

  | 参数名           | 参数说明 | 备注 |
  |---------------|------|----|
  | actual_amount | 实际价格 |    |
  | origin_amount | 原价   |    |
  | product_name  | 商品名称 |    |
  | sku_id        | 商品id |    |
  | sku_name      | 商品名称 |    |

- 响应示例
```json
{
  "code": 10000,
  "msg": "success",
  "data": [
    {
      "actual_amount": "78.0",
      "origin_amount": "78.0",
      "product_name": "【开业特惠】通用通宵8小时",
      "sku_id": 1214171123,
      "sku_name": "【开业特惠】通用通宵8小时"
    }
  ],
  "count": 1,
  "date_time": "2024-12-15 23:00:45"
}
```

## 3:获取订单信息接口

- 请求方式: GET
- 请求地址: /admin/user/meituan/coupon/detail
- 请求头: Authorization: token
- ⚠️注意 Authorization: token 前面不要带 Bearer
- 请求参数:

  | 参数名         | 参数说明 | 备注 |
  |-------------|------|----|
  | store_id    | 店铺id | 必填 |
  | coupon_code | 券码   | 必填 |

- 请求示例:
- /admin/user/meituan/coupon/detail?store_id=1&coupon_code=123456

- 响应参数:

    | 参数名       | 参数说明 | 备注 |
    |-----------|------|----|
    | order_id  | 订单id |    |
    | sku_id    | 商品id |    |
    |  sku_name | 商品名称 |    |

- 响应示例:
```json

{
    "code": 10000,
    "msg": "success",
    "data": {
        "order_id": "4971997871483397117",
        "sku_id": 1206944074,
        "sku_name": "开业特惠通用畅玩4小时[49.00元][1206944074]"
    },
    "count": 1,
    "date_time": "2024-12-16 00:06:04"
}

```
  