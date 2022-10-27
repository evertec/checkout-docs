# Process ACH

In this service, there are no customizations since there are no screens associated with the payment process. The merchant must handle the service response and inform the result of the transaction to the client. The merchant must comply with regulations and data security standards establish by NACHA.

### ACH Validation

As part of the security measures, the validation of bank account is a required process before processing an ACH transaction. This validation is through Plaid, a third-party service that allows the client to instantly connect their financial account through different options. For more information see [ACH Services](../achServices). 

## **Sale**

### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessACH/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessACH/

A JSON payload sample can be found [here](../ach_sample#sale)

### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations:<br>&nbsp;&nbsp;&nbsp;&nbsp;Sale<br>&nbsp;&nbsp;&nbsp;&nbsp;Reverse | 4-10 | 
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
 | bankAccount | string | X | Bank account number for the transaction. | 1-17 | 
 | routing | string | X | Routing number of the account's bank | 9 | 
 | accType | string | X | Account type.<br>&nbsp;&nbsp;&nbsp;&nbsp;W – Personal checking.<br>&nbsp;&nbsp;&nbsp;&nbsp;S – Personal Saving.<br>&nbsp;&nbsp;&nbsp;&nbsp;C – Commercial checking. | 1 | 
 | filler1 | string |  | Use for general value. | 0-50 | 
 | filler2 | string |  | Use for general value. | 0-50 | 
 | filler3 | string |  | Use for general value. | 0-50 | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | authNumber | string | Transaction authorization number. | 
 | batchNumber | string | Transaction batch number. | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation: SALE or REVERSE. | 
 | trxtype | string | Transaction type: ACH | 

## **Reverse**

### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessACH/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCredit/

A JSON payload sample can be found [here](../ach_sample#reverse)

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
 | bankAccount | string | X | Bank account number for the transaction. | 1-17 | 
 | routing | string | X | Routing number of the account's bank | 9 | 
 | accType | string | X | Account type.<br>&nbsp;&nbsp;&nbsp;&nbsp;W – Personal checking.<br>&nbsp;&nbsp;&nbsp;&nbsp;S – Personal Saving.<br>&nbsp;&nbsp;&nbsp;&nbsp;C – Commercial checking. | 1 | 
 | filler1 | string |  | Use for general value. | 0-50 | 
 | filler2 | string |  | Use for general value. | 0-50 | 
 | filler3 | string |  | Use for general value. | 0-50 | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | authNumber | string | Transaction authorization number. | 
 | batchNumber | string | Transaction batch number. | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation: SALE or REVERSE. | 
 | trxtype | string | Transaction type: ACH | 

## **ACH Validation**

The merchant must handle the response and implementation of the "Plaid Link" verification screen. This can be accessed through a URL and will be provided as part of the response message.
The ACH validation response message will be through an ACH sale using <b>ProcessACH</b>.

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------ | :-------------- | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | "Plaid Link" URL. | 

### Response Codes

 | **rCode** | **rMsg** | 
 | :------------ | :-------------- | 
 | 6000 | Plaid Link URL successfully created | 
 | 6001 | Insufficient Funds Available |
 | 6002 | Decline - Back account pre-verification could not be completed | 
 | 6003 | Decline - Bank account information is invalid |
 | 6004 | The financial institution indicated that the user's password or MFA information has changed. The client have to validate through the Plaid Link again. <span style="color:red">*new*</span> | 

### User status on Plaid Link &nbsp;<span style="color:red;font-size:10pt">*new*</span>

This allows to know if the client finished the validation flow through the Plaid link correctly, the merchant must create a listener process in the JavaScript file. This response does not indicate the validation status of the client through Plain Link.
This is just information to indicate if the user's interaction with the plaid screens ended successfully or was closed by the user or by some response error from Plaid.

Object emitted if the user closes the Plaid Link window or if the flow terminates successfully. This will be of type String, which should be cast to JSON.

Example:
``` JSON
{
	"finishedProcess": true,
    "ClosedByuser": false
}

```
Event response:

 | **FinishedProcess** | **ClosedByUser** | **Meaning** | 
 | :------------ | :------ | :-------------- | 
 | True | False | Successful process. | 
 | True | True | Canceled by user. | 
 | True | False | Plaid process error. | 