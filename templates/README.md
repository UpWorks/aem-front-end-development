Templates
=========

A template is the foundation to what becomes the page the user views in the browser.  Think of the templates as scaffolding for your web pages.

Each template you create is extended or ovelayed from the AEM base template.

The first step is to create a new folder under the `apps/nextgen/templates` path.

TODO: Insert image of dialog that is presented to the user when creating the folder as a node.

####Content.xml

````
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:Template"
    jcr:title="NextGen Content One Fourth Right Rail Template"
    jcr:description="Standard template with a 1/4-wide (3-grid columns) &quot;Related&quot; right rail"
    allowedPaths="/content(/.*)?"
    ranking="{Long}2060">
    <jcr:content
        jcr:primaryType="cq:PageContent"
        sling:resourceType="nextgen/components/pages/onefourthrightrail"/>
</jcr:root>
````