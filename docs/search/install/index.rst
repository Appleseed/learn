Appleseed Search Installation
=============================


Quick Install
-------------

Root Page for Installation instructions for Appleseed Search

Appleseed Search Web User Installation and Customization on Appleseed Portal.

If you have not already installed Appleseed Portal, refer to the instructions here  `<http://learn.appleseedapp.net/en/latest/docs/Portal/install/#quick-install>`_

* Steps to set up Angular Search Interface on an Appleseed Site.

   * Open a code editor (such as Visual Studio 2015, or another compatible version).
   * Go to the folder in which you installed Appleseed 
   
     * Navigate to ...\Appleseed\Design\DesktopLayouts\[Theme used]\DesktopPortalBanner.ascx
     * Make sure you choose the file in the folder for the theme used not the one directly in the .\Appleseed\Design\DesktopLayouts\ folder
     * add the Following script:
     
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

     * Create a folder called "CSS" in the ...Design\Themes\[Theme Used]\ folder
     * Add the as-search.css file which can be found in the /Portals/_Appleseed/Search.Web.User.Ng/app/css/appleseed/ folder

   * Updating css file

     * Add the @import rules below to the bottom of the @import rules located at the top of the default.css file in the \Design\Themes\[Theme used]\ folder: 

@import url(/Portals/_Appleseed/Search.Web.User.Ng/app/css/bootstrap/bootstrap.min.css

@import url(/Portals/_Appleseed/Search.Web.User.Ng/app/css/bootstrap/bootstrap-responsive.min.css);

@import url(bootstrap.css);

@import url(as-admin-bar.css);

@import url(/Portals/_Appleseed/Search.Web.User.Ng/app/css/solr-ajax/screen.css);

@import url(/Portals/_Appleseed/Search.Web.User.Ng/app/css/solr-ajax/facp.css);

@import url(/Portals/_Appleseed/Search.Web.User.Ng/app/datepicker/css/datepicker.css);

@import url(css/as-search.css);

       .. image:: ../images/Import-Rules.PNG

     * Copy the Angular and other script references listed below to the location beneath the </footer> element in the SiteMaster.master in the \Design\DesktopLayouts\[Theme_used] folder 
   <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/d3js/d3.v3.min.js"></script>

        <!-- angular scripts -->
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/lib/angular/angular.min.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/lib/angular/angular-route.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/lib/angular/angular-sanitize.min.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DateFacetController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DateFacetHistogramController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DateRangeFacetController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DatePickerFacetController.js"></script>
       
        <!--<script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DocumentSearchResultsController.js"></script>-->
       
        <!--<script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DocumentSearchHighlightResultsController.js"></script>-->
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DocumentSearchFeaturedResultController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/DocumentSearchHighlightMLTResultsController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/FacetSelectionController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/FieldFacetController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/SearchBoxController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/controllers/SearchHistoryController.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/directives/autocomplete.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/filters/textfilters.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/services/selection.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/services/solr.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/services/utils.js"></script>
       
        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/js/solr-ajax/app/document.js"></script>
       
        <!-- /angular scripts -->

        <script type="text/javascript" src="/Portals/_Appleseed/Search.Web.User.Ng/app/datepicker/js/bootstrap-datepicker.js"></script>

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
       * Set up an HTML Module or Modules for the Angular search section or sections.to be used on this page.







