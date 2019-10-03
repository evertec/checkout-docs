# ACH

This section explains the details of integration of the Web Checkout service

## Enrollment / Edit

#### Request Payload

``` JSON
{
	"EnrollmentRequestMessage":
	{
		"EnrollmentDate":"/Date(2019-01-10T17:29:53.542Z)/",
		"MerchantUser":"CERT4549444000009",
		"CustomerAccountNumber":"1711",
		"FirstName":"John",
		"LastName":"Doe",
		"Email":"test@test.com",
		"PaymentType":"V",
		"CardNumber":"4548400000000631",
		"CardExpirationDate":"1219",
		"CardCVV":"781",
		"ZipCode":"00960",
		"BankAccountNumber":"",
		"RoutingNumber":""
	}
}
```

#### Response Payload

``` JSON
{
	"AutoPayResponseMessage":
	{
		"HasError": false,
		"Message": "AccountNumber: 1711 was created successfully!",
		"Result": true
	}
}
```

## Delete

### Request Payload

``` JSON
{
	"DeleteEnrollmentRequestMessage":
	{
		"MerchantUser":"CERT4549444000009",
		"CustomerAccountNumber":"1711",
		"Email":"test@test.com"
	}
}
```

### Response Payload

``` JSON
{
	"AutoPayResponseMessage":
	{
		"HasError": false,
		"Message": " AccountNumber: 1711 was deleted successfully!",
		"Result": true
	}
}

```

## Sale

### Request Payload

``` JSON
{
	"username": "CERT4549444000009",
	"password": "433NQ2nE",
	"trxOper": "sale",
	"accountID": "1711",
	"trxID": "123456",
	"trxAmount": "1.00",
	"refNumber": "",
	"trxDescription": "Description",
	"filler1": ""
}

```

### Credit Response Payload

``` JSON
{
    "authNumber": "681117",
    "batchNumber": "243",
    "merchantid": "4549444000009",
    "postingdate": "0830",
    "rCode": "00",
    "rMsg": "Success",
    "refNumber": "024680003258",
    "requestID": "6bc2abde228c0ba",
    "systemTrace": "200468",
    "trxDatetime": "0830142436",
    "trxID": "123456",
    "trxoper": "sale",
    "trxtype": "credit"
}
```

### ACH Response Payload

``` JSON
{
    "authNumber": "228233",
    "batchNumber": "243",
    "merchantid": "4549444000009",
    "rCode": "0000",
    "rMsg": "Transaction received and approved",
    "refNumber": "034680002874",
    "requestID": "49e38b2f885c758",
    "trxID": "123456",
    "trxoper": "sale",
    "trxtype": "ach"
}
```

## Reverse

### Request Payload

``` JSON
{
    "username": "CERT4549444000009",
    "password": "433NQ2nE",
    "trxOper": "reverse",
    "accountID": "12345678901234567890",
    "trxID": "123456",
    "trxAmount": "",
    "refNumber": "024680003258",
    "trxDescription": "Description",
    "filler1": ""
}
```

### Credit Response Payload

``` JSON
{
    "merchantid": "4549444000009",
    "rCode": "00",
    "rMsg": "Success",
    "refNumber": "024680003258",
    "requestID": "5f1dc06a1224488",
    "systemTrace": "200468",
    "trxDatetime": "0830144205",
    "trxID": "123456",
    "trxoper": "reverse",
    "trxtype": "credit"
}
```

### ACH Response Payload

``` JSON
{
    "authNumber": "228234",
    "batchNumber": "243",
    "merchantid": "4549444000009",
    "rCode": "0000",
    "rMsg": "Transaction received and approved",
    "refNumber": "034680002875",
    "requestID": "173633b4367827d",
    "trxID": "123456",
    "trxoper": "reverse",
    "trxtype": "ach"
}
```

## Refund

### Request Payload

``` JSON
{
    "username": "CERT4549444000009",
    "password": "433NQ2nE",
    "trxOper": "refund",
    "accountID": "12345678901234567890",
    "trxID": "123456",
    "trxAmount": "1",
    "refNumber": "024680003259",
    "trxDescription": "Description",
    "filler1": ""
}
```

### Credit Response Payload

``` JSON
{
    "authNumber": "003259",
    "batchNumber": "243",
    "merchantid": "4549444000009",
    "rCode": "00",
    "rMsg": "Success",
    "refNumber": "024680003259",
    "requestID": "5ef6acf121b066d",
    "systemTrace": "200468",
    "trxDatetime": "0830144407",
    "trxID": "123456",
    "trxoper": "refund",
    "trxtype": "credit"
}
```
