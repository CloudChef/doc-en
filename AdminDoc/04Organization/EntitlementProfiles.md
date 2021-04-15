


**Entitlement Profiles**


Users can create and manage entitlement profiles on the entitlement profile page, define the operations users can perform on service deployments and cloud resources, and specify the approval process. Entitlement profiles can be applied to different business groups.

The deployment's entitlement stipulates the operations that can be performed after the service is successfully deployed and the approval process for the operation. Go to the "Deployment"-"Instances" page, enter the instance details page, and perform corresponding operations on the virtual machine.

Cloud resource entitlement stipulates the operations that can be performed on the cloud resource and the approval process for the operation. In the "Deployment"-"My Deployments" page, select a service deployment and the top of the list page will display the operations that can be performed by the service deployment. There are two methods for setting cloud resource entitlement. The first is to set in the entitlement profile; the second is to set in the service configuration. The cloud resource entitlement in the service configuration will inherit the business group configuration, and the enabling and disabling functions and approval process can be changed within this range. Operations that are not enabled in the business group cannot be enabled at the service configuration. The following describes the method of adding cloud resource entitlement at the business group level.

## Add Entitlement Profiles

Users can add entitlement profiles according to the following steps:

1.  Select "Organization"-"Entitlement Profiles" in the left navigation bar, and click "Add".

2.  On the "Overview" tab, fill in the name and description and check whether to allow sharing.

3.  On the "Deployment's entitlement" tab, click "Add", fill in the operation name and role, select the enabled / disabled status of the operation authorization, the enabled approval process (optional), and whether to enable two-factor authentication for Day2 operations.
    
    + Check an operation in the "Operation" list, such as changing the owner, starting service deployment, stopping service deployment, etc. In the "Roles" list, select the role that can perform this operation. In "Status", you can check enable (can perform this virtual machine operation) or disable (cannot perform this virtual machine operation) and enable or disable two-factor authentication. 

    + In "Approval process", user can choose the default template (business group administrator approval process or tenant administrator approval process).

4.  On the "Cloud Resource's entitlement" tab, click "Add" and select the cloud platform type, component, operation, role, enable / disable status of the operation authorization, enabled approval process (optional) through the drop-down list, and whether to enable two-factor authentication for Day2 operations.

    + Check an operation in the "Operation" list, such as enable, stop, suspend, etc. Select the role that can perform this operation in "Role", and check Enable (can perform the virtual machine operation) or Disable (cannot perform the virtual machine operation) in "Status" and enable or disable two-factor authentication. 

    + In "Approval process", user can choose the default template (business group administrator approval process or tenant administrator approval process).


5.  You can modify or delete each added configuration, or continue to add new entitlement.

6.  Click "Save" and return to the entitlement profiles page.

>「Note」 To enable two-factor authentication, you need to dock the authentication information system first, please refer to the specific configuration steps in [Security](http://CMP-PUBLIC-IP/help/AdminDoc/09Settings.html#Security)

## Edit and Delete Entitlement Profiles

Click "Organization"-"Entitlement Profiles" in the left navigation bar, select an entitlement profile, click the "Edit" button, enter the content to be modified, and click "OK".

In the left navigation bar, click "Organization"-"Entitlement Profiles", select an entitlement profile, and click the "Delete" button to prompt the successful deletion of the entitlement profile.




# Global Configuration of Profile Templates

The default entitlement profile template of the business group can be configured in the system configuration.

Click "Settings"-"System " in the left navigation bar, and click the "Business Groups" tab to configure the default entitlement profile template for all business groups, and check whether to add users to the parent business group when joining the sub-business group.

The default configuration can be empty. If the default template is configured, each business group no longer needs to be configured separately.



# Configure Entitlement Profiles for Business Groups Individually

Business groups can be configured entitlement profile separately. Once configured, the default template configuration will be overwritten.

In the left navigation bar, click "Organization"-"Business Groups", select a business group, in the entitlement profile tab, you can select the template to be configured through the drop-down list. Click "Save".
