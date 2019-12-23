**User Interface**

You may log in SmartCMP through multiple interfaces for operation and management. The following describes the purpose, access methods, and required permissions of the different SmartCMP interfaces.

 #  Admin manage & control interface

Purpose:
 + Add, edit and delete tenants in tenant center
 + License management: add, update, delete licenses
 + Add, edit and delete FAQs
 + Customize tenant’s display interface (including Logo and theme color)


Access method:
1. Open browser and enter: http://(SmartCMP-IPaddress)/#/login?tenant=admin
2. Log in

Required credentials: 
You must be logged in using the system administrator sysadmin.

  #   Default tenant usage & management interface 

After installation, SmartCMP will create a default tenant user account for you.
 
Purpose:
 + Connect and manage cloud platform resources
 + Manage and configure organizational structure
 + Manage and configure organizational structure
 + Request and use cloud resource

Access method:
1. Open browser and enter: http://(SmartCMP-IPaddress)
2. Log in


Required credentials: 
You may be logged in using the system administrator, default tenant user (admin, bgadmin or user) or other users you created under this tenant. Users associated with different roles have different management configurations and usage entitlement. 


# Other tenant usage & management interface

You may create other tenants using Admin management & control interface. Tenant provides isolation of resource usage and management configuration.

Purpose:
 + Connect and manage cloud platform resources
 + Manage and configure organizational structure
 + Create and publish service
 + Request and use cloud resource

Access method:
1. Open browser and enter: http://(SmartCMP-IPaddress)
2. Log in

Required credentials:
You may be logged in using the default tenant user or other users you created under this tenant. System will automatically determine the tenant to which the user belongs and log in. If you want to log in using the system administrator sysadmin, please indicate the name of the tenant in the access address:http://(SmartCMP-IPaddress)/#/login?tenant=（tenantID）

For example:
When you create a tenant DemoTenant in the Admin configuration management interface, the system will create a Default business group and three users for you by default:
+ DemoTenant_admin，Tenant Admin
+ DemoTenant_bgadmin，Default BG Admin
+ DemoTenant_user，Default BG member

When you log in as the system administrator, the access address is: http://(SmartCMP-IPaddress)/#/login?tenant=demotenant


