# Web Checkout

This section explains the details of integration of the Web Checkout service

## Payment Process Description

The process begins with the merchant, when a client clicks the payment button implemented in the merchant’s website, after the merchant displayed the amount to be paid to the customer. The amount will remain unchanged when being sent to the service; the transaction will reflect what the merchant sends as the paid amount.

The merchant’s application processes the client’s payment through the web service, which links it to Web Checkout. When the merchant uses the web service, the web service call must include the parameters specified in [this section](#parameter-description)

The web service receives the merchant’s request and redirects to Web Checkout. This Payment Service consists of three main pages. The first page asks the Client to select a payment method, the second page displays the information the Client just entered for confirmation, and a third page shows the result of the payment transaction.

## Customizable Screen Elements

This section presents the different screens elements that Web Checkout allows merchants to customize.

### Payment Methods

In Web Checkout the merchant has the ability to accept the following methods of payment:

* ACH (personal, savings, commercial)
* Visa credit & debit card
* MasterCard credit & debit card
* American Express credit card
* ATH® debit card from financial institutions certified by the ATH® Network

### Payment Method Selection Screen

![](images/screen_1.png)

The previous image shows the screen where the client selects the payment method and it includes references to the merchant customizable elements.

 | **Reference** | **Description** | 
 | :---: | --- | 
 | 1 | Merchant image or logo. Must be in JPEG format and must not exceed the 100KB. The dimensions for the logo/image  are 700 x 100. | 
 | 2 | Title that identifies the customer (i.e. Subscriber, Insured, etc.) | 
 | 3 | The merchant can specify the label to identify the accountID parameter sent in the parameters (i.e. Subscription, Membership, etc.).<br><br>**Note**: Depending on the sensitivity of this information, the Merchant may choose a mask that shows only the last 4 digits. | 
 | 4 | The merchant can specify a URL to which the client will be returned to if the button is pressed.<br><br>**Note**: By default, this button just closes the window/tab | 
 | 5 | Label for the Return Policy link (i.e. Terms & Conditions, etc.).<br><br>**Note** : By default, value is Refund Policy | 

### Address Verification Service

The Address Verification System (AVS) is a system used to verify the address of a person claiming to own a credit card. The system will check the billing address of the credit card provided by the user with the address on file at the credit card company or issuing bank.

Checkout offers this service in a limited way. When active, Checkout will request the zip code related to the billing address of the credit card and send the information in the authorization message. If the zip codes do not match, Checkout will automatically reverse the transaction (if it was authorized) and display a message to the customer indicating that they need to review the payment information.

This service is only available for Web Checkout.

### Implementation

The merchant must be registered in Evertec’s Checkout service and must have a username and a password. Evertec must also know the IP address from which the merchant will access the service. Therefore, the programming to use the service must be on the server side to validate correctly the IP address from which the service is being accessed.

Once the Merchant has sent the required parameters to the web service, it will return a response in case of a successful verification, the Web Checkout URL is: *https://checkout.evertecinc.com/V2?Token+Language*. The merchant has to redirect the customer to the URL of this response.

In case of an unsuccessful transaction, the service may return: a code with an error number (See possible response codes on the “Response Codes” section) or an error message.

The programmer must have special considerations when programming the payment button. For example, once the user clicks on the button, it may become disabled and display a message that indicates that the transaction is being processed. Please include any mechanism that simulates this wait, this so to prevent the user from clicking on the button multiple times. Every time the user clicks, a new Token request is made, and this generates failed transactions, once the Token has expired, they become Timeout-Expired transactions.

## Parameter Description

The  URLs of this service are the following:

*	Development
	*	https://mmpaytest.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCheckoutPayment/
*	Production
	*	https://mmpay.evertecinc.com/WebPaymentAPI/WebPaymentAPI.svc/ProcessCheckoutPayment/

A JSON payload sample can be found [here](../webCheckout_sample#request-payload)

### Request Structure

 | **Parameter** | **Type** | **Required** | **Description** | **Length** | 
 | :------------ | :------: | :----------: | :-------------- | :--------: | 
 | username  | string | X | Merchant username provided by Evertec. | 1-50 | 
 | password | string | X | Merchant password provided by Evertec. | 1-50 | 
 | accountID | string | X | Account number for the client of the merchant. | 1-20 | 
 | customerName | string | X | Customer name for the client of the merchant. | 1-100 | 
 | customerEmail | string | X | Customer email for the client of the merchant. | 1-100 | 
 | address1 | string |  | Client merchant address1. | 0-100 | 
 | address2 | string |  | Client merchant address2. | 0-100 | 
 | city | string |  | Client merchant city. | 0-100 | 
 | state | string |  | Client merchant state. | 0-100 | 
 | zipcode | string | X | Client merchant zip code. | 5 | 
 | phone | string |  | Client merchant phone. | 1-12 | 
 | fax | string |  | Client merchant fax. | 1-12 | 
 | trxID | string | X | Merchant unique transaction value. | 1-50 | 
 | trxDescription | string | X | Merchant transaction description value. | 1-50 | 
 | trxAmount | string | X | Amount for the transaction. | 0.0m | 
 | taxAmount1 | string |  | taxAmount1 value for the transaction. | 0.0m | 
 | taxAmount2 | string |  | taxAmount2 value for the transaction. | 0.0m | 
 | taxAmount3 | string |  | taxAmount3 value for the transaction. | 0.0m | 
 | language | string | X | Language for the transaction.<br><br>en – English / es - Spanish | 2 | 
 | ignoreValues | string |  | Card type that the merchant doesn’t like for the transaction. See [Payment Method Codes](../paymentMethod). | 0-9 | 
 | filler1 | string |  | Use for general value. | 0-50 | 
 | filler2 | string |  | Use for general value. | 0-50 | 
 | filler3 | string |  | Use for general value. | 0-50 | 

### Response Structure

 | **Parameter** | **Type** | **Description** | 
 | :------------ | :------: | :-------------- | 
 | rCode | string | Transaction response code. See [Response Codes](../responseCodes). | 
 | rMsg | string | Transaction response message. This message includes the checkout URL if the rCode is “00” | 
 | requestID | string | Request ID for the transaction. | 

## Error messages displayed in Web Checkout

Web Checkout validates the following information before proceeding with the authorization:

*	Valid format of card number
*	Valid bank’s routing number

If the customer enters invalid information about the method of payment, the system will show an error message when the payment is rejected. The payment can be rejected by any of the following reasons:

*	The card number is incorrect
*	The expiration date is incorrect
*	The CVV is incorrect
*	The PIN entered for an ATH<sup>®</sup> card is incorrect
*	The bank account or card does not have sufficient funds
*	The routing number entered is invalid
*	The bank account number is not valid

If the Web Checkout page is idle for more than 15 minutes the customer will get an error message indicating that the session expired and will be redirected to the merchant’s page. 
