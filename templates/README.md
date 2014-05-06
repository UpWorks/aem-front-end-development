Templates
=========

A template is the foundation to what becomes the page the user views in the browser.  Think of the templates as scaffolding for your web pages.

Each template you create is extended or overlayed from the AEM base template.

###Step 1
Navigate to `apps/nextgen/templates` and right click on the fullwidth template and select  copy.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-1.png)](http://upworks.github.io/aem-development/imgs/templates-step-1.png)

###Step 2
Right click on the `apps/nextgen/templates` folder and select Paste

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-2.png)](http://upworks.github.io/aem-development/imgs/templates-step-2.png)

###Step 3
A window will popup and ask you to name the copied folder. Enter the value trainingtest.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-3.png)](http://upworks.github.io/aem-development/imgs/templates-step-3.png)

###Step 4
Select the newly created folder, now click n the properties tab at the bottom of the IDE. Rename the jcr:title to Training Template.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-4.png)](http://upworks.github.io/aem-development/imgs/templates-step-4.png)

Now expand the trainingtest folder and click on the `_jcr_content` and click on the Properties tab at the bottom of the IDE and rename the `sling:resourceType` to `nextgen/components/pages/trainingtest`

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-4b.png)](http://upworks.github.io/aem-development/imgs/templates-step-4b.png)

###Step 5
Select the `apps/nextgen/components/pages/fullwidth` folder. Right click and select Copy.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-5.png)](http://upworks.github.io/aem-development/imgs/templates-step-5.png)

###Step 6
Select the `apps/nextgen/components/pages` folder. Right click and select Paste.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-6.png)](http://upworks.github.io/aem-development/imgs/templates-step-6.png)

###Step 7
A window will popup and ask you to name the copied folder. Enter the value trainingtest.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-7.png)](http://upworks.github.io/aem-development/imgs/templates-step-7.png)

###Step 8
Select the newly created folder, now click n the properties tab at the bottom of the IDE. Rename the `jcr:title` and `jcr:description`  to Training Template.

[![Screen](http://upworks.github.io/aem-development/imgs/templates-step-8.png)](http://upworks.github.io/aem-development/imgs/templates-step-8.png)

Now the template is available to the authors.
[![Screen](http://upworks.github.io/aem-development/imgs/templates-complete.png)](http://upworks.github.io/aem-development/imgs/templates-complete.png)

