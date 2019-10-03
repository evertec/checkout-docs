# ACH Services

## ACH Return

This additional service is optional in the configuration of the Web Payments Service. It is an agreement between the merchant and the Bank. The service consists in generating a report with returned ACH transactions. Additionally, the completed transactions file features a layout that includes returned transactions.

## ACH Verification Service

This additional service is optional in the configuration of the Web Payments Service. To use this service, the merchant must define a formula that will be used to reject ACH payments. This service searches a Returned ACH Transactions database that contains transactions returned for different reasons at different dates. The merchant’s formula must define quantity of occurrences, frequency and return code. An ACH payment will be rejected if it satisfies the formula.

##ACH Local Bank Service

This additional service is optional in the configuration of the Web Payments Service. This service is used for merchants who do not wish to allow clients to make ACH payments with foreign bank accounts. Once the service is activated for the merchant, every time an ACH transaction is attempted, the associated account will be verified. In case of a negative response, the transaction will be declined.

## ACH BPPR Hold Service[^1]

This additional service is optional in the configuration of the Web Payments Service. This service may be used if the merchant wishes to validate ACH payments made with BPPR accounts. When a client makes a payment with a BPPR account, the transaction amount is put on hold, guaranteeing that the transaction will not be returned for insufficient funds. If the account does not have sufficient funds, the transaction will be declined.

[^1]: This service is only available for Banco Popular's merchants.