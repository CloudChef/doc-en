

**Request Service Mgmt.**

A work order is a way for users to submit multiple types of service requests and supports submitting cloud resource blueprint service work orders and manual service work orders.

The tenant administrator can customize and publish the standard work order service, and the user can process the self-service request through the service catalog and track the status of the work order through the service request.

For the specific work order service scenario, please refer to the following steps:

1. Setup Service Groups: Tenant administrators customize the associated users.

2. Define Manual Work Order Process: Platform provides the default process out of the box (standard manual work order, standard event management process), when the tenant administrator has additional requirements, he may use custom process designers to customize the methods and strategies for designing services and add them to SmartCMP through "Service Design" - "Workflow" - Process Design. 

3. Manual Work Order Service Config: The tenant administrator defines the manual work order service process and the service group role or user that processes the work order task. After the configuration is complete, it is published to the service catalog, so that users in the business group can apply for the work order in the service catalog.

4. Request and Track: After the user applies for the work order, according to the pre-configured process, the system distributes the work order to the corresponding service group role or user according to the relationship between the service group and the work order. After receiving the work order request, the designated personnel in the service group can perform the transfer or perform the offline processing. After the completion, the status of the work order is updated. The system notifies the user by email, and the user can perform the shutdown operation or request the re-processing operation.

# Set up the Service Group{#Set up the Service Group}


The service group is a collection of service personnel who process work order tasks during the work order service management process, and supports the tenant administrator to customize the associated users.

>「Note」Previous content has already introduced the service group in detail. If you need to set up a service group, please refer to [Set up Service Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/ServiceGroup.html)

# Define Work Order Service Process{#Define Work Order Service Process}


After the service group is established, the work order is created through the service configuration, and the work order is published to the service catalog to complete the release of the service card and the management of the service catalog. The following sections will detail the steps to configure the manual work order service process, configure the manual work order service, and publish the manual work order service.

### Custom Add Manual Work Order Service Process

In the left navigation bar, click "Service Design" - "Workflow", click Add, enter the name (manual work order service process), description, select category (manual work order service), upload process configuration file.

### Built-in manual work order service process

The manual work order service process built into the platform includes standard manual work orders, standard event management processes, and automated service processes.

+ Standard event management process to solve problems related to IT resources, such as: unexpected server shutdown, network interruption, etc., network IP address conflicts, and so on. The process type belongs to the manual work order service.
+ Standard manual work orders: Services that require IT manual intervention, such as manual work order services that require a password reset.
+ Automated service process: The user applies for the manual work order service. After the service is approved, the user can automatically create the resources requested, for example, create a project, create an IP pool, and so on.

>「Note」The manual work order service process built in does not support modification and deletion. It only supports viewing and use. The manual work order service process added by the user supports modification and deletion.

# Manual Work Order Service Configuration{#Manual Work Order Service Configuration}


Administrators can publish a designed work order as a service, and post the service to the service catalog after integrating it with the internal processes. The main functions of the service items are:

The service is associated with the designated service group. The service request is handled by the user associated with the team, that is, the designated service group. The release services of the work order to the different department are associated with the process configuration. The platform supports the administrator to customize the service process, and supports the use of the built-in service process. 

### Add Manual Work Order Service Configuration {#Add Manual Work Order Service Configuration .afff6}

You can add a manual request service configuration by following the steps below:

1. In the left navigation bar, select "Service Design" - "Catalog Config" and click "Add".

 Fill in the service name, service description (optional), select the business group, and when the service type is manual work order service, add a service process and click “Submit” to enter the service configuration “Basic Information” page.

 + Fill in the following information on the "Basic Information" tab: name, description, logo image, service group, order

 + Specify the approval process on the Approval Configuration page, for example, to apply for a manual work order for creating a new project. You can specify the approval process approved by the tenant administrator.
 + Specifying the service processing phase on the Process Configuration page requires assigning the appropriate person to complete the task. Specifying the service confirmation shutdown phase requires the applicant to determine whether the problem is resolved, configure the handler type and select the handler's details based on the type (for example: Select the service group in type and further selecting service group)

 + Specify the form you created on the Form Configuration page, for example, to request a manual work order to create a new project, you can choose to create a form for the project.

2. Click the Save button, the service will be saved without publishing, click the Save and Publish button, and the service will be published to the Service Catalog page.

### Edit and Delete Manual Request Service Configuration {#Edit and Delete Manual Request Service Configuration .afff6}

In the left navigation bar, click "Service Design" - "Catalog Config", select a service configuration, click the "Edit" button, enter the content to be modified, and click "Save".

In the left navigation bar, click "Service Design" - "Catalog Config", select a service configuration, and click the "Delete" button to prompt the deletion of the service configuration.

### Publish/Unpublish Manual Work Order Service Configuration {#Publish/Unpublish Manual Work Order Service Configuration .afff6}

In the left navigation bar, click "Service Design" - "Catalog Config", select a service configuration, and click the "Publish" button to prompt the release.

In the left navigation bar, click "Service Design" - "Catalog Config", select a service configuration, and click the "Unpublish" button to prompt the unpublishing service configuration. 

# Apply and Process Work Orders{#10.4	Apply and Process Work Orders} 

The full life cycle of the work order can control and record the entire process of the work order, including work order service configuration, work order request, work order processing, and real-time viewing of service progress.


After the user completes the request in the service catalog, according to the pre-configured process, the system will dispatch the work order to the corresponding service group according to the relationship between the work order and the service group.

After receiving the work order request, the designated personnel in the service group can perform the transfer or perform the offline processing. 

After the completion, the status of the work order is updated, the system automatically notifies the user, and the user is also allowed to view the processing progress.



### My request {#My request}

Select a manual work order service and click to enter the manual work order service information details page. Enter the basic information of the service: title, description, priority, urgency, the mobile phone number of the applicant's information required, click on the application to apply for the service successfully. After the service application is successful, the service request status is changed to the processing, and the request enters my request.          

Users can view the work orders that the user has applied for and track the work order processing process according to the following steps:


1. Click "Requests" - "My Requests" in the left navigation bar. My request page displays the basic information of my request: request number, request type, title, service name, business group, project, request status, request Time, completion time.

2. Select the service request of any manual work order service, click the “Request Number” link, and jump to the manual work order service request details page to view the basic information of the request, work order information, processing record, approval process, approval record and so on.

3. Approval process: approval flow chart, approval level, approver, role. Approval record: approval process information, approval process name, status, approval opinion, approver, approval role, approval time

4. Basic information includes request number, request time, request type, applicant, contact information, email address, business group, project, etc.

5. Work order information includes title, description, priority, urgency, and field information from form configuration. 

6. Process record information: process steps, descriptions, process descriptions, process status and handlers, processing time.

### All requests {#All requests}

Tenant administrators can also view service requests for all users by following these steps:

1. Click "Requests" - "All Requests" in the left navigation bar. All request pages display basic information of all requests: request number, request type, deployment name, applicant, business group, project, request status, request time, completion time, approver.

2. Request types include manual work order request, cloud resource blueprint deployment, and Day2 operation. The details page of different request type display is slightly different. For details, please refer to: My Request

3. On the Service Request List page, you can quickly locate the service request you need to view. You can approve the status (approval status of the service request: pending approval, in progress, approved, rejected, returned, error, withdrawal), business Group, start and end time (start and end time of service request) or keyword search box for quick positioning.

### Pending Requests {#Pending Requests}

The service request waiting for the service group to process is displayed here

1. In the left navigation bar, click "Request" - "Pending Requests". The pending page displays the pending part of all processing requests initiated, which displays the basic information of the processing request: request number, service name, request type, title, business group, project, request status, request time, completion time.

2. Select a pending service request, click the “Request Number” link, and jump to the request details page to view the basic information of the request, work order information, processing records, process steps, service processing information, and so on.

3. Basic information includes request number, request time, request type, applicant, contact information, email address, business group, project, etc. Work order information includes name, description, priority, urgency, and field information from form configuration. 

4. Processing records include process steps, descriptions, descriptions of processing results, status, processors, and processing time.

5. Process steps:

 + Initiating an application: The service applicant initiates a manual work order service through the service catalog, waiting for the service group to process

 + Service Processing: Need to assign the right person to complete this work order task

 + Reprocessing: The applicant judged that the problem was not resolved satisfactorily and chose to return the service to the service staff for processing.

 + Confirm Close: If the applicant determines that the problem has been satisfactorily resolved, then close the service.

6. Processing methods: direct processing and transfer processing

 + Select direct processing method, click direct processing, fill in the processing result description, you can click submit button at the bottom of the page to complete the service request, email the service applicant, the applicant can close the work order. The service request status is changed to "Processed".

 + Select the transfer processing method, click Transfer, select the service group, process personnel and transfer instructions, click the submit button at the bottom of the page to complete the service request, and the service request status is “Processing”.

### Processed {#Processed}

Here display the requests that the service group has processed and the applicant has confirmed to close.

1. Click "Requests" - "Processed" in the left navigation bar, and the page displays the processed part of all processing requests initiated.

2. Display the basic information of the processing request: request number, request type, service name, title, applicant, business group, project, request status, request time, completion time。

3. Select a request, click the “Request Number” link, and go to the My Request Details page to view the basic information of the request, work order information, and process records.
