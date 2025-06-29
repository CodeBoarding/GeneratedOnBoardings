```mermaid
graph LR
    API_Resource_Endpoints["API Resource Endpoints"]
    HTTP_Request_Handler["HTTP Request Handler"]
    API_Response_Parser["API Response Parser"]
    Authentication_Module["Authentication Module"]
    API_Data_Models["API Data Models"]
    OAuth_Client["OAuth Client"]
    Error_Handling["Error Handling"]
    Utility_Functions["Utility Functions"]
    API_Resource_Endpoints -- "initiates requests via" --> HTTP_Request_Handler
    API_Resource_Endpoints -- "parses responses with" --> API_Response_Parser
    HTTP_Request_Handler -- "uses" --> Authentication_Module
    HTTP_Request_Handler -- "uses" --> Error_Handling
    API_Response_Parser -- "creates" --> API_Data_Models
    OAuth_Client -- "extends" --> API_Resource_Endpoints
    OAuth_Client -- "manages authentication via" --> Authentication_Module
    API_Resource_Endpoints -- "uses" --> Utility_Functions
    HTTP_Request_Handler -- "uses" --> Utility_Functions
    API_Response_Parser -- "uses" --> Utility_Functions
    Authentication_Module -- "uses" --> Utility_Functions
```
[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Component Details

This component overview describes the structure and interactions of the `coinbase-python` library's core components, focusing on how API requests are initiated, handled, authenticated, and how responses are parsed into structured data models, along with error handling and utility functions.

### API Resource Endpoints
Provides a comprehensive set of methods for interacting with various Coinbase API resources, including market data, user information, accounts, notifications, addresses, transactions, reports, buy/sell operations, deposits/withdrawals, payment methods, merchants, orders, and checkouts. These methods abstract the underlying HTTP requests and data mapping.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L207-L210" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_currencies` (207:210)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L212-L215" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_exchange_rates` (212:215)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L217-L221" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_buy_price` (217:221)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L223-L227" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_sell_price` (223:227)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L229-L233" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_spot_price` (229:233)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L235-L242" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_historic_prices` (235:242)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L244-L247" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_time` (244:247)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L251-L254" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_user` (251:254)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L256-L259" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_current_user` (256:259)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L261-L264" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_auth_info` (261:264)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L266-L269" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:update_current_user` (266:269)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L273-L276" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_accounts` (273:276)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L278-L281" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_account` (278:281)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L283-L285" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_primary_account` (283:285)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L287-L290" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:create_account` (287:290)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L292-L295" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:set_primary_account` (292:295)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L297-L300" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:update_account` (297:300)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L302-L305" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:delete_account` (302:305)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L309-L312" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_notifications` (309:312)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L314-L317" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_notification` (314:317)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L321-L324" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_addresses` (321:324)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L326-L329" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_address` (326:329)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L331-L341" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_address_transactions` (331:341)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L343-L346" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:create_address` (343:346)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L350-L353" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_transactions` (350:353)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L355-L359" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_transaction` (355:359)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L361-L368" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:send_money` (361:368)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L370-L377" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:transfer_money` (370:377)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L379-L386" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:request_money` (379:386)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L388-L393" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:complete_request` (388:393)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L395-L400" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:resend_request` (395:400)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L402-L407" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:cancel_request` (402:407)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L411-L414" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_reports` (411:414)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L416-L419" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_report` (416:419)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L421-L426" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:create_report` (421:426)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L430-L433" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_buys` (430:433)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L435-L438" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_buy` (435:438)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L440-L448" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:buy` (440:448)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L450-L454" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:commit_buy` (450:454)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L458-L461" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_sells` (458:461)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L463-L467" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_sell` (463:467)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L469-L477" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:sell` (469:477)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L479-L483" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:commit_sell` (479:483)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L487-L490" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_deposits` (487:490)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L492-L496" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_deposit` (492:496)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L498-L504" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:deposit` (498:504)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L506-L511" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:commit_deposit` (506:511)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L515-L518" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_withdrawals` (515:518)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L520-L524" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_withdrawal` (520:524)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L526-L532" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:withdraw` (526:532)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L534-L539" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:commit_withdrawal` (534:539)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L543-L546" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_payment_methods` (543:546)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L548-L551" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_payment_method` (548:551)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L555-L558" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_merchant` (555:558)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L562-L565" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_orders` (562:565)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L567-L570" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_order` (567:570)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L572-L578" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:create_order` (572:578)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L580-L586" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:refund_order` (580:586)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L590-L593" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_checkouts` (590:593)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L595-L598" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_checkout` (595:598)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L600-L606" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:create_checkout` (600:606)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L608-L611" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:get_checkout_orders` (608:611)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L613-L616" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client:create_checkout_order` (613:616)</a>


### HTTP Request Handler
This component encapsulates the core logic for making HTTP requests to the Coinbase API. It handles URI construction, sends data, manages HTTP verbs (GET, POST, PUT, DELETE), and performs initial response validation, including error handling and pagination for GET requests.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L103-L119" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._request` (103:119)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L121-L129" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._handle_response` (121:129)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L99-L101" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._create_api_uri` (99:101)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L131-L167" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._get` (131:167)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L169-L170" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._post` (169:170)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L172-L173" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._put` (172:173)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L175-L176" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._delete` (175:176)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L87-L97" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._build_session` (87:97)</a>


### API Response Parser
This component is responsible for parsing the raw JSON responses received from the Coinbase API. It transforms the raw data into structured Python objects, handles pagination information, and processes any API-specific warnings, ensuring the data is readily usable by the application.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L178-L203" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.Client._make_api_object` (178:203)</a>


### Authentication Module
This component provides the necessary classes and logic for authenticating requests to the Coinbase API. It supports both HMAC-based authentication for API key/secret pairs and OAuth2 for token-based authorization, ensuring secure communication with the API.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/auth.py#L15-L38" target="_blank" rel="noopener noreferrer">`coinbase.wallet.auth.HMACAuth` (15:38)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/auth.py#L41-L52" target="_blank" rel="noopener noreferrer">`coinbase.wallet.auth.OAuth2Auth` (41:52)</a>


### API Data Models
This component defines the Python classes that represent the various data entities (e.g., accounts, transactions, users, orders) returned by the Coinbase API. These models provide a structured and object-oriented way to access and manipulate API data within the application.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L34-L137" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.APIObject` (34:137)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L140-L281" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Account` (140:281)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L288-L289" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Address` (288:289)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L359-L360" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Buy` (359:360)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L292-L299" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Checkout` (292:299)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L379-L384" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.CurrentUser` (379:384)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L367-L368" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Deposit` (367:368)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L302-L303" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Merchant` (302:303)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L284-L285" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Notification` (284:285)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L326-L327" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.PaymentMethod` (326:327)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L319-L323" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Order` (319:323)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L363-L364" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Sell` (363:364)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L330-L344" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Transaction` (330:344)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L347-L348" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Report` (347:348)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L375-L376" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.User` (375:376)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L371-L372" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Withdrawal` (371:372)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L13-L31" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.new_api_object` (13:31)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L351-L356" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Transfer` (351:356)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/model.py#L306-L316" target="_blank" rel="noopener noreferrer">`coinbase.wallet.model.Money` (306:316)</a>


### OAuth Client
This component provides a specialized client for interacting with the Coinbase API using OAuth2 authentication. It extends the base client functionality to include methods for managing OAuth tokens, such as revocation and refreshing, catering to applications that use OAuth for authorization.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L635-L676" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.OAuthClient` (635:676)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L653-L656" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.OAuthClient.revoke` (653:656)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/client.py#L658-L676" target="_blank" rel="noopener noreferrer">`coinbase.wallet.client.OAuthClient.refresh` (658:676)</a>


### Error Handling
This component defines custom exception classes for various API errors returned by the Coinbase API, providing a structured way to handle different error scenarios.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L10-L14" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.CoinbaseError` (10:14)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L17-L29" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.APIError` (17:29)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L52-L53" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.AuthenticationError` (52:53)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L44-L45" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.InvalidRequestError` (44:45)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L36-L37" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.ParamRequiredError` (36:37)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L40-L41" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.ValidationError` (40:41)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L76-L77" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.NotFoundError` (76:77)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L80-L81" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.RateLimitExceededError` (80:81)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L32-L33" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.TwoFactorRequiredError` (32:33)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L56-L57" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.UnverifiedEmailError` (56:57)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L48-L49" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.PersonalDetailsRequiredError` (48:49)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L68-L69" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.ExpiredTokenError` (68:69)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L60-L61" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.InvalidTokenError` (60:61)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L64-L65" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.RevokedTokenError` (64:65)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L72-L73" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.InvalidScopeError` (72:73)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L84-L85" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.InternalServerError` (84:85)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L88-L89" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.BadGatewayError` (88:89)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L92-L93" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.ServiceUnavailableError` (92:93)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/error.py#L96-L118" target="_blank" rel="noopener noreferrer">`coinbase.wallet.error.build_api_error` (96:118)</a>


### Utility Functions
This component provides various utility functions used across the library, such as URI security checks, parameter encoding, and compatibility functions.


**Related Classes/Methods**:

- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/util.py#L37-L46" target="_blank" rel="noopener noreferrer">`coinbase.wallet.util.check_uri_security` (37:46)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/util.py#L31-L34" target="_blank" rel="noopener noreferrer">`coinbase.wallet.util.encode_params` (31:34)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/compat.py#L10-L10" target="_blank" rel="noopener noreferrer">`coinbase.wallet.compat.imap` (10:10)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/compat.py#L13-L13" target="_blank" rel="noopener noreferrer">`coinbase.wallet.compat.quote` (13:13)</a>
- <a href="https://github.com/coinbase/coinbase-python/blob/master/coinbase/wallet/compat.py#L16-L16" target="_blank" rel="noopener noreferrer">`coinbase.wallet.compat.urljoin` (16:16)</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)