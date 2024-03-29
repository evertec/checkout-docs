# Transaction Search

This service allows the merchant to locate a specific transaction to verify its status. If the merchant needs to reverse a transaction, they need to know its requestId; this service provides a way to get it.

## Parameter Description

The  URLs of this service are the following:

*	<b>Development</b> - 
	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessTransactionSearch/
*	<b>Production</b> - 
	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessTransactionSearch/

### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username  | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-20 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. | 0.0m | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | trxtype | string | Transaction type. This field must contain DEBIT, CREDIT or ACH values. | 
 | trxOper | string | Transaction operation. This field must contain SALE, REFUND or REVERSE values. | 
 | trxID | string | transaction ID. | 
 | trxDatetime | string | Transaction datetime. | 
 | refNumber | string | Transaction reference number. | 
 | batchNumber | string | Transaction batch number. | 
 | rCode | string | Transacion Search response status. Not transaction status| 
 | rMsg | string | Transaction Search response message. Not transaction status| 
 | authNumber | string | Transaction authorization number. | 
 | statusCode | string | This field show the transaction status in MMPY. See [Response Codes](../responseCodesTRXSearch).  | 
 | requestID | string | Request ID for the transaction. |  
