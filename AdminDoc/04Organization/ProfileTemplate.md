


**Profile Template**

Business groups can configure entitlement profiles and naming policies. Entitlement profiles: define operation permission for service deployment and cloud resources; Naming policies: define naming rules for instances and cloud resources.

The advantages of configuration templates: optimized the configuration of entitlements. The original deployment and cloud resource entitlements need to be configured on the business group and service configuration. After configuring the template, one-time configuration can be repeatedly applied to different business groups.

In the system configuration, two default templates can be selected for the business group configuration: the business group default entitlement profile and the business group default naming policy. After configuration, all business groups use such templates by default.

# Entitlement Profiles

Users can create and manage entitlement profiles on the entitlement profile page, define the operations users can perform on service deployments and cloud resources, and specify the approval process. Entitlement profiles can be applied to different business groups.

The deployment's entitlement stipulates the operations that can be performed after the service is successfully deployed and the approval process for the operation. Go to the "Deployment"-"Instances" page, enter the instance details page, and perform corresponding operations on the virtual machine.

Cloud resource entitlement stipulates the operations that can be performed on the cloud resource and the approval process for the operation. In the "Deployment"-"My Deployments" page, select a service deployment and the top of the list page will display the operations that can be performed by the service deployment. There are two methods for setting cloud resource entitlement. The first is to set in the entitlement profile; the second is to set in the service configuration. The cloud resource entitlement in the service configuration will inherit the business group configuration, and the enabling and disabling functions and approval process can be changed within this range. Operations that are not enabled in the business group cannot be enabled at the service configuration. The following describes the method of adding cloud resource entitlement at the business group level.

## Add Entitlement Profiles

Users can add entitlement profiles according to the following steps:

1.  Select "Organization"-"Entitlement Profiles" in the left navigation bar, and click "Add".

2.  On the "Overview" tab, fill in the name and description and check whether to allow sharing.

3.  On the "Deployment's entitlement" tab, click "Add", fill in the operation name and role, and select the enabled / disabled status of the operation authorization and the enabled approval process (optional).
    
    + Check an operation in the "Operation" list, such as changing the owner, starting service deployment, stopping service deployment, etc. In the "Roles" list, select the role that can perform this operation. In "Status", you can check enable (can perform this virtual machine operation) or disable (cannot perform this virtual machine operation).

    + In "Approval process", user can choose the default template (business group administrator approval process or tenant administrator approval process).

4.  On the "Cloud Resource's entitlement" tab, click "Add" and select the cloud platform type, component, operation, role, enable / disable status of the operation authorization, and enabled approval process (optional) through the drop-down list.

    + Check an operation in the "Operation" list, such as enable, stop, suspend, etc. Select the role that can perform this operation in "Role", and check Enable (can perform the virtual machine operation) or Disable (cannot perform the virtual machine operation) in "Status".

    + In "Approval process", user can choose the default template (business group administrator approval process or tenant administrator approval process).


5.  You can modify or delete each added configuration, or continue to add new entitlement.

6.  Click "Save" and return to the entitlement profiles page.


## Edit and Delete Entitlement Profiles

Click "Organization"-"Entitlement Profiles" in the left navigation bar, select an entitlement profile, click the "Edit" button, enter the content to be modified, and click "OK".

In the left navigation bar, click "Organization"-"Entitlement Profiles", select an entitlement profile, and click the "Delete" button to prompt the successful deletion of the entitlement profile.


# Naming Policies

Users can create and manage naming policies on the naming policies page to define the names of service deployment, instances, and cloud resources. The naming policies can be applied to different business groups.

##  Add Naming Policies

Users can add naming policies according to the following steps:

1.  Select "Organization"-"Naming Policies" in the left navigation bar, and click "Add".

2.  Enter the name and description in the basic information and check whether to allow sharing.

3.  Under the naming policies tab, you can define naming policies for service deployment names, instance names, Windows host names, Linux host names, and public network IP names. During configuration, you can select the default field provided by the system or enter a custom string. The naming policies are as follows:

    + Service deployment naming policies: You can set the business group service deployment naming policies. When a service group member applies for a service, the service deployment name is automatically generated according to the policies. Existing fields: business group name, project name, owner name, timestamp (yyyyMMddHHmmss), service configuration name, project abbreviation, business group abbreviation.

    + Instance naming policies: The virtual machine display name in the SmartCMP or vCenter/OpenStack management interface. Existing fields: IP address, service group name, project name, owner name, deployment name, virtual machine blueprint node name, OS host name, project abbreviation, business group abbreviation.

    + Windows hostname naming policies: Windows virtual machine hostname. Existing fields: business group name, project name, owner name, deployment name, virtual machine blueprint node name, project abbreviation, business group abbreviation.

    + Linux hostname naming policies: Linux virtual machine hostname. Existing fields: business group name, project name, owner name, deployment name, virtual machine blueprint node name, project abbreviation, business group abbreviation.

    >「Note」Virtual machine hostname does not support special symbols, otherwise deploying virtual machine may fail. Windows host naming policies generated by the Windows host name more than 15 characters will automatically intercept the field (15-suffix length). There are suffixes in the naming policies, you can choose the "naming suffix" that is already in the "infrastructure".

    + Public network IP naming policies: business group name, project name, owner name, project short name, business group short name, instance name.

4.  Click "Save".

## Edit and Delete Naming Policies

In the left navigation bar, click "Organization"-"Naming Policies", select a naming policy, click the "Edit" button, enter the content to be modified, and click "OK".

In the left navigation bar, click "Organization"-"Naming Policies", select a naming policy, and click the "Delete" button, which prompts the successful deletion of the naming policy.


# Global Configuration of Profile Templates

The default entitlement profile template and naming policy template of the business group can be configured in the system configuration.

Click "Settings"-"System " in the left navigation bar, and click the "Business Groups" tab to configure the default entitlement profile template and naming policy template for all business groups, and check whether to add users to the parent business group when joining the sub-business group.

The default configuration can be empty. If the default template is configured, each business group no longer needs to be configured separately.



# Configure Entitlement Profiles for Business Groups Individually

Business groups can be configured entitlement profile and naming policy separately. Once configured, the default template configuration will be overwritten.

In the left navigation bar, click "Organization"-"Business Groups", select a business group, in the entitlement profile tab, you can select the template to be configured through the drop-down list. Click "Save".
