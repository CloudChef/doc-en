**Service Catalog**

After the service configuration is successfully published, you will see the services published by the business group and the services shared to all business groups in the service catalog interface. You can apply for a guided request in the service catalog or a published service. You can quickly locate the service you need to apply through a service group, business group, or search box.

# Self-selection blueprint for service request

1. Go to the "Services Catalog" and click "Apply" on the card for applying for cloud resources. Specify a blueprint and click "Next".

2. On the "Basic Information" page, fill in：
 + Business group: Deploy the business group to which it belongs
 + Service deployment name: Deployment name (if the service group has set the service deployment naming rules, the service deployment name will be automatically generated according to the rules, no need to fill in)
 + Project: Deployment project
 + Owner: Deployment owner
 
3. Fill in the relevant request parameters, such as: resource bundle, private network, virtual machine configuration, storage size, number of nodes, and so on. Click "Save", click "Submit" after confirming that it is correct, and wait for the deployment to complete.


# Service Catalog Request{#Service Catalog Request}

Users can apply for configured services or shared services published by the business group in the service catalog.

1. Click “Service Catalog” in the left navigation bar, select a service, and click to enter the service application page.

2. The details of the service are displayed at the top of the service request page:

 +  Description	Description of the service
 +  Basic information	Service lease time and retention time configured by service configuration/business group configuration
 +  Topology	Topology diagram used by the service

3.  ③	Fill in the relevant request parameters below the service request page:
Organization information
 +  Business group	If the service is a full business group, that is, a shared service, you need to select a business group (this business group needs to have a related resource bundle, otherwise it will not be allowed to apply); if the service has been assigned a business group, the business group does not need to be filled out.
 +  Project	If the project is divided under the business group, you can select the project.
 +  Owner	Select the owner of the service, the owner must be a member of the business group

Deployment information
 + Name	If the service deployment name naming rule is configured for the business group, the service deployment name does not need to be filled in. The service deployment name is automatically generated according to the business group rules. 
 + If the business group name is not configured in the business group, you need to manually fill in the service.
 + Quantity	Fill in the number of deployments, the default is 1
 + Execution time	Can start service deployment at a specified time, accurate to the minute
 + Key-value label	Checked by default, all server nodes use the same key-value label.
 + If not checked, all server nodes under the service deployment will be listed, and key value labels can be set separately for each server node.

Other information
 + Parameters for form	If you customize the relevant fields for the cloud resource blueprint service and the manual single service in the form configuration of the service configuration, fill in the required information here

Request Parameters
 + Request Parameters	If during service configuration, only "Allow modification" is selected (“Modify only when approved” is not checked), the application parameter field will appear. You can configure the relevant Server and Network parameters as required. 
 + Software Configuration	If the “Add Software during request” is selected during service configuration, the software configuration bar will appear. You can add software to the computing node/software component of the service and click “Add Software”.
     Select the software to be installed and all software components will be listed
     Select relationship: “Install to” or “Depend on”
     Select the node to install to or depend on



4. After completing the request, click “Apply” to directly deploy or wait for approval according to the business group process control. You can view the deployment status in “Deployments” - “My Deployments” (you can also view the deployment in the operation history in the upper right corner) or go to "Requests" - "My Requests" to view the approval process.

5. When you apply for the service, if you cannot fill in the relevant parameters at one time, click “Save” to save the filled parameters, and at the next application, click “Load” to reload which will automatically fill the last filled in parameters. 

6. When you apply for a service, the platform can display the cost of this application (on a monthly basis).

 +  For the private cloud, after the administrator configures the accounting rules of the private cloud in the “Billing & Usage”-“Billing Rules”, the user directly uses the charging API to perform charging when applying for the service.

 +  The public cloud needs to cache the public cloud's unit price API structure and then calculate the cost.

