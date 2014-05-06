ClientLibs
==========

The client libs are a power feature of the AEM platform. 

When developing a component, in most if not all cases there is CSS and or JavaScript that is specific to the component. In the case of the Button Component the css is rolled into the core css file and there is no JavaScript.

Lets take a look at the Events Listing Component's clientlibs
[![Screen](http://upworks.github.io/aem-development/imgs/events-client-libs.png)](http://upworks.github.io/aem-development/imgs/events-client-libs.png)

Here you will see that the clientlibs node contains a CSS folder and a JS folder as well as two text files `css.txt` and `js.txt`
 
Lets take a quick look at the the two txt files. If we open the js text file.
````
#base=js
event-listing.js
````

The `#base=js` instructs the compiler that the base folder is js followed by the name or names of the JavaScript files that are to be included within the ClientLib.  During the build process AEM will create one js file and one css file respectively.  If there were more than 1 file all the files would be concatenated into one file and minified.
 
**Minified in AEM = White Space remove, line breaks still exist :(
 
Now in my component JSP I can include the client lib with one line:
`<cq:includeClientLibcategories="nextgen.event-listing" />`
Or
`<cq:includeClientLibcss="nextgen.event-listing" />`
And
`<cq:includeClientLibjs="nextgen.event-listing" />`
 
There is also the option to include this component's clientlib into a parent or global lib such as a head clientlib. Or the CSS can be including in the `css.txt` of the head and the JavaScript can by included in the foot clientlib's `js.txt` to delay the loading until the end of the page.

###Debugging Client Libs
From time to time it will be necessary to have to trouble shoot JavaScript or CSS in the browser.  AEM has a great feature to do so. Simply apply `?debugClientLibs=true` to the a URL path and AEM will unpack the concatenated  code.
 
Let's try that now and work with breakpoints in a JS file.
