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

     https://your-company.com/checkout?payid=SDybs2xqnO2gtDC3K049t7HN

### step4. verify pay result

```
POST https://XXX/PartnerCheckout/Dev/Return
Accept: application/json
Content-Type: application/json

{
	"PayID": "SDybs2xqnO2gtDC3K049t7HN"
}
```
**Response**
```
{
  "Payload": "SO_987846",
  "Result": "Success",
  "MessageEntitys": null
}
```


## Order Model
| Name |  Description|
|:-----|-----------|
|Email| *string* <br/> max length = 128 <br/> address owner's full name.<br/>`"Randolph@gmail.com"`|
|ContactWith| *string* <br/> max length = 80 <br/> address owner's full name.<br/>`"Randolph Sun"`|
|Phone| *string* <br/> address owner's phone number. <br/> `"(621) 054-6512EXT78954"` |
|State| *string* <br/> address state.  <br/>  `"CA"` |
|City| *string* <br/> max length = 45 <br/> address city. <br/> `"Fullerton"` |
|Address1| *string*<br/> max length = 100 <br/> address line one of the address<br/>      `"The Streams Apt"` |
|Address2| *string Optional.*<br/>max length=30<br/>  address line two of the address<br/> `"1301 Deerpark Dr Apt 29"` |
|ZipCode|  *string*  <br/>   address zipcode<br/> `"92831-2242"` |
|Country| *string* <br/> address country<br/>    `"US"`   |

