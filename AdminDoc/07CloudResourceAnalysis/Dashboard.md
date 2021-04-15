**Dashboard**

The dashboard page displays the content that the user cares about most after logging in, such as the total amount of resources requested, the ranking of resource utilization, the deployment being performed, the waiting approval, and the resources that are about to expire.

The system provides four built-in dashboards: cloud resource usage dashboard, business group dashboard, project dashboard, and infrastructure dashboard. By access control, different built-in dashboards can be displayed for different users under the dashboard menu directory. For the specific method of setting access control, please refer to: [Edit Existing Dashboard](#EditExistingDashboard). The user clicks on the "Dashboard" in the left navigation bar, and the menu will display all the dashboards that the current user has permission to see.

At the same time, the system provides a custom dashboard function, which allows users to customize the displayed content.


# Built-in Dashboard

The system provides four built-in dashboards: cloud resource usage dashboard, business group dashboard, project dashboard, and infrastructure dashboard. The following will introduce you the specific display content:

## Cloud Resource Usage Dashboard

The cloud resource usage dashboard displays the deployed cloud resource usage in the form of graphs. Users can view the distribution of cloud resources, alerts, and service deployments that are about to expire.

The system displays the following modules by default: cloud resource distribution, instance overview, instance operating system distribution, instance and application alerts, ongoing operations, service deployments that are about to be uninstalled, service deployments that are about to expire, the instance with the highest CPU utilization -Top10, instance with the lowest CPU utilization-Top10, instance with the highest memory utilization-Top10, instance with the lowest memory utilization-Top10, instance with the highest disk utilization-Top10 and instance with the lowest disk utilization -Top10.

By default, tenant members can view the cloud resource usage dashboard. Click the arrow at the top right of the module to download the complete results of the specific report of the module. The export format supports .csv, .xlsx and .json.


## Business Group Dashboard

The business group dashboard displays the distribution of personnel resources in the business group and the overview of cloud resources, so that users can clearly and intuitively understand the overall situation of the business group's infrastructure.

The system displays the following modules by default: business group instance distribution, number of business group members, pending approvals, business group instance request trends, business group instance removal trends, business group resource average delivery time, business group resource overview and business Group personnel resource distribution.

By default, business group administrator, infrastructure administrator, and tenant administrator can view the business group dashboard. Click the arrow at the top right of the module to download the complete results of the specific report of the module. The export format supports .csv, .xlsx and .json.


## Project Dashboard

The project dashboard shows the distribution of project instances, the number of project members, pending approvals, project instance request trends, project instance removal trends, and project resource average delivery time.

By default, project administrators, infrastructure administrators and tenant administrators can view the project dashboard. Click the arrow at the top right of the module to download the complete results of the specific report of the module. The export format supports .csv, .xlsx and .json.


## Infrastructure Dashboard

By default, the infrastructure dashboard displays the overall situation of the virtualization platform, displaying IP pools, host overview, resource bundles with the highest CPU quota usage-Top 10, resource bundles with the highest memory quota usage-Top 10, resource bundles with the highest storage quota usage- Top10 and the resource bundle with the highest virtual machine quota usage-Top10.


By default, business group administrator, infrastructure administrator, and tenant administrator can view the infrastructure dashboard. Click the arrow at the top right of the module to download the complete results of the specific report of the module. The export format supports .csv, .xlsx and .json.



# Edit Existing Dashboard{#EditExistingDashboard}

Click on the navigation bar "Settings"-"Menu"

You can edit the added dashboard and configure some parameters, such as: name, description, icon, the display order of the dashboard in the menu directory, URL parameters, the role that have access to dashboards, and whether to enable the dashboard.

For a detailed description of each parameter, please refer to: [Menu](https://cloudchef.github.io/doc/AdminDoc/09Settings#Menu)


# Add Custom Dashboard

The platform supports users to add custom dashboards, and users can add custom dashboards configured through the dashboard backend in the menu settings.

Dashboard can display resource usage or alerts of virtual machines, service deployments, hosts, etc., and can also display personnel resource profiles of resource bundles, business groups, and projects.

Dashboard can be private or shared with other people in the team.


You can create a new dashboard as follows:

1. Create a new dashboard: access the cloud management platform-Public-IP/metabase through a browser to log in to the dashboard service.

2. Click Create and enter the name, description and classification.

3. Add report modules to the board: business groups and resource bundles reports, virtual machine reports, expense reports, project report, etc.

4. After creating the dashboard, click share, choose to embed the dashboard in an application, and publish the dashboard.

5. Return to the platform dashboard configuration page, fill in the parameters, and add a dashboard. For adding steps, please refer to: [Add Menu Configuration](https://cloudchef.github.io/doc/AdminDoc/09Settings#Menu)

![仪表盘](../../picture/Admin/仪表盘.png)


