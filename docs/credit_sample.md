# Process Credit

This section explains the details of integration of the Web Checkout service

## Sale

### Request Payload

``` JSON
{
	"username": "CERT4549444000033",
	"password": "5B034VrA",
	"trxOper": "sale",
	"accountID": "0001",
	"customerName": "John Doe",
	"customerEmail": "test@test.com",
	"address1": "",
	"address2": "",
	"city": "",
	"state": "",
	"zipcode": "00960",
	"trxID": "123456",
	"refNumber": "",
	"trxDescription": "Test",
	"trxAmount": "1",
	"cardNumber": "4548400000000631",
	"expDate": "1219",
	"cvv": "781",
	"trxTipAmount": "",
	"trxTax1": "",
	"trxTax2": "",
	"filler1": "",
	"filler2": "",
	"filler3": ""
}
```

### Response Payload

``` JSON
{
	"authNumber": "702814",
	"batchNumber": "225",
	"merchantid": "4549444000033",
	"postingdate": "0812",
	"rCode": "00",
	"rMsg": "Success",
	"refNumber": "024680003203",
	"requestID": "91e265a2683d76d",
	"systemTrace": "200468",
	"trxDatetime": "0812140030",
	"trxID": "123456",
	"trxoper": "sale",
	"trxtype": "credit"
}

```

## Reverse

### Request Payload

``` JSON
{
	"username": "CERT4549444000033",
	"password": "5B034VrA",
	"trxOper": "reverse",
	"accountID": "0001",
	"customerName": "Jesus",
	"customerEmail": "test@test.com",
	"address1": "",
	"address2": "",
	"city": "",
	"state": "",
	"zipcode": "00960",
	"trxID": "123456",
	"refNumber": "024680003207",
	"trxDescription": "Prueba",
	"trxAmount": "1",
	"cardNumber": "",
	"expDate": "",
	"cvv": "",
	"trxTax1": "",
	"trxTax2": "",
	"filler1": "",
	"filler2": "",
	"filler3": ""
}

```

### Response Payload

``` JSON
{
	"merchantid": "4549444000033",
	"rCode": "00",
	"rMsg": "Success",
	"refNumber": "024680003213",
	"requestID": "af46f32dc365ce4",
	"systemTrace": "200468",
	"trxDatetime": "0812145529",
	"trxID": "123456",
	"trxoper": "reverse",
	"trxtype": "credit"
}

```

## Refund

### Request Payload

``` JSON
{
	"username": "CERT4549444000033",
	"password": "5B034VrA",
	"trxOper": "refund",
	"accountID": "0001",
	"customerName": "Jesus",
	"customerEmail": "test@test.com",
	"address1": "",
	"address2": "",
	"city": "",
	"state": "",
	"zipcode": "00960",
	"trxID": "123456",
	"refNumber": "024680003207",
	"trxDescription": "Prueba",
	"trxAmount": "1",
	"cardNumber": "4548400000000631",
	"expDate": "1219",
	"cvv": "781",
	"trxTax1": "",
	"trxTax2": "",
	"filler1": "",
	"filler2": "",
	"filler3": ""
}

```

### Response Payload

``` JSON
{
	"authNumber": "003207",
	"batchNumber": "225",
	"merchantid": "4549444000033",
	"rCode": "00",
	"rMsg": "Success",
	"refNumber": "024680003207",
	"requestID": "0ae01bfc378dc64",
	"systemTrace": "200468",
	"trxDatetime": "0812143856",
	"trxID": "123456",
	"trxoper": "refund",
	"trxtype": "credit"
}

```