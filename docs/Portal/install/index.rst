Appleseed Portal Installation
=============================


Quick Install
-------------
* Requirements

 *  .NET Framework 4.6 : `<https://www.microsoft.com/en-us/download/details.aspx?id=49981>`_
 *  Windows 7 | 8 | 10+ Physical or Cloud Instance
 *  SQL Server All Editions (Express tested) 2005 - 2016 
 *  Visual Studio 2015 All Editions (Community Tested) for development

* Release

  * Grab the latest release : `<https://github.com/Appleseed/portal/releases>`_

* Database

  * Download Microsoft SQL Server Express if you do not already have it : `<https://msdn.microsoft.com/en-us/sqlserver2014express.aspx?f=255&MSPPError=-2147217396>`_
  * Launch SQL Server Management Studio and connect to the server.
  * If there is an issue connecting to the server, launch SQL Server Configuration Manager and reconnect the stopped servers

  * Create an Empty SQL Server Database in a SQL Server Instance

    .. image:: ../images/Database-Setup.jpg
   *Right click on the Databases folder in the Object Explorer on the left and click on "New Database".
   *Enter a name in the Database Name: field

  * Set up NT AUTHORITY/NETWORK SERVICE as a Login if it doesn't exist
   *Right Click on the Logins folder in the main Security folder
   * Select "New Login.."
   * Click on the Search button next to the Login Name field.
   Click on the "Advanced..." button.
   * In this next window, click on the "Find Now" button on the middle right side.
   * Find "NETWORK SERVICE" in the list, highlight it and click on "OK".
   * Click "OK" in the next window. 

  * Give a user access to your SQL Server Database [ Network Service is recommended ]

    .. image:: ../images/User-Access1.jpg


  * Give this user db_owner in the user mapping section to your Database

   .. image:: ../images/User-Access2.jpg

* IIS Hosting

  * Unzip the archive to a non-windows controled folder such as C:\\Appleseed [ ie : Not the Windows folder or folders locked ]

    .. image:: ../images/Unzip.jpg


  * Create a Site in IIS with a .NET 4.0 Application Pool

    .. image:: ../images/IIS1.jpg


  * Change the Identy on the Application Pool to Network Service [ The site will run under this identity ]

    .. image:: ../images/IIS2.jpg


  * Point the IIS site folder to C:\\Appleseed  or where you unzipped your archive

    .. image:: ../images/IIS3.jpg


  * Browse your Site which will cause a redirect to the Web Installer

    .. image:: ../images/Web-Installer.jpg


* Web Installer

  * Follow the Instructions of the Web Installer
  * Give write access to the Identity [ ie NetworkService ] of your Application Pool to the below Files and Directories

              .. image:: ../images/Directories-Access.jpg


       * The Web Installer will do an environment check to ensure the proper permissions
       * Web.config – Needs write if you want the web installer to set your web.config up for you [ recommended ]
       * This should be removed after install
       * \\rb_logs – Needs write to provide error / info logs
       * \\Portals – Needs write to allow writing site files

* Post Installation

  * On successful installation you should see a bootstrap theme and a login

    .. image:: ../images/Portal.jpg


  * Use the default login admin@appleseedportal.net \| admin
  * Use Edit Profile to change your password
