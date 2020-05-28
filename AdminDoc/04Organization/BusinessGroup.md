**Business Group**


# Create Business Group

1.  On the left navigation, select “Organization” - “Business Group” and click “Add”.

2.  Enter the name of the business group, select the upper-level business group, enter the description of the business group, click Submit, the business group is added successfully, and go to the edit business group page.

+ Overview:

Business group primary color: Select a color as the primary color of the business group, and the service published by the business group will display the set primary color in the service catalog. If not set, it will be randomly selected by the system.

Service deployment lease time range: Set the service deployment lease time range: minimum and maximum values. Leave blank for no limits. The instance will be automatically shut down after the service lease expires. 

Service deployment retention time range: Set the service deployment retention time range: minimum and maximum values. Leave blank for no limits. After the service deployment retention time expires, the instance will be deleted and the resources will be released.

>「Note」The service deployment lease/retention time range set here will limit the range of leases that the user can select when configuring the service and applying for the service.

Maximum number of extensions: Number of extensions the user allowed to make

Allow start after service expires: Check to allow users to start the service and continue trials before extending the lease after the service deployment expires

Virtual machine CPU, memory (GB) maximum

Enable wizard-based requests to quickly apply for services



+ User:

Associated users: Click on “Associated Users”, select the users in the list, and click “OK” to associate the users to the business group. After the association is successful, the associated user will be displayed on the user page and clicking the login name will jump to the user interface. 

Remove user: If there is already a user in the business group, select a user in the list and click “Remove User” to cancel the association between the user and the business group. The user will not be able to view and use the resources of the business group.

Associated role: Select a user in the list interface, click on “Associate Role”, check “Business Group Administrator”, and click “Submit” to give the user the role of the business group administrator.

+ Rule:

Naming Policies: Configure the naming policies for service deployment, instances, and cloud resources. Click the drop-down list to select the added naming policies. Leave blank to use the default template in system settings.

Specification: The configuration specification of business group requesting resources in the service catalog and requesting the maximum CPU and memory of instance, leaving blank to indicate no limit.



+ Entitlement Profiles
The "Entitlement Profiles" tab can be configured with an entitlement profile that specifies the operations that users can perform on service deployment and cloud resources.

Click the drop-down list to select the added entitlement profiles. Leave blank to use the default template in the system settings. Once configured, the default template configuration will be overwritten.



+ Resource Quota

Business group resource quota meets the needs of controlling department-level resource quotas. The budget quota of the business group is independent of the resource quota of the resource bundle. When the budget of the business group reaches the threshold and there is a large amount of resource quota remaining in the resource bundle, business group members cannot request new resources in the service catalog. Note: The resource quota can be configured with a larger amount than the business group budget. Specifically, the following resources can be set: CPU, memory, storage, and number of virtual machines. Note: First, you must enable "Enable resource quota". 

- Disabled by default: The resource quota interface prohibits input and does not calculate the amount of resources used

- Enabled: The above resources can set quotas. They are all non-required items. Only integers greater than or equal to zero can be entered. Leave blank to indicate no limit. Supports viewing of used quotas. (If a certain quota is unlimited, then the remaining is always unlimited. The usage rate is always 0%.) When new service deployment occupies resources, operations modify the configuration, or the resource usage or the business group gets changed, the corresponding resource usage will change. 

>「Note」If the business group has not enabled quotas, but the business group has resources occupied, after the quota is enabled, the business group needs to be able to display the resources that have been used. Quotas for child business groups are temporarily independent, that is, they are not restricted by the parent business group and can be configured separately.



+ Budget Quota 

The administrator can configure a monthly budget for this business group, leaving it blank for unlimited.

>「Note」Personal budget cannot be greater than the total budget of the business group.

When the spending of this month exceeds the budget, users will not be able to request new cloud resources, and paid instances belonging to users will be shut down. Supports control of resources and resource requests based on configured policies. You can view the real-time usage rate, resource usage, and remaining amount of cloud resources of the business group on this page. Specific steps:

- Select year or month as the time unit. Select monthly to indicate that it is cleared on the 1st of each month and restore the initial value; select annual to indicate that the zero has been cleared on the beginning of the next year and restore the initial value. 

-  Business group quota management: Fill in the total budget. Set the percentage. When the overall cost of the business group exceeds the configured total budget percentage, subsequent notifications are triggered, and the system will automatically send a notification to the business group administrator. 

- User quota management: Set personal budget and percentage. When personal budget usage reaches the threshold, trigger subsequent notifications and send notifications to users.

- Budget strategy: Select "Cannot request new resources after the budget is used up". When the business group budget is used up, all users associated with the business group will not be able to request new resources that require payment. Select "Paid resources will be automatically shut down after the budget is used up". For example: Configure vSphere billing rules. Deploy vSphere instances. Configure business group billing and personal budgets. Configure "Shutdown after budgets are used up", and when personal budgets are used up, the instances belonging to the individual will be shut down, or when the business group budget is used up, those belonging to the business group will be shut down. After shutdown, reservation will be made according to the retention time of the business group and after the retention time expires, the resources will be put into the recycle bin.

>「Note」When there are multiple users with different quotas in the business group, one user owing money does not affect other users' requests for resources. The instances belonging to that user are shut down which does not affect the status of other users'.

- Personal budget renewal: Submit the renewal ticket. The administrator can modify the quota for each user on the "User" tab. Specific operation steps: Select "User"-"Budget Configuration" and modify the user's personal budget.


Click Save to view the current business group.




# View Current Business Group

Choose Organization - Business Groups to view all current business groups. Displays the name of the business group, the upper-level business group, the creator, and the creation time. You can add, edit, and delete business groups.

# Modify the Business Group Configuration

Select "Organization " - "Business Groups", select a business group, click the "Edit" button, enter the content to be modified and click "Save".

## Add a Sascaded Business Group

In the UI of adding a business group, you can select a higher-level business group, so that your current business group can be added to the upper-level business group to implement a cascaded organization. (Can only add one superior business group) The cascaded business group can realize the hierarchical relationship of the organization. You can connect to any organizational structure of any company through the cascaded business group.

The cascaded business group has the following characteristics:

-   The users associated with the child business group do not necessarily have to be associated with the parent business group. The tenant administrator may check "When you add a user to a child business group, add this user to the parent business group as well." in "System"-"Business Groups", that is: when you add users into the child business group, the user will be automatically added to the parent business group
Uncheck this option, when the user does not exist in the parent business group, the child business group can also directly add the associated user, and it will not be automatically added to the parent business group

-   The parent business group administrator will automatically become the administrator of all child business groups (this rule has nothing to do with system configuration)

-   The resource bundles associated with each level of business group are independent of each other

-   The service catalogs associated with each level of business group are independent of each other

-   The deployment and virtual machines associated with each level of the business group are independent of each other

## Delete a Business Group

You can delete a business group by following the steps below: 

1.  On the left navigation, select “Organization Structure” - “Business Group”, select a business group, and click the “Delete” button.

2.  Confirm the delete operation, click "Yes" to delete the business group.

>「Important」Deleting business group will delete the script library, naming suffix, key pair, etc. under the business group and remove all users from the business group. Before deleting a business group, ensure that all service deployments under the business group have been uninstalled successfully, and all resource bundles under the business group are removed, and all released and unpublished services are deleted.
