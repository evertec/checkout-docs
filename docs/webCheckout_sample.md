# Web Checkout

This section explains the details of integration of the Web Checkout service

## Request Payload

``` JSON
{
	"username": "CERT4549444000033",
	"password": "5B034VrA",
	"accountID": "0001",
	"customerName": "Jesus",
	"customerEmail": "test@test.com",
	"address1": "",
	"address2": "",
	"city": "",
	"state": "",
	"zipcode": "00921",
	"phone": "",
	"fax": "",
	"trxID": "123456",
	"trxDescription": "werwer",
	"trxAmount": "1.00",
	"taxAmount1": "",
	"taxAmount2": "",
	"taxAmount3": "",
	"taxAmount4": "",
	"taxAmount5": "",
	"filler1": "",
	"filler2": "",
	"filler3": "",
	"language": "en",
	"ignoreValues": ""
}

```

## Response Payload

``` JSON
{
	"rCode": "00",
	"rMsg":
	"https://checkouttest.evertecinc.com/?token=93D414BC592444FD9C9370C89CAF753793D414BC592444FD9C9370C89CAF753708122019&lang=en",
    "requestID": "be0a144611c341a"
}

```