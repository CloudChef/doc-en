**Governance**

# Event

Used to define the scope to which the event applies and the notifications and actions that are triggered.

For example, an IP conflict detection alert (when an IP address is detected to be occupied by an unknown machine, it can trigger an alert), and supports:

+ Set notifications for IP collision detection (IP collision detected)
+ Notification/mail header: <time, accurate to seconds> IP address conflict detected: x.x.x.x
+ The content of the notification/mail: <time, accurate to the second> An IP address conflict was detected and x.x.x.x was occupied by an unknown machine. Please check the reason. This IP address will no longer be assigned
+ Successfully set notifications for instance deployments (instance deployment is successful)
+ Support for extending other types, such as instance name modification notifications, instance IP address modification notifications, and more.
+ Flexibly custom triggered event names, types, application scopes, triggered actions.

Specific steps:

Click on the left menu bar "Governance" - "Event", you will see the event configuration list, display name, type, scope, object, status, creator, creation time.

1. Add event configuration: Click Add, enter the event name, select the type (detect IP conflict, VM deployment completed), select the scope (tenant), and choose to trigger notification on an object. Notification configuration select user/role/e-mail. If the event is triggered, they will receive system notification and email notification

2. Edit event configuration: Select an event in the list, click "Edit" to enter the editing interface. May edit every parameter.

3. Enable/Disable Event: Select an enabled/disabled event in the list interface, and the disable/enable operation above will be available.

## Operation configuration:

Provides common task configuration for automatic operation triggered by alerts, event configuration, etc. (specific operation configuration steps are similar to pipeline process design task configuration)
+ Common requirements scenarios include: After the VM is deployed, you need to register to the springboard; after the VM is deleted, you can log off the springboard; after the alert scenario occurs, you can create a ticket process.
+ Implementation ideas: After the event occurs, the alert can be triggered. The configuration operation is the same as the pipeline configuration task.
+ For example, after the cloud resource is deployed, not only can the e-mail notification occur, but also the operation of the cloud resource. The notification and operation can be configured at the same time.

 + Other common usage scenarios include: after the VM is deployed, you need to register to the bastion host; after the VM is deleted, you can unregister the bastion host; after the alert scenario occurs, you can create a ticket process 


# Event History
List the events triggered and the status of the tasks performed. The event history page displays:
+ Show event number (event_timestamp), event name, event type, trigger object, trigger time, notification object (no display if without notification), trigger operation (no display if without operation), operation execution status
+ The triggering object displays the actual object name. For example, if an IP conflict is detected, the triggering object displays a specific IP address. If the deployment is completed or updated, the triggering object is the deployment.
+ Quickly locate events based on filter criteria (event type, operational status, start and end time)
+ Click on any event to enter the event details page: including the event itself, notification information, and triggered action information. (Event information: What time, for which object, what triggered. Notice: notification sent to who (displayed the role name, username, email address together). Triggered action information: What action was triggered, operation State, execution result and output).


