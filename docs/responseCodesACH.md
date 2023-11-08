# Response Codes

## Process ACH
|**rCode**|**rMsg**|
|:------------|:--------------|
|0000|Transaction received and approved|
|0006|Invalid field received: accttype|
|0026|Invalid field received: routingnumber|
|4000|Invalid field. See rMsg response. Ex. [ Invalid trxOper field, Invalid customerEmail format, Invalid zipcode, trxAmount format error. Ex. 1000.00,  filler1 cannot be greater than 50, filler2 cannot be greater than 50]
|9999|Generic error|

## Process ACH : ACH Validation
 | **rCode** | **rMsg** | 
 | :------------ | :-------------- | 
 | 6000 | Plaid Link URL successfully created | 
 | 6001 | Insufficient Funds Available |
 | 6002 | Decline - Back account pre-verification could not be completed | 
 | 6003 | Decline - Bank account information is invalid |
| 6004 | The financial institution indicated that the user's password or MFA information has changed. The client have to validate through the Plaid Link again. <span style="color:red">*new*</span> | 