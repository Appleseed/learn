.. toctree::
   :titlesonly:

=============================
Appleseed Search Installation
=============================

.. contents:: Table of Contents

Appleseed Search Web User Installation and Customization outside of Appleseed Portal.
-------------

This section explains how to use the Appleseed Search frontend without embedding it into an Appleseed Search module.

You may download the necessary files from `<https://github.com/Appleseed/search-web-user>`_

* Steps to set up a standalone Angular Search Interface.

	* Download the project from Github and navigate to the folder ``Appleseed.Search.Web.User.Ng.Solr/app``.
	* Each of the sample HTML search pages (documents.html, images.html, location.html) runs a single-page Javascript application that is responsible for executing search actions and displaying results. The application will use configuration values specified in the HTML to determine where to send its queries.  Typically the application configuration files are located in ``app/js/solr-ajax/app/`` and named after the respective sample page.
	* In particular, the "data-source" attribute tells the application what the URL is to your Solr core. Set the "data-source" attribute to the URL to your Solr core.

		* ex. data-source="http://localhost:8983/solr/core"
		* The URL to your Solr core must be resolveable and accessible by the browser. If you are running the application as a public service, then the URL to your Solr core must be publicly accessible.

	* documents.html contains most of the sample front-end elements with the latest Angular controllers.
	* Load the HTML search page in your browser and attempt to execute searches against your Solr index. If you experience any problems, open your browser console. You should see log entries for each search query that is executed, and information about any errors that may have occurred.
	* You should also customize the HTML search page to use the appropriate controllers and to populate them with the appropriate Solr field.

Appleseed Search Web User Installation and Customization on Appleseed Portal.
-------------

This section explains how to combine the Appleseed Portal and Search products.  Appleseed Portal is used as a Front End to the Appleseed Search product.

You may download the necessary files from `<https://github.com/Appleseed/search-web-user>`_

If you have not already installed Appleseed Portal, refer to the instructions here  `<http://learn.appleseedapp.net/en/latest/docs/portal/install/#quick-install>`_

* Steps to set up an Angular Search Interface on an Appleseed Site.

   * Open a code editor (such as Visual Studio 2015, or another compatible version).
   * Go to the folder in which you installed Appleseed 
   
     * Navigate to ``...\Appleseed\Design\DesktopLayouts\[Theme used]\DesktopPortalBanner.ascx``
     * Make sure you choose the file in the folder for the theme used not the one directly in the ``.\Appleseed\Design\DesktopLayouts\`` folder
     * add the Following script:
	 
		::
     
			// Add attributes to html element for Angular Search
	   
			$("html").attr({

			  "xmlns":"http://angularjs.org",
			  
			  "id":"ng-app",
			  
			  "ng-app":"solr-ajax"
			  
			});

		.. image:: ../images/Script-Update.PNG

     * Verify that the script is working.
     
       * Navigate to the Appleseed portal page.
       * Right click and click inspect elements. 
       * Check if the code has been added to the <html> element

        .. image:: ../images/Script-Verification.PNG

   * CSS Folder

     * Create a folder called "CSS" in the ``...Design\Themes\[Theme Used]\`` folder
     * Add the as-search.css file which can be found in the /Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/appleseed/ folder

   * Updating css file

     * Add the @import rules below to the bottom of the @import rules located at the top of the default.css file in the ``\Design\Themes\[Theme used]\`` folder: 

		::	 
	 
			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/bootstrap/bootstrap.min.css;

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/bootstrap/bootstrap-responsive.min.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/bootstrap/bootstrap.css);

			@import url(as-admin-bar.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/solr-ajax/screen.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/solr-ajax/facp.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/solr-ajax/hints.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/datepicker/datepicker.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/chosen/chosen.css);

			@import url(/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/css/chosen/chosen-spinner.css);

			@import url(css/as-search.css);

       .. image:: ../images/Import-Rules.PNG

     * Copy the Angular and other script references listed below to the location beneath the </footer> element in the SiteMaster.master in the ``\Design\DesktopLayouts\[Theme_used]`` folder 
	 
		::	 
		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/d3js/d3.v3.min.js"></script>

		<!-- angular scripts -->

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/lib/angular/angular.js"></script>

		<!--<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/bower_components/angular/angular.min.js"></script>-->
		
		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/lib/angular/angular-route.js"></script>
		
		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/lib/angular/angular-cookies.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/lib/angular/angular-sanitize.min.js"></script>

		<!-- scripts - chosen -->

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/chosen/chosen.jquery.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/chosen/angular-chosen.js"></script>

		<!-- controllers and directives -->

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DateFacetController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DateFacetHistogramController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DateRangeFacetController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DatePickerFacetController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DocumentSearchResultsController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DocumentSearchFeaturedResultController.js"></script>

		<!--<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DocumentSearchHighlightResultsController.js"></script>-->

		<!--<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/DocumentSearchHighlightMLTResultsController.js"></script>-->

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/FacetSelectionController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/FacetClearSelectionController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/FieldChosenFacetController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/FieldFacetController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/SearchBoxController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/SearchBoxHistoryController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/controllers/SearchHistoryController.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/directives/autocomplete.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/filters/textfilters.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/filters/usfitextfilters.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/services/selection.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/services/solr.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/services/utils.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/app/document.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/directives/searchbox.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/directives/searchboxHistory.js"></script>

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/solr-ajax/directives/count-to.js"></script>

		<!-- /angular scripts -->

		<script type="text/javascript" src="/Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/js/datepicker/bootstrap-datepicker.js"></script>
		
			<script>

				$(function() {
		   
					$(dateValidation).hide();
		   
					var checkin = $('#sDate').datepicker({format: 'mm/dd/yyyy'}).on('changeDate', function (ev) {
		   
						if (ev.date.valueOf() > checkout.date.valueOf()) {
		   
							var newDate = new Date(ev.date)
		   
							newDate.setDate(newDate.getDate() + 1);
		   
							checkout.setValue(newDate);
		   
						}
		   
						checkin.hide();

						$('#eDate')[0].focus();
		   
					}).data('datepicker');

					var checkout = $('#eDate').datepicker({format: 'mm/dd/yyyy'}).on('changeDate', function (ev) {
	 
						checkout.hide();

					}).data('datepicker');
				});

			</script>
		
    * Setting up Search on the Appleseed Site.
   
       * Login as admin. 
       * Click on the Site Manager(or Administration) tab on the left side of the	Admin Bar at the top. 
       *	Under Add New Page
   
         * Select a Page Parent (or leave as default if this page should be on the Root Level.) 
         * Select the roles that can see the page under Page Visible To:
         * Add a Page Title, such as Search.
         * Click the Add New Page button. 
         * Navigate to the new page. 

     * On this page, 
   
       * Click the Edit this Page link in the Admin Bar.
       * Click the Page Modules tab. 
       * Set up an HTML Module or Modules for the Angular search section or sections to be used on this page.

     * Add the Module code. 
    
       * Click on Edit icon for the Module created
       * Switch to Source if the editor is in visual mode, and paste in the contents of the search-module.html file in the /Portals/_Appleseed/Appleseed.Search.Web.User.Ng.Solr/app/ folder.
	   * Customize the module code as necessary for the various controllers and fields you wish to use.

Update styling as necessary in the as-search.css file added to the ``\Design\Themes\[Theme used]\css`` folder.


.. include:: /././common.txt





