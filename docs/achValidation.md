# ACH Validation



Bank account validation is a required process before processing an ACH transaction. This validation is through Plaid, a third-party service that allows validating bank accounts. It is necessary for the merchant to implement the verification screen “Plaid Link” in their services. This can be accessed through a URL and will be provided as part of the response message from the Process Credit service through the **rMsg** parameter.

![](images/screen_7.png)

The Plaid Link process is required for al clients that have not been validated or if they use a different account number. For accounts already validated, this process will not be necessary.

![](images/screen_2.png)

There are several types of bank account validation through the Plaid Link:

1. Instant Auth (credential-based) - Flow by default and is verified instantly.
2. Instant Match (Account and routing number based) - Alternate flow when instant auth is not available. Plaid will ask the user to enter their account number and routing number.
3. Automated Micro-Deposits - Plaid will make a micro-deposit and then automatically verify within one to two business days.
4. Same-Day Micro-Deposits – Plaid will make two deposits that will be posted within one business day. Customers are then instructed to manually verify deposited amount within one business day.


-The types of bank account validation depend on the affiliation of the financial institution to Plaid.
<br/>
-The minimum browser requirements for Plaid Link: Internet Explorer 11.



## Response Payload

``` JSON
{
	"authNumber": "",
    "batchNumber": "",
    "merchantid": "4549444000009",
    "rCode": "6000",
    "rMsg": "https://example.com",
    "refNumber": "",
    "requestID": "",
    "trxID": "",
    "trxoper": "payment",
    "trxtype": "ach"
}

```









