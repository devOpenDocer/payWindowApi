# ScenePay

> 情景助手统一支付窗


## URL 参数

Type: GET

`https://pay.docer.wps.cn/payhome/#/?app_id=APP_ID&pay_sign=PAY_SIGN&active_pay_sign=ACTIVE_PAY_SIGN&ask_url=ASK_URL&notify_url=NOTIFY_URL&title=TITLE&descript=DESCRIPT`

| 字段 | 描述 | 示例 | 默认值 | 是否必填 |
| --- | --- | --- | --- | --- |
| app_id | 脚本标识 | `1` | 无 | 是 |
| pay_sign | 付费点标识 | `paysign1,paysign2`(多付费点标识以逗号分隔) | 无 | 是 |
| active_pay_sign | 当前付费点标识 | `paysign1` | 传入的第一个付费点标识 | 否 |
| ask_url | 服务器校验地址 | `a.company.com/ask` | 无 | 是 |
| notify_url | 支付成功通知地址 | `a.company.com/notify` | 无 | 是 |
| title | 支付页标题 | `开通xxx工具特权` | 无 | 否 |
| descript | 支付页描述 | `xxx` | 无 | 否 |

注意：参数若包含中文或url，需先经过encodeURIComponent方法编码

## 支付状态消息广播

- 支付成功

``` json
{
	"data": {
		"url": "http://test.pay.wps.cn/api/pay/qrcodelink/?data=aHR0cDovL3Rlc3QucGF5Lndwcy5jbi9hcGkvcGF5L3FyY29kZXBheT9vcmRlcl9pZD0yMDE4MDEzMTgwNzk3NjVj&size=b",
		"order_num": "201801318079765c",
		"total_fee": "0.01",
		"sign": "lwzs_pay_lwzlb"
	},
	"paystatus": "success"
}
```

- 支付失败

``` json
{
	"data": {
		"url": "http://test.pay.wps.cn/api/pay/qrcodelink/?data=aHR0cDovL3Rlc3QucGF5Lndwcy5jbi9hcGkvcGF5L3FyY29kZXBheT9vcmRlcl9pZD0yMDE4MDEzMTgwNzk3NjVj&size=b",
		"order_num": "201801318079765c",
		"total_fee": "0.01",
		"sign": "lwzs_pay_lwzlb"
	},
	"paystatus": "fail"
}

```

## 接口逻辑流程图

![](https://github.com/devOpenDocer/payWindowApi/blob/master/static/flow.png)

## 其它

- [支付窗接口异常对照](./error.md)



