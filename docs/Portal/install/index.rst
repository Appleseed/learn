Appleseed Portal Installation
=============================


Quick Install
-------------

* Release

  * Grab the latest release : `<https://github.com/Appleseed/portal/releases>`_

* Database

  * Create an Empty SQL Server Database in a SQL Server Instance

    .. image:: ../images/Database-Setup.jpg
|br|
  * Give a user access to your SQL Server Database [ Network Service is recommended ]

    .. image:: ../images/User-Access1.jpg
|br|
  * Give this user db_owner in the user mapping section to your Database

   .. image:: ../images/User-Access2.jpg
|br|
* IIS Hosting

  * Unzip the archive to a non-windows controled folder such as C:\\Appleseed [ ie : Not the Windows folder or folders locked ]

    .. image:: ../images/Unzip.jpg
|br|
  * Create a Site in IIS with a .NET 4.0 Application Pool

    .. image:: ../images/IIS1.jpg
|br|
  * Change the Identy on the Application Pool to Network Service [ The site will run under this identity ]

    .. image:: ../images/IIS2.jpg
|br|
  * Point the IIS site folder to C:\\Appleseed  or where you unzipped your archive

    .. image:: ../images/IIS3.jpg
|br|
  * Browse your Site which will cause a redirect to the Web Installer

    .. image:: ../images/Web-Installer.jpg


* Web Installer

  * Follow the Instructions of the Web Installer
  * Give write access to the Identity [ ie NetworkService ] of your Application Pool to the below Files and Directories

              .. image:: ../images/Directories-Access.jpg
|br|
       * The Web Installer will do an environment check to ensure the proper permissions
       * Web.config – Needs write if you want the web installer to set your web.config up for you [ recommended ]
       * This should be removed after install
       * \\rb_logs – Needs write to provide error / info logs
       * \\Portals – Needs write to allow writing site files

* Post Installation

  * On successful installation you should see a bootstrap theme and a login

    .. image:: ../images/Portal.jpg
|br|
  * Use the default login admin@appleseedportal.net \| admin
  * Use Edit Profile to change your password
