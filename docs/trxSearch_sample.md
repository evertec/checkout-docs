# Transaction Search

This section explains the details of integration of the Web Checkout service

## Request Payload

``` JSON
{
	"username": "CERT4549444000009",
    "password": "433NQ2nE",
	"accountID": "123456",
	"trxID": "123456",
	"trxAmount": "0.01"
}
```

## Response Payload

``` JSON
[
    {
        "authNumber": "228226",
        "batchNumber": "242",
        "merchantid": "632",
        "rCode": "00",
        "rMsg": "Success",
        "refNumber": "034680002858",
        "requestID": "5dffe79ab458b62",
        "statusCode": "0000",
        "trxDatetime": "8/29/2019 9:23:29 AM",
        "trxID": "123456",
        "trxoper": "sale",
        "trxtype": "ach"
    },
    {
        "authNumber": "384591",
        "batchNumber": "243",
        "merchantid": "632",
        "rCode": "00",
        "rMsg": "Success",
        "refNumber": "024680003257",
        "requestID": "c00500029e52b79",
        "statusCode": "0000",
        "trxDatetime": "8/30/2019 10:16:55 AM",
        "trxID": "123456",
        "trxoper": "sale",
        "trxtype": "credit"
    },
    {
        "authNumber": "681117",
        "batchNumber": "243",
        "merchantid": "632",
        "rCode": "00",
        "rMsg": "Success",
        "refNumber": "024680003258",
        "requestID": "6bc2abde228c0ba",
        "statusCode": "8003",
        "trxDatetime": "8/30/2019 10:24:33 AM",
        "trxID": "123456",
        "trxoper": "reverse",
        "trxtype": "credit"
    }
]
```