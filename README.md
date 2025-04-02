# CashAppPay

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

