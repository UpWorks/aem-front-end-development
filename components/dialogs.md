Dialogs
=======

Flip over to the browser - lets look at the Button component.
 
**May need to enable the components in the sidekick via the Design interface.

Drag the Button Component from the sidekick to an open parsys.

[![Screen](http://upworks.github.io/aem-development/imgs/components-dialog.png)](http://upworks.github.io/aem-development/imgs/components-dialog.png)

Lets go ahead and author this component.

Now lets take a look at the file that drives this dialog, the `dialog.xml`
````
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:nt="http://www.jcp.org/jcr/nt/1.0"
    jcr:primaryType="cq:Dialog"
    stateful="false"
    xtype="dialog">
    <items
        jcr:primaryType="cq:Widget"
        xtype="tabpanel">
        <items jcr:primaryType="cq:WidgetCollection">
            <basicProperties
                jcr:primaryType="cq:Panel"
                title="Properties">
                <items jcr:primaryType="cq:WidgetCollection">
                    <link
                        jcr:primaryType="cq:Widget"
                        collapsed="{Boolean}false"
                        collapsible="{Boolean}true"
                        title="Button Link"
                        xtype="dialogfieldset">
                        <items jcr:primaryType="cq:WidgetCollection">
                            <text
                                jcr:primaryType="cq:Widget"
                                fieldLabel="Label"
                                name="./text"
                                allowBlank="{Boolean}false"
                                xtype="cgctextfield"/>
                            <linkUrl
                                jcr:primaryType="cq:Widget"
                                fieldLabel="Link"
                                name="./linkUrl"
                                parBrowse="{Boolean}true"
                                parLinkPattern="\{0}#{1}"
                                xtype="pathfield"/>
                            <openNewWindow
                                jcr:primaryType="cq:Widget"
                                boxLabel="Open in New Window"
                                name="./openNewWindow"
                                type="checkbox"
                                xtype="selection"/>
                            <promoCode
                                jcr:primaryType="cq:Widget"
                                fieldLabel="Campaign code"
                                name="./campaignCode"
                                xtype="textfield"
                                validator="function(value){return Validators.validateCampaignCode(value);}"/>
                        </items>
                    </link>
                    <styling
                        jcr:primaryType="cq:Widget"
                        collapsed="{Boolean}false"
                        collapsible="{Boolean}true"
                        title="Button Styling"
                        xtype="dialogfieldset">
                        <items jcr:primaryType="cq:WidgetCollection">
                            <cssClass
                                jcr:primaryType="cq:Widget"
                                defaultValue=""
                                fieldLabel="Style"
                                name="./cssClass"
                                type="select"
                                xtype="selection">
                                <options jcr:primaryType="cq:WidgetCollection">
                                    <standard
                                        jcr:primaryType="nt:unstructured"
                                        text="Standard"
                                        value=""/>
                                    <subdued
                                        jcr:primaryType="nt:unstructured"
                                        text="Subdued"
                                        value="btn-subdued"/>
                                </options>
                            </cssClass>
                            <size
                                jcr:primaryType="cq:Widget"
                                defaultValue=""
                                fieldLabel="Size"
                                name="./size"
                                type="select"
                                xtype="selection">
                                <options jcr:primaryType="cq:WidgetCollection">
                                    <fourteen
                                        jcr:primaryType="nt:unstructured"
                                        text="Large"
                                        value=""/>
                                    <twelve
                                        jcr:primaryType="nt:unstructured"
                                        text="Small"
                                        value="btn-small"/>
                                </options>
                            </size>
                            <horizontalAlignment
                                jcr:primaryType="cq:Widget"
                                defaultValue="align-left"
                                fieldLabel="Horizontal Alignment"
                                name="./horizontalAlignment"
                                type="select"
                                xtype="selection">
                                <options jcr:primaryType="cq:WidgetCollection">
                                    <left
                                        jcr:primaryType="nt:unstructured"
                                        text="Left"
                                        value="align-left"/>
                                    <center
                                        jcr:primaryType="nt:unstructured"
                                        text="Center"
                                        value="align-center"/>
                                    <right
                                        jcr:primaryType="nt:unstructured"
                                        text="Right"
                                        value="align-right"/>
                                </options>
                            </horizontalAlignment>
                            <icon
                                jcr:primaryType="cq:Widget"
                                fieldLabel="Icon"
                                defaultValue=""
                                name="./iconClass"
                                type="select"
                                xtype="selection">
                                <options jcr:primaryType="cq:WidgetCollection">
                                    <none
                                        jcr:primaryType="nt:unstructured"
                                        text="--None--"
                                        value=""/>
                                    <home
                                        jcr:primaryType="nt:unstructured"
                                        text="Home"
                                        value="home"/>
                                    <layers
                                        jcr:primaryType="nt:unstructured"
                                        text="Layers"
                                        value="layers"/>
                                    <gear
                                        jcr:primaryType="nt:unstructured"
                                        text="Gear"
                                        value="gear"/>
                                    <lock
                                        jcr:primaryType="nt:unstructured"
                                        text="Lock"
                                        value="lock"/>
                                    <audio
                                        jcr:primaryType="nt:unstructured"
                                        text="Audio"
                                        value="audio"/>
                                    <video
                                        jcr:primaryType="nt:unstructured"
                                        text="Video"
                                        value="video"/>
                                    <pricing
                                        jcr:primaryType="nt:unstructured"
                                        text="Pricing"
                                        value="pricing"/>
                                    <print
                                        jcr:primaryType="nt:unstructured"
                                        text="Print"
                                        value="print"/>
                                    <phone
                                        jcr:primaryType="nt:unstructured"
                                        text="Phone"
                                        value="phone"/>
                                    <refresh
                                        jcr:primaryType="nt:unstructured"
                                        text="Refresh"
                                        value="refresh"/>
                                    <cart
                                        jcr:primaryType="nt:unstructured"
                                        text="Shopping Cart"
                                        value="cart"/>
                                    <addToCart
                                        jcr:primaryType="nt:unstructured"
                                        text="Add to Cart"
                                        value="add-to-cart"/>
                                    <rss
                                        jcr:primaryType="nt:unstructured"
                                        text="RSS"
                                        value="rss"/>
                                    <share
                                        jcr:primaryType="nt:unstructured"
                                        text="Share"
                                        value="share"/>
                                    <fb
                                        jcr:primaryType="nt:unstructured"
                                        text="Facebook"
                                        value="facebook"/>
                                    <linkedIn
                                        jcr:primaryType="nt:unstructured"
                                        text="LinkedIn"
                                        value="linked-in"/>
                                    <mail
                                        jcr:primaryType="nt:unstructured"
                                        text="Mail"
                                        value="mail"/>
                                    <twitter
                                        jcr:primaryType="nt:unstructured"
                                        text="Twitter"
                                        value="twitter"/>
                                    <youTube
                                        jcr:primaryType="nt:unstructured"
                                        text="YouTube"
                                        value="you-tube"/>
                                    <download
                                        jcr:primaryType="nt:unstructured"
                                        text="Download (arrow pointing down)"
                                        value="download"/>
                                    <downloadDoc
                                        jcr:primaryType="nt:unstructured"
                                        text="Download document (doc with arrow)"
                                        value="download-doc"/>
                                    <preview
                                        jcr:primaryType="nt:unstructured"
                                        text="Preview document"
                                        value="preview"/>
                                    <newDocument
                                        jcr:primaryType="nt:unstructured"
                                        text="New document"
                                        value="new-document"/>
                                    <saved
                                        jcr:primaryType="nt:unstructured"
                                        text="Saved document"
                                        value="saved"/>
                                    <document
                                        jcr:primaryType="nt:unstructured"
                                        text="Generic document"
                                        value="document"/>
                                    <excel
                                        jcr:primaryType="nt:unstructured"
                                        text="Excel document"
                                        value="xls"/>
                                    <close
                                        jcr:primaryType="nt:unstructured"
                                        text="Close"
                                        value="close"/>
                                    <add
                                        jcr:primaryType="nt:unstructured"
                                        text="Add"
                                        value="add"/>
                                    <subtract
                                        jcr:primaryType="nt:unstructured"
                                        text="Subtract"
                                        value="subtract"/>
                                    <check
                                        jcr:primaryType="nt:unstructured"
                                        text="Check"
                                        value="check"/>
                                    <clipboard
                                        jcr:primaryType="nt:unstructured"
                                        text="Clipboard"
                                        value="clipboard"/>
                                    <education
                                        jcr:primaryType="nt:unstructured"
                                        text="Education"
                                        value="education"/>
                                    <paperClip
                                        jcr:primaryType="nt:unstructured"
                                        text="Paperclip"
                                        value="paper-clip"/>
                                    <pencil
                                        jcr:primaryType="nt:unstructured"
                                        text="Pencil"
                                        value="pencil"/>
                                    <read
                                        jcr:primaryType="nt:unstructured"
                                        text="Book"
                                        value="read"/>
                                    <calendar
                                        jcr:primaryType="nt:unstructured"
                                        text="Calendar"
                                        value="calendar"/>
                                    <magnify
                                        jcr:primaryType="nt:unstructured"
                                        text="Magnify"
                                        value="magnify"/>
                                    <zoom
                                        jcr:primaryType="nt:unstructured"
                                        text="Zoom (glass w/plus sign)"
                                        value="zoom"/>
                                    <enlarge
                                        jcr:primaryType="nt:unstructured"
                                        text="Enlarge (arrows out)"
                                        value="enlarge"/>
                                    <shrink
                                        jcr:primaryType="nt:unstructured"
                                        text="Shrink (arrows in)"
                                        value="shrink"/>
                                    <arrowRight
                                        jcr:primaryType="nt:unstructured"
                                        text="Arrow Right"
                                        value="arrow-right"/>
                                    <arrowUp
                                        jcr:primaryType="nt:unstructured"
                                        text="Arrow Up"
                                        value="arrow-up"/>
                                    <caretDown
                                        jcr:primaryType="nt:unstructured"
                                        text="Caret Down"
                                        value="caret-down"/>
                                    <caretRight
                                        jcr:primaryType="nt:unstructured"
                                        text="Caret Right"
                                        value="caret-right"/>
                                    <caretUp
                                        jcr:primaryType="nt:unstructured"
                                        text="Caret Up"
                                        value="caret-up"/>
                                    <triangleDown
                                        jcr:primaryType="nt:unstructured"
                                        text="Triangle Down"
                                        value="triangle-down"/>
                                    <triangleRight
                                        jcr:primaryType="nt:unstructured"
                                        text="Triangle Right"
                                        value="triangle-right"/>
                                    <triangleUp
                                        jcr:primaryType="nt:unstructured"
                                        text="Triangle Up"
                                        value="triangle-up"/>
                                </options>
                            </icon>
                        </items>
                    </styling>
                </items>
            </basicProperties>
        </items>
    </items>
</jcr:root>
````
Link to XTYPE Definitions:
[http://dev.day.com/docs/en/cq/5-5/developing/widgets/xtypes.html](http://dev.day.com/docs/en/cq/5-5/developing/widgets/xtypes.html)