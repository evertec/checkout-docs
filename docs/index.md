# Checkout Technical Documentation

Checkout is a complete online payment solution that allows merchants to easily accept electronic payments of credit cards, debit cards (including the ATH® debit card with PIN, the debit card most commonly used in Puerto Rico) and checking and savings accounts through the ACH network.

## Implementation methods

Checkout offers several ways to accept payments.

You can use the prebuild payment module on your website or application. If you want to customize your payment workflow, you can build your own integration using Checkout APIs.

1.	Payment module
	*	Checkout offers a payment module where the payment information can be capture for the pressing of a transaction
2.	APIs
	*	Checkout also APIs that can be invoked directly from the commerce site. In this way, merchants can control the interface where the customer enters the payment information and only use the services for processing and authorizing the payment.

## Payment services

Checkout includes several payment services that can be used through Web Checkout or consume directly through the Direct Connection. Some of these services include a graphical interface and others are web services without graphical interface.

### Payment Module

1.	[Web Checkout](webCheckout)
	*	A secure web page that allows the capture of the customer's payment information and process the transaction. This reduces the risk of the transaction, since the sensitive information provided by the client is handled only by Web Checkout. Web Checkout has a "responsive" interface which adjusts to the size of the screen of the device that is being accessed, allowing the customer experience to be the same always.

### APIs

1.	[Process Credit](credit)
	*	Service for the processing of payment, void and refund of transactions with a Visa, MasterCard and American Express
2.	[Process ACH](ach)
	*	Service for the processing of payment and reverse of transactions with a checking or savings bank account
3.	[Process Wallet](wallet)
	*	Service that allows the merchant to save a payment method (credit card or bank account) of a customer and process payments, reversals and refunds at any time using the saved payment method. Typically, it is used for recurring payments or subscriptions. The customer's payment information is tokenized and stored in a secure environment. Each client must be registered in the service. A unique identifier will be assigned per client that the merchant will have to provide in order to make future charges.
4.	[Transaction Search](trxSearch)
	*	Service that consults and provides the status of a transaction. It helps commerce to improve the user experience by being able to know the status of a transaction at any time. It is also very useful for customer service issues.

## Important Information

To ensure the security of the data from the customers and merchants and to comply with PCI DSS, we have established the following procedures:

1.	Every connection from the merchant’s application to any of our services has to be made through TLS 1.1 or greater.
2.	All communications between Evertec and the merchant will be processed through https requests.
3.	When a merchant registers for the service they are assigned a username and password. The merchant uses the username / password combination as a key for payment requests.
4.	The merchant must provide a list IP addresses from which the payment service will be accessed. This means that in each call to the service, the merchant identification is validated, as well as the address from which the call is made.
5.	All merchants have to complete the <a href="https://www.pcisecuritystandards.org/pci_security/completing_self_assessment" target="_blank">Self-Assessment Questionnaire (SAQ)</a>.
	*	This questionnaire is designed as a self-validation tool to assess security for cardholder data. The SAQ includes a series of yes-or-no questions for each applicable PCI Data Security Standard requirement. There are different questionnaires available to meet different merchant environments. You can easily find the SAQ that best describes how you accept payment cards.
	*	To help merchants complete the SAQ, we have a portal available which allows them to complete the questionnaire annually <a href="https://pciportal.gmsectec.com/Merchant/MerchantRegistration" target="_blank">https://pciportal.gmsectec.com/Merchant/MerchantRegistration</a>.
	