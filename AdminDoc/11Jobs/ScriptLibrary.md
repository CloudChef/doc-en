
**Script Library**

# Introduction

Script: Refers to tools or commands that can be run on the terminal. The platform supports scripts such as Shell, Perl, Bat, PowerShell, Python, and SQL.

Script library: The administrator creates and manages a large number of scripts in a unified manner. The platform supports the creation of shared scripts according to business needs for authorized business group members of certain roles to directly reference in any scenario.


Features: Standardize management of scripts applicable to multiple environments on a unified platform. Support create, edit, and delete scripts directly and quick search for newly created scripts.
Flexibly select the type of the cloud resource (instance, database, etc.) executed by the script. Take the creation of a MySQLCheck script checking database parameters as an example. You can specify the cloud resource type executed by the script as RDS under Software and RDS under PaaS. You can also view the detailed log information of the script execution in the execution history. For specific steps, please refer to [Execution History](http://CMP-PUBLIC-IP/help/AdminDoc/11作业管理/执行历史.html)


# Specific steps to create and use scripts
## Create a Script
The platform supports the creation of multiple types of scripts. Here we take the creation of a SQL script — MySQLCheck script as an example. This script is suitable for checking database parameters.
1. In the left navigation, select "Jobs"-"Script Library", click the "Add" button, and the script creation page appears.
2. Enter the script name MysqlCheck, select the cloud resource type as RDS under Software and RDS under PaaS. When you choose to allow sharing, you can specify the business group and role that can use the MysqlCheck script. If sharing is not allowed, only the creator can use The script.

    ![创建脚本](../../picture/Admin/创建脚本.png)

3. Fill in the relevant parameters in the script content input box. For example, the MysqlCheck script in the figure below defines detailed parameters, such as error log storage path, database storage path, and database size.

![脚本内容](../../picture/Admin/脚本内容.png)

## Script Execution

### Quickly Execute Scripts During Operation 

Take, for example, a script that quickly executes parameter check for database resources. The specific steps are:
1. In the left navigation, select "Deployments"-"Resources", select the successfully deployed database, and click to execute the script.
2. On the script execution configuration page, choose to a successfully created MysqlCheck script to automatically and quickly complete the database parameter check.

![执行脚本](../../picture/Admin/执行脚本.png)   

### Associate Scripts and Tasks

Take the database inspection scenario as an example. First, you need to add and complete the MysqlCheck script in the script creation interface, and then complete the binding of the operation and the script in the task creation interface. When the pipeline is executed automatically, it is actually the script running at the bottom layer. For more details, please refer to [Task Configuration](http://CMP-PUBLIC-IP/help/AdminDoc/11Jobs/#Task%20Configuration)



