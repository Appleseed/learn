======================= 
Upgrade Instructions
======================= 

 

Manual Upgrade 
--------------

* Create a Backup Directory for all your Site and SQL backups.
* Backup your Site Directory as a compressed (zip) archive.
	* Store this archive in your Backup Directory.
* Backup your Appleseed portal SQL database using SQL Server Management Studio.
* Backup your custom application database if your instance has custom modules.
* Make sure you have completed the above steps BEFORE proceeding.
* Download the latest stable release of `Appleseed Portal <https://github.com/appleseed/portal>`_.
	* Create a New Folder in your Web Server Directory for the new upgraded site
		* Extract the contents of the UPGRADE package into a folder on your computer
		* It is NOT recommended that you extract directly over your old website.
		* Copy the following from your OLD site folder to your new Upgraded site folder: 
			* \Portals Directory - To ensure your sites files are carried over
			* \Design Directory - To ensure that all design and theme files are carried over
* Configure IIS for a new website on a different port ( IE 81 )
	* Make sure you have the proper .NET Framework for the build as it may have changed
* Create a new Integrated application pool if using IIS Web Server
* Setup Permissions on the file system in your newly created dirctory
	* Make sure your Application Pool user has read / write permission to :
		* \Portals Directory - To allow for file storage per portal 
		* \rb_logs Directory - To allow logs to be rewritten
		* Web.config - Only during upgrade to have settings written 
* Restore your portal database backup to a NEW database name.
* Once you have the upgraded website running you can modify your website settings in IIS to utilize the new website, rather than the non-* upgraded website.
* Check to see if the instance is using any modules that were removed from the upgrade.
* Check to see if the instance custom modules are still working as they did before the upgrade.

.. toctree::
    :titlesonly:
  
.. include:: /./common.txt
