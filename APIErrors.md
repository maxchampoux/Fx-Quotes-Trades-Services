# API Error List #  

Hey there! You want to manage any error return and display it to you users as it should be? You are at the right place. 
Please have a look to the error list. This list may be updated.

| Error | HTTP Status | Error type | Error message |
|---|---|--------|----------------|
|1|418|Testing error|Here is the detail of the testing error.|
|2|400|Bad request|There is something wrong with the format of your X-WSSE header|
|3|403|Bad credentials|Either your login or password is wrong|
|4|500|WSSE authentication failed|Something went wrong with the WSSE authentication. Try again later.|
|5|400|Future date given|You put a date in the parameters that is in the future.|
|6|400|Nonce expired|Your nonce is expired. You should generate a new one with each request you do.|
|7|400|Digest is not as expected|Your digest is not as expected. Check the manual to know how to generate it.|
|8|500|Database writing failed|The object you submitted could not be recorded in our databases|
|9|400|Entry already exists|The object you submitted already exists|
|10|400|Missing field|A field is missing in your parameters.|
|11|400|Invalid argument|The IBAN you submitted for this account is not a valid IBAN.|
|12|400|Invalid argument|The currency you submitted for this account is not a valid currency.|
|13|404|Not found|The ressource requested was not found on this server|
|14|500|Payment not closed for account|You cannot delete an account which have payment not processed|
|15|401|Unauthorized|You must use the WSSE secured authentication to access this ressource|
|16|403|Forbidden|You do not have the permission to access this API. Contact our IT team to request an access.|
|17|400|Invalid argument|The object you submitted had an invalid type or format|
|18|404|Route not found|There is no route for the URL given. You may have forgotten some mandatory parameters. Check the API documentation for more informations.|
|19|400|Invalid argument|The country you submitted for this account is not a valid country.|
|20|400|Already deleted|The entry you tried to delete is already deleted|
|21|400|Nonce already used|The nonce you used for this request is already used for another. Try to generate a new one.|
|22|400|Invalid argument|The external bank account ID you submitted for this payment is not a valid external bank account ID.|
|23|400|Invalid argument|You have no deposit account available for the currency you submitted.|
|24|400|Invalid argument|The currency you submitted for this payment is not a valid currency.|
|25|400|Invalid argument|You have submitted a currency different from the destination account currency.|
|26|400|Invalid argument|The desired date of execution for the payment you submitted is not a valid date|
|27|400|Invalid argument|The fee currency you submitted for this payment is not a valid currency.|
|28|400|Invalid argument|The currency you submitted for this wallet was not a valid currency.|
|29|400|Entry already exists|You already have a wallet with this currency.|
|30|400|Invalid argument|The country you submitted for this wallet is not a valid country.|
|31|403|Forbidden|You do not have the permission to do this request.|
|32|400|Invalid argument|As you can have many wallets for one currency, you have to specify one with your payment.|
|33|400|Invalid argument|The priority option you submitted for this payment is not a valid priority option|
|34|400|Invalid argument|The source wallet you submitted for this trade is not a valid wallet|
|35|400|Invalid argument|The delivery wallet you submitted for this trade is not a valid wallet|
|36|400|Invalid argument|The quote you submitted for this trade is outdated, please request a new one.|
|37|400|Invalid argument|The source currency you submitted for this trade is not the same as the source account currency.|
|38|400|Invalid argument|The delivery currency you submitted for this trade is not the same as the delivery account currency.|
|39|400|Invalid argument|The currency related to the nominal amount of your request must equal of the currency source of your currency pair.|
|40|400|Invalid argument|The status you submitted for this request is not a valid status.|
|41|400|Invalid argument|The sorting method you submitted for this request is not a valid sorting method.|
|42|400|Invalid argument|The source wallet you submitted do not have the same currency of the quote source currency.|
|43|400|Invalid argument|The beneficiary wallet you submitted do not have the same currency of the quote beneficiary currency.|
|44|400|Invalid argument|You cannot submit a request with a null or zero amount.|
|45|400|Invalid argument|The side you submitted is not a valid side.|
|46|400|Invalid argument|The date you submitted to retrieve the balance is prior to the creation date of the wallet.|
|47|400|Invalid argument|The payment fee option you submitted is not a valid payment fee option.|
|48|400|Invalid argument|The currency of the source wallet is not the same as the currency of the beneficiary account.|
|49|400|Invalid argument|The currency pair you submitted for this trade is not a valid currency pair.|
|50|400|Invalid argument|The external bank account you submitted for this payment is not a valid external bank account.|
|51|400|Invalid argument|The clearing code type you submitted is not a valid clearing code type.|
|52|400|Invalid argument|The currency pair you submitted is not a valid currency pair, or contains invalid currencies.|
|53|400|Invalid argument|The amount you submitted for this payment exceed the payment amount limit.|
|54|400|Invalid argument|The date you specified for this request has an invalid format.|
|55|400|Invalid argument|The clearing code you submitted for this external bank account is not a valid clearing code.|
|56|403|Forbidden|You do not have the permission to access this request on the API.|
|57|400|Invalid argument|The holder type you submitted for this holder is not a valid holder type.|
|58|400|Market closed|The request you submitted needs the financial market to be open.|
|59|400|Not handled|The currency pair you submitted is not handled for trading or quotations.|
|60|400|Service unavailable|The trading service is currently unavailable, please try again later.|
|61|500|Internal server error|Something went wrong with the server, please try again later.|
|62|400|Invalid argument|The holder country needs a state to be specified.|
|63|400|Invalid argument|The state you submitted is not a valid state.|
|64|400|Invalid argument|The postcode you submitted is not a valid postcode.|
|65|403|Forbidden|You reached your API quota for this month. In order to execute more calls on the API, please refer to your API subscription plan.|
|66|400|Bad request|A X-WSSE-Requested-By HTTP header is mandatory, but was not in this request|
|67|403|Bad credentials|The X-WSSE-Requested-By value is wrong|
|68|400|Bad request|A X-WSSE-OTP HTTP header is mandatory, but was not in this request|
|69|400|Bad request|There is something wrong with the format of your X-WSSE-OTP header|
|70|400|Bad request|The OTP method you submitted with your X-WSSE-OTP is wrong|
|71|400|Bad credentials|The OTP authentication is wrong|
|72|403|Forbidden|The partner using the API do not have access to this request.|
|73|403|Bad credentials|The OTP session ID does not correspond to any OTP session on our system.|
|74|403|Forbidden|The OTP session expired.|
|75|403|Forbidden|The IP address of your request is not from your trusted IP.|
|76|400|Bad request|The document type you submitted is not a valid document type.|
|77|400|Bad request|
