**Service Request**

SmartCMP can manage and record the full life cycle of cloud resource services and tickets, including service configuration, request, processing, and real-time viewing of service progress. The full life cycle of the ticket can control and record the entire process of the ticket, including ticket service configuration, ticket request, ticket processing, and real-time viewing of service progress.

Users can request configured services and shared services published by the business group in the service catalog. The service types include two types: one is ticket service, and the other is cloud resource blueprint service. After the service request is completed, the service information can be viewed on the page of my request list. 

After the user completes the request in the service catalog, according to the pre-configured process, the system will dispatch the ticket to the corresponding service group according to the relationship between the ticket and the service group. Members of the service team can also actively perform node operations. After receiving the ticket request, the designated personnel in the service group can perform the transfer or perform the offline processing. 
After the completion, the status of the ticket is updated, the system automatically notifies the user, and the user is also allowed to view the processing progress.

On the pending page, the approver configured by the administrator in the approval process has the approval authority and can view the details of the service request to be approved and approve the operation.

>「Note」
 If you want to view the details of a pending service request, please refer to: [Pending Approval](#Pendingapproval)。

After the approver has completed the approval process, click on "Requests" - "Approved" on the left menu bar to view a list of all approved requests. This page displays the request number, request type, service deployment name, applicant, business group, project, request status, request time, and completion time.

>「Note」
If you want to view the details of a pending service request, please refer to: [Approved Request](#ApprovedRequest)。

# My request {#My request}

Select a manual ticket service and click to enter the manual ticket service information details page. Enter the basic information of the service: title, description, priority, urgency, the mobile phone number of the applicant's information required, click on the application to apply for the service successfully. After the service application is successful, the service request status is changed to the processing, and the request enters my request.          

Users can view the tickets that the user has applied for and track the ticket processing process according to the following steps:


1. Click "Requests" - "My Requests" in the left navigation bar. My request page displays the basic information of my request: request number, request type, title, service name, business group, project, request status, request Time, completion time.

2. Select the service request of any manual ticket service, click the “Request Number” link, and jump to the manual ticket service request details page to view the basic information of the request, ticket information, processing record, approval process, approval record and so on.

3. Approval process: approval flow chart, approval level, approver, role. Approval record: approval process information, approval process name, status, approval opinion, approver, approval role, approval time

4. Basic information includes request number, request time, request type, applicant, contact information, email address, business group, project, etc.

5. Ticket information includes title, description, priority, urgency, and field information from form configuration. 

6. Process record information: process steps, descriptions, process descriptions, process status and handlers, processing time.

# Pending approval{#Pendingapproval}

On the pending page, the approver configured by the administrator in the approval process has the approval authority and can view the details of the service request to be approved and approve the operation.

1. In the left navigation bar, click "Request" - "Pending Approval". Pending Approval page displays the pending approvals for all the approval requests you initiated. It displays the basic information of the approval request: request number, request type, service deployment, name, applicant, business group, project, request status, request time.

2. Select a request, click the “Request Number” link, and go to the My Request Details page to view the approver of the request, approval status, basic information, ticket information, service deployment information, component parameters, IP address, deployment. Resource occupancy information overview, service request, resource request basis, and so on.

3. Basic information includes request number, request time, request type, applicant, business group, project, and so on.

4. Service deployment basic information includes service catalog, service deployment name, quantity, and reason.

<!-- -->

1. Set parameters are collected from Blueprint Deployment Component Parameters

2. View the overview of deployment resource occupation information: resource bundle name, resources to be allocated, etc.

3. Service request information: approval process, approval process name, status, approval comments, approver, approval role, approval time and approval comments.

4. Click the Approval button at the bottom of the page to approve the application. The application status is changed to Approved. If you click Reject, the application will be rejected. Fill in the approval comments and click Return and the request will be returned to the applicant to modify the request details.

# Approved Request{#ApprovedRequest}

All requests that have been approved are displayed here.

In the left navigation bar, click "Requests" - "Approved". The approved page displays the parts of all the approval requests that you have approved, including the basic information of the approval request: request number, request type, service deployment name. applicant, business group, project, request status, request time.

# Pending Requests {#Pending Requests}

The service request waiting for the service group to process is displayed here

1. In the left navigation bar, click "Request" - "Pending Requests". The pending page displays the pending part of all processing requests initiated, which displays the basic information of the processing request: request number, service name, request type, title, business group, project, request status, request time, completion time.

2. Select a pending service request, click the “Request Number” link, and jump to the request details page to view the basic information of the request, ticket information, processing records, process steps, service processing information, and so on.

3. Basic information includes request number, request time, request type, applicant, contact information, email address, business group, project, etc. Ticket information includes name, description, priority, urgency, and field information from form configuration. 

4. Processing records include process steps, descriptions, descriptions of processing results, status, processors, and processing time.

5. Process steps:

 + Initiating an application: The service applicant initiates a manual ticket service through the service catalog, waiting for the service group to process

 + Service Processing: Need to assign the right person to complete this ticket task

 + Reprocessing: The applicant judged that the problem was not resolved satisfactorily and chose to return the service to the service staff for processing.

 + Confirm Close: If the applicant determines that the problem has been satisfactorily resolved, then close the service.

6. Processing methods: direct processing and transfer processing

 + Select direct processing method, click direct processing, fill in the processing result description, you can click submit button at the bottom of the page to complete the service request, email the service applicant, the applicant can close the ticket. The service request status is changed to "Processed".

 + Select the transfer processing method, click Transfer, select the service group, process personnel and transfer instructions, click the submit button at the bottom of the page to complete the service request, and the service request status is “Processing”.

# Processed {#Processed}

Here display the requests that the service group has processed and the applicant has confirmed to close.

1. Click "Requests" - "Processed" in the left navigation bar, and the page displays the processed part of all processing requests initiated.

2. Display the basic information of the processing request: request number, request type, service name, title, applicant, business group, project, request status, request time, completion time。

3. Select a request, click the “Request Number” link, and go to the My Request Details page to view the basic information of the request, ticket information, and process records.


# All requests

Tenant administrators can view the details of all applications as follows:

1. Click "Service Request" - "All Requests" on the left menu bar to view a list of all applications for the tenant, including pending approval and approved, pending process and processed (For pending process and processed please refer to Chapter IX).

2. This page displays the request number, service name, request type, title, business group, project, request status, request time, and completion time. Click on "Request Number" to view the details of the request.

3. Basic information includes request number, request time, request type, applicant, contact information, email address, business group, project, etc.

4. Ticket information includes title, description, priority, and urgency.

5. Approval information includes approver, approval status, service deployment name, service request, and resource request basis.

6. Processing records including process steps, descriptions, processing result descriptions, status, handlers, processing time.

>「Note」Default tenant administrator has permission to view all applications
