.. toctree::
	:titlesonly:
	
=========================================== 
Deployment 
=========================================== 


Client
------

This document provides the basic and detailed setup instructions for new 
Windows environments, specifically for Appleseed development under source control for client projects,
generally deployed on a physical Server or on the Cloud.

Directory Structure
------------------

Below is an overview of the directory structure for deploying a single Anant Application.
Please note for some old clients this is list as C:\Services or C:\Accounts or C:\Sites

- C:\Accounts - Create an accounts directory on the root of the primary drive.  It would be nice if you can store this on a drive other than C:\ as only the OS should reside there. 
- C:\Accounts\ClientName - Create a unique client name for an individual site
- C:\Accounts\ClientName\prod - The production directory for the site that will be seen in the public  This should be on the client’s environment or AWS.













.. include:: /././common.txt