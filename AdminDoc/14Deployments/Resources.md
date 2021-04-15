**Resources**

Under the cloud resource menu, all the cloud resources are uniformly managed, the related information is displayed and the corresponding to each cloud resource are provided.

Click on "Deployments" - "Cloud Resources" in the left navigation bar. On the left, you will see five menus: "Storage", "Container", "Network Resources", "PaaS" and "Software".

### Storage {#Storage .afff6}

Cloud hard disk

Support unified management of OpenStack/Azure/Alibaba Cloud/QingCloud cloud hard disk.

1. Click “Cloud Drive” under “Storage” and you will see the list of cloud drives.

2. On the list of the cloud disk, you can view related information about the cloud disk: name, cloud platform type, status, business group, service deployment, project, owner, size (GB), mount status, mounted cloud host, and creation time

3. Click on the name to go to the cloud drive details page. The cloud hard drive details page includes "Basic Information" and "Operation History"

4. Basic Information page of the cloud drive details includes:

-  	Basic information: name, cloud platform type, status, business group, service deployment, project, owner, cloud host to which the size is mounted, creation time, etc.

-   Organization information: service deployment name, service name, business group, tenant, project, etc.

-   Operations:

<!-- -->

-  	Volume separation: remove the mount relationship between the cloud drive and the cloud host

-  	Volume mounting: Establish mount relationship between cloud and cloud hosts

-  	Resize: Supports resizing of hard drives (Azure/AWS)

5. Operation History: include the operation history of the cloud drive.

Object storage

Supports unified management of object storage for AWS, Azure, and Alibaba Cloud, respectively S3, Blob, and OSS.en

1. Click “Object Storage” under “Storage” and you will see the object storage list.

2. In the object storage list interface, you can view related information about object storage: name, cloud platform type, status, status, business group, service deployment, project, owner, creation time.

3. Click on the name to enter the object storage details page. The object storage details page includes "Basic Information" and "Operation History"

4. Basic Information page of the object storage details includes:

-  	Basic information: name, cloud platform type, status, owner, public access level, storage account, resource group, creation time, etc.

-  	Organization information: service deployment name, service name, business group, tenant, project, etc.

5. Operation History: includes the operation history of the cloud hard disk.

### Container {#Container .afff6}

Support to display various component information of Kubernetes in cloud resources, including deployment, container, service, route (Ingress), storage volume (PVC), configuration dictionary (Config Map), secret dictionary (Secrets), etc.

Deployment

Kubernetes' deployment provides declarative updates for Pod and Replica Sets. By describing the desired cluster state in the Deployment, the Deployment Controller will gradually update the current cluster state to the desired cluster state at a controlled speed. The main responsibility of Deployment is also to ensure the number and health of Pod. 90% of the functions are exactly the same as Replication Controller and can be regarded as the next generation Replication Controller.
 +  Support the deployment of resources for the deployment, click on "Container" - "Deployment", you will see the deployment list of Kubernetes: display name, cloud platform type, status, business group, service deployment, project, owner, label , container group, image, and creation time. Advanced Search quickly categorizes list information by business group, status, project, and owner.

 +  Click on the name to go to the deployment details page. The deployment details page includes "Basic Information", "Container Group", "Operation History", "Monitoring", "Triggered Alert", and Operations such as "Update Copy Quantity", "Update Image", "Adjust Configuration".

>「Note」"Monitoring" and "Triggered Alerts" tab will only appear if the Prometheus monitoring address is set on the Kubernetes cloud platform.

 +  Basic Information page of the deployment includes:

-   Basic information: name, namespace, tags, notes, policies, images, creation time, etc.

-   Organization information: service deployment name, service name, business group, tenant, project, etc.

-   Operations:

<!-- -->

-   Update the number of copies: Update the number of copies of the POD (Replicas), click to select the number of copies to be updated in the box, or enable the timing to perform operations at specific times.

-   Update Images: Update the instance image of the deployment. Click to select the container node to be updated in the pop-up box (required), select the image source, select the image name (required), select the image label, or enable the timing to perform operations at specific times. Click "Submit" and wait for the operation to complete.

 >「Note」Support integration of Habor and Docker native images as Image Registry. In the Kubernetes cloud platform, a container image source can be added. Reference: [Add Kubernetes Cloud Platform ](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html)

-   Adjust container configuration: adjust the size of the vCPU and memory of the selected container node, including the request value and maximum value, and the request value (request) must be less than the maximum value (limit)

 +  Operation History: includes the operation history of the deployment.

 +  Monitoring: Display the monitoring information of the deployment, such as Pod CPU usage, Pods memory usage, Pod network traffic, etc. You can change the time span to view the monitoring information of different time periods.

 +  Triggered Alerts: According to the defined alert policy and alert operation for the container, if the monitoring information detects that the deployment has reached the triggering alert condition, an alert will be triggered. This page displays the triggered alert information and can be used to resume, pause, cancel, etc.

Daemon set

The Kubernetes daemon set (Daemon Set) guarantees that a copy of the container is run on each Node, often used to deploy some cluster logs, monitoring or other system management applications. After the deployment is successful, you can view the details in Cloud Resource - Containers - Daemon Set in the left navigation bar.

  In the Container Service - Daemon Set, you can view basic information about the daemon set, such as: name, cloud platform type, status, business group, service deployment, project, owner, label, container group, image, and creation time, etc. Advanced Search quickly categorizes list information by business group, status, project, and owner

  Click on the name to go to the Daemon Set details page. Including "Basic Information", "Container Group", "Operation History", "Monitoring", "Triggered Alerts ", etc.

  Basic Information page includes:

-   Basic information: name, namespace, label, comment, image, creation time, etc.

-   Organization information: service deployment name, service name, business group, tenant, project, etc.

-   Operations: update the image, adjust the configuration

 ④	Operation History page: Includes the history of operations performed on the daemon group

>「Note」"Monitoring" and "Triggered Alerts" tab will only appear if the Prometheus monitoring address is set on the Kubernetes cloud platform.

Stateful replica set

Kubernetes' stateful set (Stateful Set) is to solve the problem of state service. It consists of the following parts: Headless Service for defining DNS domains, volumeClaimTemplates for creating PersistentVolumes, and StatefulSet for defining specific applications. After the deployment is successful, you can view the details in Cloud Resource - Containers - Stateful Replica Set in the left navigation bar.

  In Containers - Stateful Replica Set, you can view basic information about a stateful replica set, such as: name, cloud platform type, status, business group, service deployment, project, owner, label, container group, images	 and creation time, etc. Advanced Search quickly categorizes list information by business group, status, project, and owner.

  Click on the name to go to the details page of the Stateful Set. Including "Basic Information", "Container Group", "Operation History", "Monitoring", "Triggered Alerts", and Operations such as "Update Copy Quantity", "Update Image", "Adjust Configuration", etc.

Container

After the K8s Container is successfully deployed, you can view the details in Cloud Resource - Containers in the left navigation bar.

  In the Container list interface, you can view the container's name, cloud platform type, status, business group, service deployment, project, owner, image, port, creation time, and so on. Advanced Search quickly categorizes list information by business group, status, project, and owner

  Click on the name to go to the details page of the container. Including "Basic Information" and "Operation History"

  Operations: "Adjust configuration"

Service

In a K8 cluster, the service that the client needs to access is the Service object. Each Service corresponds to a valid virtual IP inside the cluster, and a service is accessed through the virtual IP inside the cluster. After the deployment is successful, you can view the details in Cloud Resource - Container - Service in the left navigation bar.

  In the list of services of the container service, you can view the name of the service, cloud platform type, status, business group, service deployment, project, owner, cluster IP, internal endpoint, external endpoint, creation time, and so on. Advanced Search quickly categorizes list information by business group, status, project, and owner.

  Click on the name to go to the service details page. Includes pages such as "Basic Information", "Container Group", "Operation History", "Monitoring", "Triggered Alert", etc.

  Operations: "Update the number of copies", "Update the image" and "Adjust the configuration"

Routing

In Kubernetes, the IP of the service and pod is usually only accessible inside the cluster. Requests outside the cluster need to be forwarded to the NodePort exposed by the service on the Node through load balancing, and then forwarded to the relevant Pod by the kube-proxy, and the ingress is a collection of routing rules for the request to enter the cluster. After the deployment is successful, you can view the details in Cloud Resource – Container - Routing in the left navigation bar.

1. On the Ingress list, you can view the name of the route, cloud platform type, status, service group, service deployment, project, owner, endpoint, rule, creation time, and so on. Advanced Search quickly categorizes list information by business group, status, project, and owner

2. Click on the name to enter the routing details page. Including "Basic Information" and "Operation History"

Storage volume

The storage volume (PVC: Persistent Volume Claim) in Kubernetes is a request stored by the user. It is similar to pod. The Pod consumes node resources, and the PVC consumes photovoltaic resources. After the deployment is successful, you can view the details in Cloud Resource – Container - Storage Volume in the left navigation bar.

1. 在On the storage volume (PVC) list interface, you can view the name of the storage volume, cloud platform type, status, business group, service deployment, project, owner, volume status, total amount, access mode, storage class, creation time, etc. Advanced Search quickly categorizes list information by business group, status, project, and owner.

2. Click on the name to go to the details page of the storage volume. Including "Basic Information" and "Operation History”

Configuration dictionary

In Kubernetes, the configuration dictionary (ConfigMap) is used to store key-value pairs of configuration data, which can be used to save a single attribute or to save a configuration file. ConfigMap is similar to the secret dictionary (Secret), but it makes it easier to work with strings that don't contain sensitive information. After the deployment is successful, you can view the details in Cloud Resource - Container - Configuration Dictionary in the left navigation bar.

1. In the ConfigMap list interface, you can view the name of the configuration dictionary, cloud platform type, status, business group, service deployment, project, owner, creation time, and so on. Advanced Search quickly categorizes list information by business group, status, project, and owner.

2. Click on the name to go to the details page of the configuration dictionary. Including "Basic Information" and "Operation History"

Secrets

In Kubernetes, the secret dictionary solves the configuration problem of sensitive data such as passwords, tokens, keys, etc., without exposing the sensitive data to images or Pod Specs. Secret can be used as a Volume or as an environment variable. After the deployment is successful, you can view the details in Cloud Resource - Container - Secret Dictionary in the left navigation bar.

1. In the list of the secret dictionary, you can view the name of the secret dictionary, cloud platform type, status, business group, service deployment, project, owner, type, creation time, and so on. Advanced Search quickly categorizes list information by business group, status, project, and owner.

2. Click on the name to go to the details page of the confidential dictionary. Including "Basic Information" and "Operation History"






### Network resource 

Supports OpenStack firewall (FireWall), floating IP (Floating IP) independent deployment and full lifecycle management. After the deployment is complete, you can view basic information and health status in Cloud Resources - Network Resources. It also supports OpenStack's load balancer (LoadBalance) and load balancing listener (Listener), as well as VMware NSX's virtual server (VirtualServer).

Load balancer

Load balancing is a key component of a highly available network infrastructure and is typically used to distribute workload across multiple servers to improve the performance and reliability of a website, application, database, or other service.

If the load balancer (LoadBalancer) is included in the deployment, you can view the details in Cloud Resources - Network Resources - Load Balancer after the deployment is successful.

1. On the load balancer (LoadBalancer) list interface, display the name of the load balancer, cloud platform type, status, service group, service deployment, project, owner, IP address, creation time, etc.

2. Click on the name to go to the details page, including "Basic Information" and "Operation History"

3. Operations (OpenStack):

-   Bind floating IP: Select a floating IP, bind the load balancer and floating IP, and start timing to perform operations at specific time.

-   Unbind floating IP: If the load balancer is bound to a floating IP, you can unbind the operation and start the operation at a specific time.

Load balancing listener

VMWare NSX / OpenStack / Azure load balancing listener is supported. VMWare NSX load balancing listener is VirtualServer, OpenStack load balancing listener is Listener, and Azure load balancing listener is LoadBalancerRule. The load balancer can listen for requests on multiple ports, each specified by a load balancing listener. After the deployment is successful, you can view the details in Cloud Resources - Network Resources - Load Balanced Listener.

1. In the load balancer listener (Listener) list interface, display the name, status, description, business group, project, owner, protocol, cloud platform type, creation time, etc. of the load balancing listener.

2. Click the name to enter the details page, including the "Basic Information" and "Operation History" interface, and operations of "Add Member" and "Delete Member".

3. Operations – OpenStack

-   "Add members": add internal and external members. Select the instance to which you want to add members, specify the IP address, port, and weight. Bootable timing can be performed at specific times.

-   Delete member: Click to select the member to be deleted, you can set up timing to perform operations at a specific time.

Floating IP

Supporting OpenStack's floating IP (Floating IP), Floating IP can be deployed separately. After the deployment is successful, you can view the detailed information by selecting "Cloud Resources" - "Network Resources" - "Floating IP" in the left navigation bar.

1. Select Cloud Resource - Network Resource - Floating IP to view the list of successfully deployed floating IPs. The interface displays the name of the floating IP, cloud platform type, status, business group, service deployment, and Project, owner, IP address, network, mapped address, creation time, etc.

2. Click on the name to go to the details page, including "Basic Information" and "Operation History"

3. "Basic Information" page, showing the basic information and organization information of the floating IP

4. “Operation History” page, showing the operation history. When clicked, the operation details will be displayed below the operation history list.

5. Operations:

-   “Associated Port”: If the current floating IP is not associated with any port, the “Associated Port” operation will be displayed at the top of the details page. After clicking, select the port to be bound in the bullet box. All unassociated ports (Ports) in the OpenStack cloud platform will be listed in the drop-down box. Select "Submit" after selecting.

-   “Unbind”: If the current Floating IP has been associated with the port, the “Unbind” operation will be displayed at the top of the details page. Click “Submit” to enable the operation at a specific time.

Firewall

Support for OpenStack Firewall as a service, Fwaas for OpenStack objects such as projects, routers and router ports. The core concepts of the OpenStack firewall are firewall policies and firewall rules. A policy is an ordered collection of rules. In the left navigation bar, select "Cloud Resources" - "Network Resources" - "Firewall" to view the deployed firewalls.

1. Select Cloud Resources - Network Resources - Firewall to view the successfully deployed firewall list interface, which displays the name of the firewall, cloud platform type, status, business group, service deployment, project, owner, Policy, routing, activation status, administrator status, creation time, etc.

2. Click on the name to go to the details page, including "Basic Information" and "Operation History"

3. Basic Information: displays basic and organizational information about the firewall.

4. Operation History page: Display the operation history. When clicked, the operation details will be displayed below the operation history list.

5. Operations：

Update Firewall: Click to select an existing firewall policy or create a new firewall policy. Check "Use existing policy" to list all available firewall policies in the OpenStack cloud platform under the current business group. If it is not checked, create a new firewall policy, fill in the policy name (required), policy description (optional), choose whether it is shared, audited, or timed. Click “Submit” after the operation is completed.

Update Firewall Policy: This page lists a list of all currently available rules. Support for using existing rules and creating new rules. If you use an existing rule, check the rules that will be used in the list. If you create a new rule, click + on the upper right corner of the list to display the new rule interface:

-   Fill in the basic information: name, description, protocol (required, TCP, UDP, ICMP, and any), action (required, allowed, denied), source IP, source port, destination IP, destination port, whether the selection is shared and activate.

-   You can select the location of the new rule, specify that the current rule is inserted before a rule (before the rule), or specify that the rule is inserted after a rule (after the rule). If both are specified, the former has a higher priority.

>「Note」：A firewall policy can be associated with multiple rules, but rules can only be associated with one policy.

Delete firewall rules: Delete the associated rules in the firewall. After deletion, they will not be recoverable. You can select multiple rule deletions at the same time, or you can start timing to perform operations at specific times.

Security group

A security group is a virtual firewall with stateful inspection and packet filtering to divide security zones in the cloud. You can configure or disable the access of a virtual machine instance in a security group to the public or private network by configuring a security group rule.

Support for displaying security groups for OpenStack, AWS, Azure, and Alibaba Cloud. If the security group component is deployed, the deployed security group components are viewed in Cloud Resources - Network Resources - Security Groups.

1. On the Security Group list page, display the security group name, cloud platform type, status, business group to which it belongs, service deployment, project, owner, creation time, etc.

2. Click on the name to go to the details page, including the "Basic Information" and "Operation History".

3. Basic Information page displays basic information, organization information, and inbound/outbound security group rules for the security group.

4. Operation History shows the operation history. When clicked, the operation details will be displayed below the operation history list.

Domain Name System DNS

Support OpenStack Domain Name System DNS. If the DNS component is deployed, the deployed DNS components will be viewed in "Cloud Resources" - "Network Resources" - "Domain Name System DNS".

1. On the Domain Name System DNS list, display the DNS name, status, business group, project, owner, DNS type, DNS domain, DNS server, DNS parameters, etc.

2. Click on the name to go to the details page, including the "Basic Information" and "Operation History".

3. Operations

-   Update DNS: update DNS parameters, DNS type cannot be changed

### PaaS resources

Supports independent deployment and full lifecycle management of relational databases (RDS) of AWS, Azure, and Aliyun, supporting relational database as a service (RDS as a Service) and web applications. After the deployment is complete, you can view basic information and health status in Cloud Resources - PaaS Resources.

Relational Database

In the left navigation bar, select "Cloud Resources" - "PaaS Resources" - "Relational Databases" to view the successfully deployed relational database (RDS).

1. In the list interface of the relational database, you can view information about the relational database, such as name, business group, project, owner, cloud platform type, creation time, etc.

2. Click on the name to enter the relational database details page. There are two pages: “Basic Information” and “Operation History”.

3. Basic Information page displays basic and organizational information for the relational database.

4. Operation History shows the operation history of the relational database. When clicked, the operation details will be displayed below the operation history list.

5. Operations:

-  Update the firewall: Click the relational database name to enter the details page or select a relational database in the relational database list page, click the “Update Firewall” button to open the “Update Firewall - RDS Name” popup window. Check "Timer", set the execution time, click the "Submit" button to update the firewall regularly; or click the "Submit" button to update the firewall immediately.

Web application

In the left navigation bar, select "Cloud Resources" - "PaaS Resources" - "Web Application" to view the successfully deployed web applications.

1. In the web application list interface, you can view related information about the web application, such as name, business group, project, owner, cloud platform type, creation time, etc.

2. Click on the name to enter the web application details page. There are two pages: “Basic Information” and “Operation History” 

3. Basic Information page displays basic and organizational information for the web application.

4. Operation History page shows the operation history of the web application. When clicked, the operation details will be displayed below the operation history list.

### Software Resources

> Support unified display and management of software resources.

1. Select Cloud Resources - Software Resources - Software to view a list of successfully deployed software that displays the software name, cloud platform type, status, business group, service deployment, project, owner, version, system type, creation time, etc. Filter your business groups, status, projects, or owners with advanced search, or use normal search for quick targeting.

2. Click on the name to go to the details page, including "Basic Information" and "Operation History"

3. Basic Information displays basic information, organization information, and parameters of the software.

4. Operation History displays the operation history. When clicked, the operation details will be displayed below the operation history list.

5. Operations:

> The operations displays the corresponding operations according to the operation definition of the software in "Service Design" - "Software Components", for example, start, stop, delete, create, configure, etc.

