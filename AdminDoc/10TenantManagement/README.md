
**Tenant Management**

# Overview


SmartCMP supports the multi-tenant hybrid cloud billing management mode. In the tenant center page of the tenant management, the system administrator can manage the tenant.

+ Log into system through URL http://server-address/#/login?tenant=admin, and click on "Tenant Center" - "Tenant" in the menu.

- Add tenant: Click “Tenant Center” - “Tenant” in the menu, click “Add” button on the tenant page, input ID and name of the tenant in “Basic Information”, set the logo image and theme color of the tenant, click “save”

- Edit tenant: Click “Tenant Center” - “Tenant” in the menu, select a tenant on the tenant page, click “Edit” button, enter the tenant information to be modified; when editing the tenant, set the theme color for the tenant, you can choose the default 3 themes or customize, click "Save" after "OK"

- Delete tenant: Click “Tenant Center” - “Tenant” in the menu, select a tenant on the tenant page, click the “Delete” button, click “Yes” to prompt the tenant to delete successfully.

>「Note」Admin tenant cannot be deleted.

# License Management


Log in to the system management as tenant and click on "System Management" - "License Management" in the menu. The License Management page displays the total number of instances and the number of instances used, as well as the total number of authorized physical CPUs and the number of physical CPUs used.

 Release license for product license control software, including the following:

  + Registration name: system license owner
  + License Type: Controls the functional attributes of the software, such as which system components are included, which cloud platform management is supported, etc.
  + Version: System version
  + Valid until: Software usage time limit. After expired, if want to continue, it needs to be updated
  + Number of authorized instances: Use this system to create virtual machine caps. Exceeding the upper limit will not allow deployment of new virtual machines
  + Number of authorized physical CPUs (number): Use this system to create a virtual physical CPU upper limit. If this item is set, the number of authorized instances is considered to be unlimited. In a hybrid cloud environment, if it is purchased according to the CPU, the virtual machine on the public cloud is calculated according to 15 virtual machines equal to 1 physical CPU. Exceeding the upper limit will not allow deployment of new virtual machines.
  + Status: Shows the status of the license: valid and expired

1. Click the Add button to enter the license add page, enter the license, click "Add"

2. Select a license, click Update, enter the update license interface, enter a new license, click "Update" to update the license

3. Select a license and click “Delete” to delete the license. When the system expires within 15 days, the user will see a message at the top of the page.
   A combination of multiple licenses is currently supported.

