.. toctree::
	:titlesonly:
	
=========================================== 
Deployment 
=========================================== 


Client
------

This document provides the basic and detailed setup instructions for new 
Windows environments, specifically for Appleseed development under source 
control for client projects, generally deployed on a physical Server or on the Cloud.

Directory Structure
------------------

Below is an overview of the directory structure for deploying a single Application.
Please note for some old clients this is list as C:\Services or C:\Accounts or C:\Sites

* C:\Accounts - Create an accounts directory on the root of the primary drive.  It would be nice if you can store this on a drive other than C:\ as only the OS should reside there. 
* C:\Accounts\ClientName - Create a unique client name for an individual site.
* C:\Accounts\ClientName\prod - The production directory for the site that will be seen in the public  This should be on the client’s environment or AWS.
* C:\Accounts\ClientName\stage - The staging or verification site directory.  This site may or may not be public.  This site is used by the client to review the latest stable development fixes.  This should be on the client’s environment or AWS.
* C:\Accounts\ClientName\[environment]\www - Store the actual site/application/appleseed install in this directory.
* C:\Accounts\ClientName\[environment]\backup - Store site & SQL Data backups in this directory .
* C:\Accounts\ClientName\SiteName - Create a unique site directory for each site and follow the above directory recommendations.


Database 
--------

Appleseed Portal Database Naming 
[client_ap_environment]

Production
- clientname_ap_prod

Stage
- client_ap_stage

Application Database Naming 
[client_app_environment]

Production
- client_app_prod

Stage
- client_app_stage

Deployment Steps
----------------

* Alert Services in the Client Slack Room to inform the client of the deployment ( especially if it takes down the site longer than an hour
* Get approval from the PM
* Pause the site in IIS
* Backup the Current www directory and store in the \backup folder with the date in the folder name
 ** You may only need to backup exactly what you replace
 ** For major changes, backup the whole folder
* Apply the update to the www directory
* If there were any DB changes, Backup the Current SQL Database and store the backup file in the backup folder
* Apply the SQL database update (May need to restart SQL Server)



.. include:: /././common.txt