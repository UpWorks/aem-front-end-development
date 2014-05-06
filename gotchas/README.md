Development Gotchas
===================

###Selectors:
As an AEM developer, you need to be aware of the wrapping elements that AEM wraps a component's HTML with.

[![Screen](http://upworks.github.io/aem-development/imgs/aem-additional-wrapper.png)](http://upworks.github.io/aem-development/imgs/aem-additional-wrapper.png)

###ClientLib Cache:
As a new AEM developer you will run into situations after you run a build where your CSS or JavaScript changes are not visible.
 
If you are using the `?debugClientLibs=true` during development you will also see changes immediately. However if you are not and do not see your changes there are two things you can do.
 
Within CRXDE Lite, navigate to your client lib's js or css txt file, Open it, CNTRL C the content of the file and CNTRL X followed by CNTRL S. Then CNTRL V and CNTRL S.  This will invalidate the clients libs cache and regenerate a new lib under `/var/clientlibs/apps/nextgen`

[![Screen](http://upworks.github.io/aem-development/imgs/var-clientlibs-loc.png)](http://upworks.github.io/aem-development/imgs/var-clientlibs-loc.png)

As a second option in CRXDE Lite you can simply delete the entire apps folder followed  by clicking save all.  This will have the same net affect.

[![Screen](http://upworks.github.io/aem-development/imgs/crxdelite-saveall.png)](http://upworks.github.io/aem-development/imgs/crxdelite-saveall.png)