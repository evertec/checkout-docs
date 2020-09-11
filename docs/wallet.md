# Process Wallet 

In this service, there are no customizations since there are no screens associated with the payment process. The merchant must handle the service response and inform the result of the transaction to the client. The merchant must comply with regulations and data security standards establish by PCI.

***A previous configuration URL's is required to process ATH payments.**

## Customer Account 

The following services work with the creation, update and removal of a user account.

### Enrollment

The first step to execute a payment with a stored method of payment is for the merchant to enroll the customer to the Wallet service. With this service the merchant will enroll the customer and the method of payment of the customer.

#### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/Autopay/EnrollmentService.svc/Enroll
*	Production
	*	https://autopay.evertecinc.com/EnrollmentService.svc/Enroll

A JSON payload sample can be found [here](../wallet_sample#enrollment-edit)

#### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | enrollmentDate | string | X | Request date stamp format = “YYYY-MM-DD” | 10 | 
 | merchantUser | string | X | Username provided by EVERTEC for the merchant | 1-50 | 
 | customerAccountNumber | string | X | Customer account number related to merchant | 1-20 | 
 | firstName | string | X | Customer’s First Name | 1-50 | 
 | lastName | string | X | Customer’s Last Name | 1-50 | 
 | email | string | X | Customer’s Email | 1-100 | 
 | paymentType | string | X | See [Payment Method Codes](../paymentMethod) | 1 | 
 | cardNumber | number | X<sup>*</sup> | Credit card number. | 15-19 | 
 | cardExpirationDate | string | X<sup>*</sup> | Credit card expiration date. format=MMYY | 4 | 
 | cardCVV | number | X<sup>*</sup> | Card validation number | 4 | 
 | zipCode | number | X<sup>*</sup> | Card holder zip code | 5 | 
 | bankAccountNumber | number | X<sup>**</sup> | Bank Account Number. | 5-14 | 
 | routingNumber | number | X<sup>**</sup> | Bank Routing Number.<br> | 9 | 

!!! info
	<sup> * </sup>&nbsp;&nbsp;&nbsp;&nbsp;Required if paymentType = V, M, X<br>
	<sup> ** </sup>&nbsp;&nbsp;&nbsp;Required if paymentType = C, W, S

#### Request Structure
 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | hasError | string | TRUE or FALSE: TRUE if an error occurs | 
 | message | string | Description of Result | 
 | result | string | TRUE or FALSE: TRUE if no error occurs (will be the opposite of HasError parameter) | 

### Edit Customer

This service provides the functionality for modifying payment information in the service. The service updates the enrolled customer information. The process replaces the method of payment (credit card/bank account) that the customer has associated with your account number with the new information sent in the transaction.

#### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/Autopay/EnrollmentService.svc/EditEnroll
*	Production
	*	https://autopay.evertecinc.com/EnrollmentService.svc/EditEnroll

A JSON payload sample can be found [here](../wallet_sample#enrollment-edit)

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | enrollmentDate | string | X | Request date stamp format = “YYYY-MM-DD” | 10 | 
 | merchantUser | string | X | Username provided by EVERTEC for the merchant | 1-50 | 
 | customerAccountNumber | string | X | Customer account number related to merchant | 1-20 | 
 | firstName | string | X | Customer’s First Name | 1-50 | 
 | lastName | string | X | Customer’s Last Name | 1-50 | 
 | email | string | X | Customer’s Email | 1-100 | 
 | paymentType | string | X | See [Payment Method Codes](../paymentMethod) | 1 | 
 | cardNumber | number | X<sup>*</sup> | Credit card number. | 15-19 | 
 | cardExpirationDate | string | X<sup>*</sup> | Credit card expiration date. format=MMYY | 4 | 
 | cardCVV | number | X<sup>*</sup> | Card validation number | 4 | 
 | zipCode | number | X<sup>*</sup> | Card holder zip code | 5 | 
 | bankAccountNumber | number | X<sup>**</sup> | Bank Account Number. | 5-14 | 
 | routingNumber | number | X<sup>**</sup> | Bank Routing Number.<br> | 9 | 

!!! info
	<sup> * </sup>&nbsp;&nbsp;&nbsp;&nbsp;Required if paymentType = V, M, X<br>
	<sup> ** </sup>&nbsp;&nbsp;&nbsp;Required if paymentType = C, W, S


#### Response Structure
 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | hasError | string | TRUE or FALSE: TRUE if an error occurs | 
 | message | string | Description of Result | 
 | result | string | TRUE or FALSE: TRUE if no error occurs (will be the opposite of HasError parameter) | 

### Delete Customer

This service provides the functionality for delete payment information in the service. The service deletes the enrolled customer information from the system.

#### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/Autopay/EnrollmentService.svc/DeleteEnroll
*	Production
	*	https://autopay.evertecinc.com/EnrollmentService.svc/DeleteEnroll

A JSON payload sample can be found [here](../wallet_sample#delete)

#### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | merchantUser | string | X | Username provided by EVERTEC for the merchant | 1-50 | 
 | customerAccountNumber | string | X | Customer account number related to merchant | 1-20 | 
 | email | string | X | Customer’s Email | 1-100 | 

#### Response Structure
 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | hasError | string | TRUE or FALSE: TRUE if an error occurs | 
 | message | string | Description of Result | 
 | result | string | TRUE or FALSE: TRUE if no error occurs (will be the opposite of HasError parameter) | 

## Transaction Processing

The following services work with the execution of different transactions related to sale, reverse and refund.

### Sale Transaction

This service will execute a transaction using the stored method of payment of the customer in the service.

#### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessWalletTransaction/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessWalletTransaction/

A JSON payload sample can be found [here](../wallet_sample#sale)

#### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username  | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations: Sale | 4-10 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-20 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | refNumber | string |  | Provided by authorized transaction. This field is required for refund or reverse transactions. | 1-20 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. | 0.0m | 
 | filler1 | string |  | Use for general value. | 0-50 | 

#### Response Structure for Credit
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
 | trxOper | string | Transaction operation. This field must contain SALE, REFUND or REVERSE values. | 
 | trxtype | string | Transaction type. This field must contain DEBIT, CREDIT or ACH values. | 

#### Response Structure for ACH
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
 | trxOper | string | Transaction operation. This field must contain SALE, REFUND or REVERSE values. | 
 | trxtype | string | Transaction type. This field must contain DEBIT, CREDIT or ACH values. | 

#### Response Structure for ATH
| **Parameter** | **Type** | **Description** | 
| :------------ | :------: | :-------------- | 
| rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
| rMsg | string | Transaction response message. This field must contain a pinpad URL if rCode is 00 (succesfull). | 

### Reverse Transaction

This service will reverse a transaction.

#### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessWalletTransaction/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessWalletTransaction/

A JSON payload sample can be found [here](../wallet_sample#reverse)

#### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username  | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations: Reverse | 4-10 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-20 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | refNumber | string |  | Provided by authorized transaction. This field is required for refund or reverse transactions. | 1-20 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. | 0.0m | 
 | filler1 | string |  | Use for general value. | 0-50 | 

#### Response Structure for Credit
 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | systemTrace | string | System trace for the transaction. | 
 | trxDatetime | string | Transaction datetime. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation. This field must contain SALE, REFUND or REVERSE values. | 
 | trxtype | string | Transaction type. This field must contain DEBIT, CREDIT or ACH values. | 

#### Response Structure for ACH
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
 | trxOper | string | Transaction operation. This field must contain SALE, REFUND or REVERSE values. | 
 | trxtype | string | Transaction type. This field must contain DEBIT, CREDIT or ACH values. | 

### Refund Transaction

This service will execute a transaction using the stored method of payment of the customer in the service.

#### Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://uat.mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessWalletTransaction/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessWalletTransaction/

A JSON payload sample can be found [here](../wallet_sample#refund)

#### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username  | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | trxOper | string | X | Transaction operations: Refund | 4-10 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-20 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | refNumber | string |  | Provided by authorized transaction. This field is required for refund or reverse transactions. | 1-20 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. | 0.0m | 
 | filler1 | string |  | Use for general value. | 0-50 | 

#### Response Structure for Credit
 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | authNumber | string | Transaction authorization number. | 
 | batchNumber | string | Transaction batch number. | 
 | merchantid | string | Merchant number provided by Evertec. | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. | 
 | refNumber | string | Transaction reference number. | 
 | requestID | string | Request ID for the transaction. | 
 | systemTrace | string | System trace for the transaction. | 
 | trxDatetime | string | Transaction datetime. | 
 | trxID | string | transaction ID. | 
 | trxOper | string | Transaction operation. This field must contain SALE, REFUND or REVERSE values. | 
 | trxtype | string | Transaction type. This field must contain DEBIT, CREDIT or ACH values. |  
