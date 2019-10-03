# ACH

This section explains the details of integration of the Web Checkout service

## Sale

### Request Payload

``` JSON
{
	"username": "CERT4549444000009",
	"password": "433NQ2nE",
	"trxOper": "sale",
	"accountID": "0001",
	"customerName": "John Doe",
	"customerEmail": "test@test.com",
	"address1": "address1",
	"address2": "address2",
	"city": "city",
	"state": "state",
	"zipcode": "00960",
	"trxID": "123456",
	"refNumber": "",
	"trxDescription": "Prueba",
	"trxAmount": "0.01",
	"bankAccount": "132456798",
	"routing": "021502011",
	"accType":"w",
	"filler1": "",
	"filler2": "",
	"filler3": ""
}

```

### Response Payload

``` JSON
{
	"authNumber": "227527",
	"batchNumber": "225",
	"merchantid": "4549444000009",
	"rCode": "0000",
	"rMsg": "Transaction received and approved",
	"refNumber": "034680002833",
	"requestID": "573630eab413298",
	"trxID": "123456",
	"trxoper": "payment",
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
	"accountID": "0001",
	"customerName": "John Doe",
	"customerEmail": "test@test.com",
	"address1": "",
	"address2": "",
	"city": "",
	"state": "",
	"zipcode": "00960",
	"trxID": "123456",
	"refNumber": "034680002834",
	"trxDescription": "Prueba",
	"trxAmount": "0.01",
	"bankAccount": "",
	"routing": "",
	"accType":"",
	"filler1": "",
	"filler2": "",
	"filler3": ""
}

```

### Response Payload

``` JSON
{
	"authNumber": "227535",
	"batchNumber": "225",
	"merchantid": "4549444000009",
	"rCode": "0000",
	"rMsg": "Transaction received and approved",
	"refNumber": "034680002834",
	"requestID": "e4d47bb2932b4fc",
	"trxID": "123456",
	"trxoper": "reverse",
	"trxtype": "ach"
}

```