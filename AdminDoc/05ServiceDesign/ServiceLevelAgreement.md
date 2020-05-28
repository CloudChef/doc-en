**Service Level Agreement**

Concept: The service level agreement is a commitment and agreement between the service provider and the service applicant. The agreement stipulates the time and other conditions for the completion of the service. User can associate service level agreements with services provided by the platform (for example: manual tickets, cloud resource deployment, and task execution) to ensure timely tracking of service processing.

Application scenario: In the traditional resale mode, the SLA agreement is written into the contract and has someone to track it. In the new resale scenario, SmartCMP binds the SLA to the service. Service applicants and service providers can automatically track the entire process and view the service progress and the time spent in real time.

Main functions:
+ Tenant administrators can create one or more service level agreements, define service response time (two optional time units, days / hours), service agreement name, description, priority (highest, high, medium, Low), and users and roles notified by email.

+ Service level agreements are created once and can be applied to different services repeatedly, but a service configuration can only be associated with one service level agreement.

+ Define four SLA status: the remaining time accounts for 50% -100% of the response time, the status is normal; the remaining time accounts for 25% -50% of the response time, the status is warning; the remaining time accounts for the response time 0-25 %, the status is critical; and the remaining time is below 0, the status is overdue. For example, the tenant administrator sets the SLA response time to 4 hours. After the tenant member request service, if the remaining time for service processing is more than 2 hours, then the SLA status color is green; if the remaining time is within 1 hour and 2 hours the SLA status color is displayed in yellow; if the remaining time is within 0-1 hours, the color of the SLA status displays orange; and if it is overdue, the color of the SLA status displays red.

+ When the SLA level changes, a notification will be sent to the role or user configured by the administrator in advance.

+ Administrators can configure service level agreements for related services. They can be set as allowing changes when applying and published to the service catalog after the configuration is completed. When users request services through the service catalog, they can choose service level agreements as needed.

+ If the administrator has configured a service level agreement for the service, and the service is configured with an approval process in which the SLA is not allowed to be modified on the approval page, when the approver rejects the service request and the applicant reapplies for the service, the remaining time is still calculated based on the previous request time.


The following describes the configuration steps of the service level agreement.

## Add Service Level Agreement

Tenant administrators have the authority to create, edit, and delete service level agreements. Tenant members only have the right to view. Tenant members with service configuration rights can associate service level agreements with services.

+ Tenant administrators select "Service Design"-"Service Level Agreement" on the left navigation, click Add to enter the creation interface, fill in the service name, description, priority (highest, high, medium, low), and the user and role notified by email (single or multiple roles).


+ Associate service level agreements in the service configuration interface, supporting cloud resource deployment services, ticket services, task execution services, and many other service types. The parameters may be set as allowing changes when applying. When requesting services, the end user can choose the service level agreement again according to actual needs.

+ After the end user initiates a service request, he/she can view SLA status information in My Request list. Four SLA status are defined: Normal, the remaining time accounts for the response time in the range of 50% -100% and the color is displayed in green. Waring, the remaining time accounts for 25% -50% of the response time and the color is displayed in yellow. Critical, the remaining time accounts for the response time 0-25 % and the color is displayed in orange. Overdue, the remaining time is below 0 and the color is displayed in red. When the SLA status changes, the configured user or role will be notified by email.


## Edit and Delete Service Level Agreement

Select "Service Design"-"Service Level Agreement" in the left navigation, and click Edit on the service level agreement list interface to modify the relevant information of the agreement.

Select "Service Design"-"Service Level Agreement" in the left navigation, and click Delete to delete the agreement.