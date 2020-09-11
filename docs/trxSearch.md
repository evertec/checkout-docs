# Transaction Search

This service allows the merchant to locate a specific transaction to verify its status. If the merchant needs to reverse a transaction, they need to know its requestId; this service provides a way to get it.

## Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessTransactionSearch/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessTransactionSearch/

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
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | authNumber | string | Transaction authorization number. | 
 | statusCode | string | This field show the transaction status in MMPY. | 
 | requestID | string | Request ID for the transaction. |  
