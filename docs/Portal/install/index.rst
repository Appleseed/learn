Appleseed Portal Installation 
=============================


Quick Install
-------------

* Release

   * Grab the latest release : `<https://github.com/Appleseed/portal/releases>`_ 
   
* Database

   * Create an Empty SQL Server Database in a SQL Server Instance
   
     * Give a user access to your SQL Server Databse [ Network Service is recommended ]
     * Give this user db_owner in the user mapping section to your Database
     
* IIS Hosting

  * Unzip the archive to a non-windows controled folder such as C:\\Appleseed [ ie : Not the Windows folder or folders locked ]
  * Create a Site in IIS with a .NET 4.0 Application Pool
  
     * Change the Identy on the Application Pool to Network Service [ The site will run under this identity ]
     * Point the IIS site folder to C:\\Appleseed  or where you unzipped your archive
     * Browse your Site which will cause a redirect to the Web Installer
     
* Web Installer

  * Follow the Instructions of the Web Installer
  * Give write access to the Identity [ ie NetworkService ] of your Application Pool to the below Files and Directories
  
       * The Web Installer will do an environment check to ensure the proper permissions
       * Web.config – Needs write if you want the web installer to set your web.config up for you [ recommended ]
       * This should be removed after install
       * \\rb_logs – Needs write to provide error / info logs
       * \\Portals – Needs write to allow writing site files
       
* Post Installation

  * On successful installation you should see a bootstrap theme and a login
  * Use the default login admin@appleseedportal.net \| admin
  * Use Edit Profile to change your password
