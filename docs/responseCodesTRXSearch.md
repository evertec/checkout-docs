# Response Codes

## Transaction Search: **statusCode**
|**statusCode**|**Description**|
|:------------|:--------------|
|0001|Transaction initiated (The transaction has not been sent for processing)|
|0000|Transaction approved|
|8003|Transaction reversed|
|8004|Refund completed|
|8005|Refund failed|
|3092|Payment process was not completed or transaction was canceled|

## Transaction Search: **rCode**
|**rCode**|**Description**|
|:------------|:--------------|
|00|Transaction search completed. It does not represent the status of the transaction|
|4000|Invalid field. See **rMsg** response for details.|
|4001|Authentication error (Invalid merchant username or password)|
|4002|Invalid IP|
|9999|Generic error. Contact EVERTEC service desk.|

<br>

* An **empty string** response (**HTTP 200 OK**) means that no transaction was found that matches the data received in the transaction search method.
* Take into consideration that after the reconciliation process, the status of the transactions may change.
* The range for the transaction search at the data level is limited until 3:00 AM the next day, for those transactions that have been included in the reconciliation process.
* It is recommended that the merchant reconciles the transactions using the Lockbox files, LogFile, and PDF Report.



