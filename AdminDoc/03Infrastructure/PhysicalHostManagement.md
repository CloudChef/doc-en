**Physical Host Management**


You can select “Infrastructure” on the left navigation and select the secondary menu “Physical Host Information” to add physical host information to manage the physical machines on the cloud platform and those temporarily not on the cloud platform.

# Add/Edit a Physical Host

Go to "Infrastructure" - "Physical Host ", click the "Add" button, select the platform (currently supports OpenStack, vSphere, physical server, PowerVC), and enter the physical host related information:

-   Basic information: physical machine name, IP address, cloud platform, platform type. Click “Save” and the physical host is added successfully

-   Physical machine information: fill in the relevant information of the physical machine, such as manufacturer, model, MAC address, etc., all optional

For OpenStack and vSphere, if the IP address filled in matches the IP address of a host in the actual cloud platform, the physical host resource information is automatically captured, which is visible on the basic information tab during next edit.

SmartCMP automatically synchronizes all physical host information under vSphere and OpenStack cloud platforms to the list every day 

# View Physical Host Information

After the physical host is successfully added, you can view all the added physical host information on the physical host list interface. Click the name to enter the basic information page, and obtain the resource information, storage information, and network information of the physical host through the input information.

# Delete Physical Host Information

On the physical host list page, select a physical host and click Delete in the menu bar. After confirming, the physical host information will be deleted.
