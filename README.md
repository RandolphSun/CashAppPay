# CashAppPay

## step1. get pay url
```
POST https://xxx/PartnerCheckout/Dev/Auth
Accept: application/json
Content-Type: application/json

{
	"AppID": "xxx",
	"AppSecret": "xxx",	
	"Payload": "SO_987846",
	"Amount": 9.99,
	"Items": [
		{
			"ItemNumber": "9SIBEGC0001759",
			"Quantity": 1
		}
	]	
}
```
**Response**
```
{
  "Url": "https://xxxx",
  "Result": "Success",
  "MessageEntitys": null
}
```
### step2.  return newegg page. (step1.Response.Url)

### step3. newegg return to partner site.

     https://your-company.com/checkout?PayToken=SDybs2xqnO2gtDC3K049t7HN

### step4. verify pay result

```
POST https://XXX/PartnerCheckout/Dev/Return
Accept: application/json
Content-Type: application/json

{
	"PayToken": "SDybs2xqnO2gtDC3K049t7HN"
}
```
**Response**
```
{
  "Payload": "SO_987846",
  "PayID":"NeweggSO_XXXXXX",
  "Result": "Success",
  "MessageEntitys": null
}
```
**ErrorCode**
| Code | Desc |
|:-----|-----------|
|InvalidApp|AppID或者AppSecret错误|
|InvalidItem|Item信息错误|
|InvalidAmount|传入的item和金额不匹配|
|InvalidPayToken|传入的PayToken不正确|
|UnSuccess|PayToken过期|

## Test Item
| ItemNumber | Amount |
|:-----|-----------|
|9SIBEGC0001759|9.99|
|9SIBEGC0001777| 5|
|9SIBEGC0001778| 10|
|9SIBEGC0001779| 15|
|9SIBEGC0001780| 20|

