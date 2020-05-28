**Fund Management**
SmartCMP docks with payment gateways, supports the creation of fund accounts to create user-specific wallets, provides pre-paid and post-paid cloud resource purchase methods and supports multiple payment channels for configuration use and recharge of fund accounts. The recharge amount will be automatically deducted when a subscription is deployed or renewed, and can be used for automatic deduction of pay-as-you-go bills.

+ Main functions:
    + Fund account: that is, user wallet. SmartCMP can open the wallet function for each user so that the administrator can create an account, specify the account owner, and the owner can recharge the account with the corresponding amount.
    + Payment channel: the tenant administrator can configure the payment method which currently supports PayFort.
    + Recharge: When the user purchases paid resources and the account balance is insufficient, the account owner can clics the recharge button, enter the recharge amount, select Payfort, redirect to the payment gateway page, enter the credit card information and recharges the account. After payment is completed, user will be redirected to the pre-configured SmartCMP management interface.
    + Request and use resources: There are two payment methods: pre-paid and post-paid. Pre-paid means that users need to pay first when requesting resources. Post-pay means to use resources first, and then periodically synchronize the cost list docking with the operation support system, and users pay bills Offline.
    + The owner and tenant administrator of the fund account can view the transaction records, that is, the details of the transactions (including the details of recharge and deduction) which also support multi-dimensional filtering.

The following describes the specific configuration steps:

# Accounts
Tenant administrators can create one or more accounts, each of which can be linked to one or more business groups. Each fund account can specify an owner, and the owner can view the details of this account, including (account name, ID , associated business group and owner, creation time and account balance). When the account balance is insufficient, cloud resource request and change operations are affected, owner can recharge the account.

+ Tenant administrators can add fund accounts according to the following steps:

    + Select "Fund"-"Accounts" in the left navigation bar and click "Add"
    + Fill in the name, description, select the associated business group, owner and type.
    + Click Save and the system prompts that the fund account has been successfully saved.

+ Tenant administrators can edit and delete fund accounts according to the following steps:

    + Click "Fund"-"Accounts" in the left navigation bar, select a fund account, click the "Edit" button, enter the content to be modified, and click "Save".
    + Click "Fund"-"Accounts" in the left navigation bar, select a fund account, and click the "Delete" button.

# Payment Channel
SmartCMP supports PayFort as a recharge method.

+ Tenant administrators can add payment channels according to the following steps:
    + Select "Fund"-"Payment Channel" in the left navigation bar, and click "Add" to select a payment method (PayFort).
    + Fill in the name, description, and enter the fields that need to be filled in to connect to the PayFort payment gateway, including: PayFort address, Access Code, Merchant ID, SHA type, SHA Request Phrase, SHA Response Phrase, Return URL (after recharging through the specified payment channel , Jump back to the address of the SmartCMP management interface).
    + Click Save, the system prompts that the payment channel has been successfully saved.

+ Tenant administrators can edit and delete payment channels according to the following steps:

    + Select "Fund"-"Payment Channel" in the left navigation bar, select a payment channel, click the "Edit" button, enter the content to be modified, and click "Save".
    + Select "Fund"-"Payment Channel" in the left navigation bar, select a payment channel, and click the "Delete" button to prompt the successful deletion of the payment channel.

# Recharge

+ The owner of the fund account can recharge the account that he owns. If the user has multiple accounts, he can drop down to select a single account when recharging.

+ When the user purchases paid resources and the account balance is insufficient, the account owner can clics the recharge button, enter the recharge amount, select Payfort, redirect to the payment gateway page, enter the credit card information and recharges the account. After payment is completed, user will be redirected to the pre-configured SmartCMP management interface.

+ Fund account owner or authorized user can recharge the account according to the following steps:

    + Select "Fund"-"Recharge" in the left navigation bar.
    + Choose fund account. If the user owns multiple accounts, click the drop-down list to select the account that needs to be recharged.
    + Enter the recharge amount, select Payfort, redirect to the payment gateway page, enter the credit card information and recharges the account. After payment is completed, user will be redirected to the pre-configured management interface.

+ Recharge amount: The recharge amount will be automatically deducted when a subscription is deployed or renewed, and can be used for automatic deduction of pay-as-you-go bills.

+ Perform payment operations when requesting resources: If the business group associated with the account is a prepaid type, and the account balance is recharged. Then members of the business group fill in the parameters when requesting paid resources in the service catalog and click submit and the page prompts the user to complete the payment first. User clicks Confirm to jump to the payment page, select the PayFort payment method, complete the information input on the payment page, and after the payment is successful, redirect to the interface configured in advance (for example: the deployment list page ). User can check the deployment details. If payment fails, return to the service catalog request page, user can choose to reapply.

+ After the successful deployment of cloud resources, operations can be performed. For example, in pay-as-you-go mode, the upgrade of the instance can be performed, and in subscription mode, the renewal of the instance will result in a corresponding fee deduction.

# Transactions

Fund account owners and administrators can view the account transaction details on this page.
In the left navigation bar, select "Funds"-"Transactions". This page displays the transaction records of the fund account in detail, including: transaction number, transaction time, transaction type, payment channel and transaction amount. Users can filter and view specific transaction records according to the type of income and expenditure or start and end time.