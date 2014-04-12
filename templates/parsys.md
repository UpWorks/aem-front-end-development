The AEM Parsys
==============

###What is the Parsys?

The parsys is a drop area for components within AEM. If it is the desire to drop a componet into an area or section of your templates. It must contain a parsys.

The Parsys
````
<cq:include path="mainParsys" resourceType="foundation/components/parsys"/>
````
It is considered a best practive to decide on a parsys path naming convetion for use in your projects.

For example:
* `path="mainParsys"` for the main parsys on the page
* `path="secondaryParsys"` for a left or right rail of the page


