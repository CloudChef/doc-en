**Resource Recycle**


# System Automatic Resources Recycle

SmartCMP setup lease time and retention time of service deployments through business group or service configuration, so that resources can be automatically recycled within a specified time after being applied for.

1. “Organization” - “Business Groups”, click the name of the business group to enter the “Overview” page, where you can modify the service deployment lease time range and service deployment retention time range under the business group.

2. “Service Design” - “Service Configuration”, click the service configuration name to enter the Overview page, where you can modify the service deployment lease time and service deployment retention time under the service configuration.

>「Note」The lease/retention time in the service configuration cannot exceed the maximum time range on the business group.

If the lease time of the service expires, all instances under the deployment will be automatically shut down.

If the retention time of the service expires, all instances under the deployment will be deleted and the resources will be released.

# Manually Recycle Resources

1. "Deployments" - "My Deployments", enter the service deployment list interface, select a service deployment, and a list of operations for the service will appear at the top.

2. Click Dismount Service Deployment, which will remove all cloud resources contained in the service deployment.

3. Users can also "enable timing" timing to dismount resources

4. After “OK”, if the business group has an approval process, the execution will be started after the approval is passed; if there is no approval process, the removal will start directly.

# Service Deployment Extension

If the service is expiring, the service deployment can be extended.

1. Click “Organization” - “Business Group” in the left navigation bar to enter the “Overview” page. On this page, you can configure the “Maximum Deferrable Times” under the business group to ensure that the service rental time can still be expired. You can also control resource requests in the business group.

2. After the business group member service request is successfully deployed, in the "Deployments" - "My Deployment", select a service deployment, and the "Expiration Time" operation will appear at the top of the service deployment list interface.

3. Click “Extend” to extend the expiration time. The page also displays “Extended Times” and “Maximum Deferrable Times” under the business group.

4. Click “OK”. If the business group has an approval process, it will be executed after the approval is passed; if there is no approval process, it will be executed directly.

# Recycle Bin

Recycle bin function to optimize the recycling process

Recycle bin function to optimize the recycling process

1. In the left menu, select Deployment - Recycle Bin to manually delete the service deployment on the Recycle Bin list page. The status of the resource stage is displayed as deleted. The service deployment information is kept for one day by default and after the expiration it is permanently deleted, and the resources are also permanently released from the cloud platform.

2. Click “Restore” on the recycle bin list page to restore the resource.
