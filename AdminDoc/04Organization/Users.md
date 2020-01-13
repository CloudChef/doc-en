**Users**

In the left navigation, select "Organization" - "Users". This page displays all users under the current tenant, and displays the user login name, username, user e-mail address, login method, business group, organizational unit, user status, creation time, and time and so on. Users can add, edit, reset passwords and delete operations. May locate user quickly by search.

# Add Users

1.  In the left navigation, select "Organization" - "Users", click "Add", select the login type: Local / According to the system configuration, enter the Create User Basic Information interface (if the system is configured with LDAP login mode, it will also be optional)

2.  Basic Information: Enter the required fields such as username, login name, email address and password, mobile phone number, QQ number, contact name, expiration time (automatically disable when the specified expiration time reaches), etc. 

3.  Roles: The default user is a tenant member. The system has software architect, infrastructure administrator, tenant administrator and other roles by default. You can also customize the role and assign corresponding permissions to the role. For details, refer to Roles. When a role is selected, the entity object and scope of the role corresponding to the role are displayed. 

4.  Associated Business Group page: Select the business group and associate the business group with the user. For details, see [Add Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html)

5.  Click “Save” and the user is created successfully.

# Edit Users

In the left navigation bar, click "Organization" - "Users", select a user, click the "Edit" button, enter the content to be modified, and click "Save".

## Reset Password

Click "Organization" - "Users" in the left navigation bar, select a user, click the "Reset Password" button, enter the new password, confirm the password, and click "Submit". A new password is required when the user logs in again.

# Delete Users

In the left navigation bar, click "Organization" - "Users", select a user, click the "Delete" button, and the delete prompt box will pop up, click "Yes" to prompt the deletion of the user success.

# Disable/Enable Users 

In the left navigation bar, click "Organization" - "Users", select a user, click the "Disable" button, pop-up prompt box and click "Yes" to prompt the user to disable.

After the user is disabled, he/she cannot log in to the system. When logging in to the system, it shows the user is disabled on the login page.

After the user is disabled, it can be enabled. In the left navigation bar, click "Organization" - "Users", select a disabled user, click the "Enable" button, and enable it to log in again.

# Import AD Users

Click "Organization" - "Users" in the left navigation bar, click "Add", and the Select LDAP User page appears.

On the left side, you can select the OU. On the right side, you can choose to add the users to the corresponding business group in batches. Click “Import” to add the LDAP user to complete. You can also filter by keyword.

>「Note」Supports automatic synchronization of AD accounts



#  LDAP Login Type {#LDAP Login Type .afff6}

1.  Go to the menu "Settings" - "System ". In the system configuration, the user can configure the login type of the current tenant. The login types that current system supports are: Local login, LDAP/Microsoft Active Directory

 + Select local login, SmartCMP will use the local database to authenticate the logged in user

 + Select LDAP/Microsoft Active Directory, SmartCMP will authenticate the logged in user using OpenLDAP or Microsoft AD

2.  If you select LDAP/Microsoft Active Directory, the LDAP configuration interface will appear.

 + Directory Server Address: Host address of OpenLDAP or Microsoft AD (multiple domain control addresses can be entered, separated by commas)

 + Directory Service Port: For OpenLDAP, use port 389; if it is Microsoft AD, use port 3268

 + Domain Name: Please enter the domain name using the syntax of LDAP. For example, if your domain name is “cloudchef.io”, the domain name here should be “dc=cloudchef, dc=io”

 + Administrator username: Please use the “Account@Domain” method, for example: administrator@cloudchef.io

 + Administrator password: Please enter your administrator password

 + Directory Search Properties: This is customized for your LDAP based server. We provide default search properties.

3.   For Microsoft AD, we use sAMAccountName and userPrincipalName to search for your account information by default.

4.   For OpenLDAP, we use cn or uid to search for your account information by default. If your server has additional configuration, enter the search attribute you use here.

5.   If "Allow local login at the same time" is checked, local users and LDAP users can log in at the same time.


