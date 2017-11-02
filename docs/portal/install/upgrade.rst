======================= 
Upgrade Instructions
======================= 



Manual Upgrade 
--------------

* Create a Backup of for your Site and SQL databases and store them in a backup folder.
* Backup your Site Directory as a compressed (zip) archive.
	* Store this archive in your Backup Directory.
* Backup your Appleseed Portal SQL database using SQL Server Management Studio.
* Backup your Custom Application Database if your instance has custom modules.
* Make sure you have completed the above steps BEFORE proceeding.
* Download the latest stable release of `Appleseed Portal <https://github.com/appleseed/portal>`_.
	* Create a New Folder in your Web Server Directory for the new upgraded site.
		* Extract the contents of the UPGRADE package into a folder on your computer.
		* It is NOT recommended that you extract directly over your old website.
		* Copy the following from your OLD site folder to your new Upgraded site folder: 
			* \Portals Directory - To ensure your sites files are transferred over.
			* \Design Directory - To ensure that all design and theme files are transferred over.
			* \Bin Custom DLLs - Any custom application or third-party dlls that are required.
			* \DesktopModules\CustomModules - Any Custom Module(s) that have been installed.
			* Custom Folders - Any custom folders that have been created.
* Configure IIS for a new website on a different port ( IE 81 ).
	* Make sure you have the proper .NET Framework for the build as it may have changed.
		* This allows you to leave your old site in place should an issue occur with the upgrade.
* Create a new Integrated Application Pool if using IIS Web Server.
* Setup Permissions on the file system in your newly created dirctory.
	* Make sure your Application Pool user has read / write permission to :
		* \Portals Directory - To allow for file storage per portal.
		* \rb_logs Directory - To allow logs to be rewritten.
		* Web.config - Only make writable during upgrade to have settings written.
* Restore your portal database backup to a NEW database name.
* Open up your new Website on a different port ( IE 81 ).
	* Run through the web installer as normal.
		* Make sure the checks are all green.
	* Point to your newly restored SQL Database.
		* This way you only upgrade a restored backup of your database and can restore back if an issue occurs.
* Once you have the upgraded website running you can modify your website settings in IIS to utilize the new website, rather than the non-* upgraded website.
* Upgrade Check List
	* Check to see if Login works as expected for all User Role types.
	* Check to see if Users in the admin role have administrative permission.
	* Check to see if the new upgraded features are working as expected.
	* Check the rb_logs folder for any errors.
	* Check to see if the upgraded instance custom modules are still working as they did before the upgrade.
	* Check to see if the upgraded instance is using any modules that were removed from the upgrade.
	* Make a new backup of the updated database.
	* Make a new backup of the site directory.
	* Review css styling on existing pages

 Webconfig Keys
 --------------

* The following keys can be added/modified in the Portal's web.config file:
	* <add key="CSSLoadTop" value="true" />
		* When upgrading Appleseed Portal from early versions (pre 1.0.3.0), page styling may appear different.  This is because the default.css for the Portal is now loaded first, where previously it was being added in between other stylesheets.
		* To use the old css loading behavior, set CSSLoadTop to "false".

.. toctree::
    :titlesonly:
  
.. include:: /./common.txt




 

