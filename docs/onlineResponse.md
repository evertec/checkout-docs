# Online Response

This service provides the merchant an alternative to access real-time results when a transaction is sent and authorized through the Web Payment Service. The result of a transaction is sent to the merchant using the http POST method to a URL address specified by the merchant. The Online Response is generated at the same time that the client receives the payment confirmation.

## Conditions

*	Evertec, Inc. is not responsible for the security measures implemented by the merchant to protect the sent information or the functionality of this webpage.
*	A transaction is considered completed once the client saw the Payment Confirmation screen. It is the merchant responsibility to make daily closings with the closing files sent every night.
*	If the merchant does not receive the data of a completed transaction, the completed transaction will not be reversed.
*	It is the merchant responsibility to use payment data to update their applications. Please make sure not to include the data more than once to avoid duplicate payments.
*	The URL (https) that will receive the transaction data will be developed and published by the Merchant.
*	The merchant may include an SSL certificate, issued by a renowned entity and deemed trustworthy. To authenticate, the certificate entity is verified. If the entity is well known, the certificate will be accepted by most browsers. When using a certificate, it must be registered and valid.
*	The URL must only be available to Evertec. The Merchant must validate that the webpage that receives the notification accepts only calls made from one of Evertec IP addresses.
*	For implementation, it is necessary to know the IP address where the webpage that receives the POST is located.
*	Evertec does not guarantee that the response will be received. Certain events in the Internet (communication problems, Merchant’s website unavailability, etc.) may prevent the POST.

## Service Description

This service returns a string with a maximum length of 133 characters. This string contains the data of a successful transaction, providing the Merchant a way to update their systems at the same time the transaction has been completed in the Web Service.

## Requisites

*	Webpage that only accepts values sent through the http POST method.
*	The URL and IP address must be informed to Evertec when filling out the Web Payment Service application form.

## Parameter Description

 | **Name** | **Description** | **Length** | 
 | :------- | :------------- | :--------- | 
 | VTransactionID | Transaction identifier | 26 | 
 | VAccountId | Customer account identifier | 20 | 
 | VTotalAmount | Total amount | 10 | 
 | VPaymentMethod | Payment method | 1 | 
 | VPaymentDescription | Payment description | 50 | 
 | VAuthorizationNum | Transaction authorization number | 6 | 
 | VConfirmationNum | Transaction confirmation number | 20 | 
 | VFILLER | Value of MerchantTransId field; formerly known as Tax5 | 50 | 

## Confirmation of Sent Message

Evertec expects the merchant’s web server to send an http response code that indicates that the data sent to the merchant’s URL was successfully received. This response is only informative for the Online Response service.

```
{
	statuscode = 200,
	description = OK
}
```


The service waits ten (10) seconds for a response confirming whether or not the message was received. After this wait, Evertec continues with its normal workflow, storing this response in a response log.
Note: If the merchant’s web server does not respond (200 OK) in the specified response time, the transaction is considered completed.
