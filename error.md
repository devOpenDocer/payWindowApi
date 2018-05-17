# 支付窗内接口异常情形

- 获取付费点

> https://pay.docer.wps.cn/api/pay/point

| msg | 含义 |
| --- | --- |
| empty	 | 获取付费点信息失败 |
| xxx is required	 | 缺少必填参数 |

- 支付接口

> https://pay.docer.wps.cn/api/pay/index

| msg | 含义 |
| --- | --- |
| invalid pay_sign or app_id | 非法的付费点或者助手app_id |
| get price failed | 获取付费点价格失败 |
| have paid order | 存在已支付但未成功通知第三方的订单 |
| app deny buy | 调用ask_url失败或者接口返回不允许购买，（ask_url：询问第三方当前用户是否可以购买指定付费点） |
| update pay_order_id failed | 更新订单失败 |
| xxx is required	 | 缺少必填参数 |

