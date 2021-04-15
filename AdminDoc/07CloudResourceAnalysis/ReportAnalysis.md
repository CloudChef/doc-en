**Report & Analysis**


# Data Center Overview

For users with view overview permissions, users can see the Resource Analysis - Data Center Overview menu. The overview is used to view the current status of the data center and status information for the last 7 days. In SmartCMP, a data center is a collection of all cloud platforms in a geographic location. In the "Data Center" interface, users can see the data center map, as well as the current CPU, memory, storage, instance and physical host status and usage of each data center, click the "zoom in"   icon in the upper right corner and can enter full screen mode to view. 

On full screen display interface, you can press "Esc" to exit the full screen state.

Chart description:

- Data Center Distribution Graph: Displays current resources for all data centers in the system, including CPU, memory, storage, number of virtual machines, and number of physical hosts.

- Current resource usage: Shows resource usage in one or more data centers, including CPU, memory, and storage, and shows usage trends for nearly 7 days.

- Instance Overview: Displays the current number of instances and their corresponding status in one or more data centers

- Physical Host Overview: Displays the current number of physical hosts in one or more data centers and their corresponding status

- Number of instances and physical hosts in the last 7 days: Displays the number of instances and physical machines in the last 7 days of the data center and the corresponding status.

# Resource Request Trend

On the resource request page, the user can view the resource request status of the current tenant's business group. This page contains four charts, which correspond to the instance request /dismount amount (number), service deployment request /dismount amount, CPU request amount (number), memory request amount (GB) and hard disk request amount (GB).

Select the filter item at the top of the page: business group, type (each cloud platform), time span. The user can change the statistical mode of the chart by setting the time span, thereby obtaining the resource request information more intuitively.

# Business Group Resource Usage

On the business group resource occupation page, users can see the resource usage of each business group in the current system. The business group resource occupation page displays four kinds of information, corresponding to four charts, namely: CPU usage (number), memory usage (GB), storage usage (GB), and the number of virtual machines used (number).

The user can select the cloud platform in the type drop-down list, the chart will display the corresponding information of the currently selected cloud platform. User can also set the time span to change the chart statistics mode. If there are multiple business groups in the current system, the user can select a business group from the drop-down list of the business group. The data statistics page of the corresponding business group is displayed, and the corresponding chart is displayed to obtain information.

# Report

You can view related billing reports and instance status reports or other custom reports in Resource Analysis - Reports. In Settings - Reports, you can choose to enable or disable a report for different user roles. Support filtering criteria for multiple dimensions of the report and displaying column selection for the header. Excel files can be exported.


## Built-in Report

The system provides built-in billing reports and cloud platform overall situation reports for users to view.

Click "Report & Analysis"-"Reports" to view billing reports: business group expense statistics report, business group expense detail report. Click Generate on the current page to generate all reports for the business group to which the user belongs, and filter according to the cloud platform type, business group, and start time. Click Export to export the filtered report, the export format is an Excel file.

Click "Report & Analysis"-"Reports" to view the overall status report of the cloud platform: instance overall status report, virtual machine overall status report, storage overall status report, current month expiring virtual machine report and IP pool usage report. Click Generate on the current page, and filter by owner, query month, cloud platform type, IP pool, data center, business group, and project. Click Export to export the filtered report, the export format is an Excel file.

## Add Custom Reports

The platform also supports users to add custom reports on demand. Users can add custom reports configured in the menu settings to view on demand.

You can create a new report as follows:

+ Access SmartCMP-Public-IP/report through a browser to log in to the report service to create.

+ On the report design page, click Add (or click Add under a parent category), enter the report name, activation status, sorting and remarks, and click Save.

![报表1](../../picture/Admin/报表1.png)

+ On the report designer page, fill in the basic settings, data column configuration, SQL statements, query parameters and other information, and click Save.

![报表2](../../picture/Admin/报表2.png)

+ After creating the report, you can click Preview to preview the current report in the form of a table or chart.


## Report Configuration

The administrator can enable or disable a report in "System"-"Reports", and can choose to assign the report to a certain role for viewing, such as tenant members, business group administrators, software architects, and custom roles.