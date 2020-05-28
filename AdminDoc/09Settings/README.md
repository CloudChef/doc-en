**Settings**


# System
In the left menu bar, select "Settings" - "System" to enter the "Overview" page:

Login Type
1. Local Log in
2. LDAP/Microsoft Active Directory: If selected, the “LDAP Configuration” tab will appear.
3. OAuth2
>「Note」Multiple login methods can be configured.
+ DNS domain (OpenStack)	   Add a DNS domain, you can add one or more (optional)
+ A domain name consists of a multi-level domain name such as root domain name, top-level domain, second-level, third-level, etc. Each domain name consists of letters, numbers, and hyphens (-) (the first character cannot be a hyphen) and is not case-sensitive and no more than 63 characters. A full domain name has a total length of no more than 255 characters and must end with a dot. After the configuration is successful, you can configure secondary and tertiary domain names in the OpenStack resource bundle.
>「Note」DNS domain name needs to be configured on the DNS server. If not, it will report an error when applying for service.



# Interface configuration

Use "System"-"Interface Configuration" to determine brand and service request information including color, 页眉页脚、菜单配色、浏览器标签、登录页面、自注册功能、主页、 about pages, and whether to display help documentation, and adjust the display of service catalogs. 

## Configure Branding

The specific steps to configure the branding: On the branding tab,

+ Choose a bright or dark color style to control the color style of the left navigation bar area.
   The theme color can be selected from solid color or gradient color. Use the color palette to select the set color. When a gradient color is selected, the highlighted menu and buttons will be displayed in a gradient color, and links and labels will be displayed in the second color.
   The text box and button style can be set to square or rounded corners.

+ You can choose whether to hide the header. When you choose not to hide, use the color palette to select the header color, text and icon color (respectively effective), upload icon and custom text content.

+ Configure colors for the menu. You can use the color palette to configure colors for menus, text, and icons, and the color settings will take effect separately.


+ You can choose whether to hide the footer. When you choose not to hide, use the color palette to select the footer color and text color (respectively effective), upload icons, and customize text content.

+ New tenant's menu, header and footer colors will not be affected by other tenants.

+ Upload browser icon and customize browser title.

+ Upload the background image of the login page, define the text on the left side of the login page, customize the text style and color, and the text supports the use of Markdown syntax format.
   Choose whether to use verification code on the login page, and set whether to enable or disable "Forgot password".

+ Choose whether to hide the user self-registration function. When choosing not to hide, click the drop-down box to select the configured form and service to define the fields and self-registration process that the user needs to fill in during self-registration.

+ Upload the homepage icon and configure the jump link of the homepage button which supports external links or relative paths within the system.

+ You can choose whether to hide the about page. When you choose not to hide, upload pictures, define the product name and copyright notice.

+ Define whether to display the help document. When you choose to hide, the question mark button in the upper right corner of the navigation bar will be hidden.


##  Configuration Catalog

Specific steps for configuring service requests: The service catalog currently supports 2 views. On the Service Request tab, 

 +	Tenant administrators can configure how groups and services are displayed in the service catalog: tab display or hierarchy display 
 
    Specific display method: 
    Tab display: group display according to the tab page. 
    Hierarchical display method, according to the card mode, first display the service group
    In the service catalog interface, you can view the service group icon, name, description and folder display mode. Click on a group to show all the cards of this service group.

 + The tenant administrator can configure the field display on the service request page. The configurable fields are: description, execution time, key-value label, business group, project, and owner.










# Notifications

## SMTP configuration

Go to the menu "Settings" - "Notifications". On the SMTP Configuration tab, you can configure the SMTP configuration that the current tenant can access.

The following information can be filled in the SMTP configuration:

Basic Information     |Description
:------------:|: ------------:
Use SSL     | Use SSL for current SMTP
SMTP server  | SMTP server address
Port        | SMTP port number
Username      | Username
Password        | Password
Sender      | Default sender 

After the configuration is complete, you can click "Verify Settings", the system will automatically send a test email to the current account's email address according to the configuration to verify whether the SMTP server is working.

## SMS Configuration

Go to the menu "Settings" - "Notifications". In the "SMS Configuration" tab, you can fill in the SMS (short message) configuration that the current tenant can access.

  Basic Information     |Description
  :---:|:---:
  Username      | Username
  Password        | Password
  SMS server |  SMS server address
  Port     |   SMS port

## Enterprise WeChat

In the menu "Settings" - "Notifications", in the "Enterprise WeChat Configuration" tab, the tenant administrator can configure the information about the current tenant enterprise WeChat.

 Basic Information     |Description
 :---:|:--: 
 Enterprise ID | View in the enterprise WeChat management background "My Business" → "Enterprise Information"
 Application ID | The unique Agent ID of each application, please view it in the enterprise WeChat management background "Applications and applets" → "Applications"
 Application Keys | Each application has a separate access key. Please view it under the “Applications and Applets”→“Applications” in the enterprise WeChat management background.

## DingTalk
Go to the menu "Settings" - "Notifications". In the "DingTalk Configuration" tab, the tenant administrator can configure the information about the current tenant’s DingTalk.

 Basic Information     |Description
 :---:|:---:
 Application ID |When the application ID is used to create an application, the system automatically generates an Agent Id, which can be used to send scenarios such as enterprise session messages.
 Application Secret |When the application is created, it is automatically generated by the system together with the application key.
 Application Key  |When the application is created, the system automatically assigns it, which is the unique identifier in the application development process.

# Menu


When you access a third-party system or an extended system (such as access to Baidu, JD, Azure bills, dashboards), the menu configuration makes the access menu more flexible.

In the menu configuration you can define a variety of dashboards, you can also access the external system, and freely choose the extended menu, the following describes the specific operation method.

## Add a Menu Configuration

In the menu configuration, users can define the access of the built-in menu, a variety of dashboards and third-party systems. The built-in menus, dashboards and extended systems will be assigned to different roles for viewing according to the defined permissions, and can be displayed flexibly.

Click "System"-"Menu", click Add, select the menu configuration type:

+   Select the access right of the built-in menu to set the role to view the menu. In the drop-down box, select the menu to be configured (Service Request, My Deployment, Report and Analysis, etc.) and the role (tenant administrator, project member, etc.) that can access this menu. Set the status of this menu configuration: enable or disable this configuration.

+   Select Metabase to access the dashboard, and select external URL to access the third-party system.
    Enter the name, description, location, URL parameters, role (select the role that can access this menu), status (choose to enable or disable this configuration) and upload the icon.

You have the flexibility to choose where to extend the menu, for example: 

Add extension menu Baidu, location selection

-  Before system management (system management is a first-level menu), Baidu is also a first-level menu in front of the system management menu.

-  Located in system management (system management is a first-level menu), Baidu is a secondary menu built into the system management menu.

-  After system management (system management is a first-level menu), Baidu is also a first-level menu behind the system management menu.

Click Submit. The menu configuration list displays all the currently added dashboards, displaying the dashboard name, description, ULR source, URL parameters, role (you can view the role of the dashboard), status, creation time, and so on.

## Edit and Delete Menu Configuration

Click "Settings" - "Menu", click Edit, and edit the extended menu information in the "Edit Menu Configuration" tab.

Click "Settings" - "Menu", click delete to delete the extended menu. 

# Report

The report configuration function provides users with more various types of reports to form an extensible report module, which supports administrators to define report functions freely and flexibly.

+ Supports custom report viewing permissions for different roles, sets the status of the report (enabled, disabled), and chooses to assign reports to a role for viewing, such as tenant members, business group administrators, software architects, and custom roles.

+ After the configuration is completed, you can view the corresponding report in Resource Analysis - Report.





