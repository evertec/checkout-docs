# Process Credit

In this service, there are no customizations since there are no screens associated with the payment process. The merchant must handle the service response and inform the result of the transaction to the client. The merchant must comply with regulations and data security standards establish by PCI.

## **Sale**

### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://mmpaytest.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/

A JSON payload sample can be found [here](../credit_sample#sale)

### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations:<br>&nbsp;&nbsp;&nbsp;&nbsp;Sale<br>&nbsp;&nbsp;&nbsp;&nbsp;Reverse<br>&nbsp;&nbsp;&nbsp;&nbsp;Refund | 4-10 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-50 | 
 | customerName | string | X | Customer name for the client of the merchant. | 1-100 | 
 | customerEmail | string | X | Customer email for the client of the merchant. | 1-100 | 
 | address1 | string |  | Client merchant address1. | 0-100 | 
 | address2 | string |  | Client merchant address2. | 0-100 | 
 | city | string |  | Client merchant city. | 0-100 | 
 | state | string |  | Client merchant state. | 0-100 | 
 | zipcode | string | X | Client merchant zip code. | 5 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | refNumber | string |  | Provided by authorized transaction. This field is required for refund or reverse transactions. | 1-20 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. Format 0.00 |  | 
 | trxTax1 | string |  | Tax1 value for the transaction. Format 0.00 |  | 
 | trxTax2 | string |  | Tax2 value for the transaction. Format 0.00 |  | 
 | cardNumber | string | X | Card number for the transaction. | 16-19 | 
 | expDate | string | X | Expiration date for the card number for the transaction. | 4 | 
 | cvv | string | X | Card Verification Value. | 3-4 | 
 | filler1 | string |  | Use for general value. | 0-50 | 
 | filler2 | string |  | Use for general value. | 0-50 | 
 | filler3 | string |  | Use for general value. | 0-50 | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | authNumber | string | Transaction authorization number. | 
 | batchNumber | string | Transaction batch number. | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | postingdate | string | Date when the transaction will be posted. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | systemTrace | string | System trace for the transaction. | 
 | trxDatetime | string | Transaction datetime. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation: SALE, REFUND or REVERSE. | 
 | trxtype | string | Transaction type: CREDIT. |

## **Reverse**

### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://mmpaytest.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/

A JSON payload sample can be found [here](../credit_sample#reverse)

### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations:<br>&nbsp;&nbsp;&nbsp;&nbsp;Sale<br>&nbsp;&nbsp;&nbsp;&nbsp;Reverse<br>&nbsp;&nbsp;&nbsp;&nbsp;Refund | 4-10 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-50 | 
 | customerName | string | X | Customer name for the client of the merchant. | 1-100 | 
 | customerEmail | string | X | Customer email for the client of the merchant. | 1-100 | 
 | address1 | string |  | Client merchant address1. | 0-100 | 
 | address2 | string |  | Client merchant address2. | 0-100 | 
 | city | string |  | Client merchant city. | 0-100 | 
 | state | string |  | Client merchant state. | 0-100 | 
 | zipcode | string | X | Client merchant zip code. | 5 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | refNumber | string | X | Provided by authorized transaction. This field is required for refund or reverse transactions. | 1-20 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. Format 0.00 |  | 
 | trxTax1 | string |  | Tax1 value for the transaction. Format 0.00 |  | 
 | trxTax2 | string |  | Tax2 value for the transaction. Format 0.00 |  | 
 | cardNumber | string |  | Card number for the transaction. | 16-19 | 
 | expDate | string |  | Expiration date for the card number for the transaction. | 4 | 
 | cvv | string |  | Card Verification Value. | 3-4 | 
 | filler1 | string |  | Use for general value. | 0-50 | 
 | filler2 | string |  | Use for general value. | 0-50 | 
 | filler3 | string |  | Use for general value. | 0-50 | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | systemTrace | string | System trace for the transaction. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation: SALE, REFUND or REVERSE. | 
 | trxtype | string | Transaction type: CREDIT. | 

## **Refund**

### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://mmpaytest.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/

A JSON payload sample can be found [here](../credit_sample#refund)

### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations:<br>&nbsp;&nbsp;&nbsp;&nbsp;Sale<br>&nbsp;&nbsp;&nbsp;&nbsp;Reverse<br>&nbsp;&nbsp;&nbsp;&nbsp;Refund | 4-10 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-50 | 
 | customerName | string | X | Customer name for the client of the merchant. | 1-100 | 
 | customerEmail | string | X | Customer email for the client of the merchant. | 1-100 | 
 | address1 | string |  | Client merchant address1. | 0-100 | 
 | address2 | string |  | Client merchant address2. | 0-100 | 
 | city | string |  | Client merchant city. | 0-100 | 
 | state | string |  | Client merchant state. | 0-100 | 
 | zipcode | string | X | Client merchant zip code. | 5 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | refNumber | string | X | Provided by authorized transaction. This field is required for refund or reverse transactions. | 1-20 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. Format 0.00 |  | 
 | trxTax1 | string |  | Tax1 value for the transaction. Format 0.00 |  | 
 | trxTax2 | string |  | Tax2 value for the transaction. Format 0.00 |  | 
 | cardNumber | string | X | Card number for the transaction. | 16-19 | 
 | expDate | string | X | Expiration date for the card number for the transaction. | 4 | 
 | cvv | string | X | Card Verification Value. | 3-4 | 
 | filler1 | string |  | Use for general value. | 0-50 | 
 | filler2 | string |  | Use for general value. | 0-50 | 
 | filler3 | string |  | Use for general value. | 0-50 | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | authNumber | string | Transaction authorization number. | 
 | batchNumber | string | Transaction batch number. | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | postingdate | string | Date when the transaction will be posted. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | systemTrace | string | System trace for the transaction. | 
 | trxDatetime | string | Transaction datetime. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation: SALE, REFUND or REVERSE. | 
 | trxtype | string | Transaction type: CREDIT. | 

