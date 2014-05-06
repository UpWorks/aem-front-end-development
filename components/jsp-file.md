JSP File
========

Now lets walk through the JSP file for this component
````
<%@include file="/apps/af-foundation/components/shared/global.jsp"%>
<%@page import="com.capgroup.wcm.cgc.common.LinkURLUtil"%>
<%
    String linkUrl = LinkURLUtil.getLinkUrl(properties.get("linkUrl", ""));
    if (resource.getChild("iconImage/fileReference") != null) {
        pageContext.setAttribute("iconImage",resource.getChild("iconImage").adaptTo(ValueMap.class));
    }
    String buttonStyle = properties.get("cssClass","").toLowerCase();
    String iconClass = properties.get("iconClass", "none");
    if (iconClass.equals("none")) {
        iconClass = "";
    }
    String buttonTarget = "_self";
    if (properties.get("openNewWindow","false").equals("true")) {
        buttonTarget="_blank";
    }
    String onclick = "";
    if (!linkUrl.equals("")) {
        onclick += "onclick='window.open(\"";
        onclick += linkUrl;
        onclick += "\",\"";
        onclick += buttonTarget;
        onclick += "\")'";
        buttonStyle += " buttonLink";
    } 
    pageContext.setAttribute("linkUrl", linkUrl);
    pageContext.setAttribute("buttonSize",properties.get("size", "").toLowerCase());
    pageContext.setAttribute("horizontalAlignment",properties.get("horizontalAlignment", "align-left").toLowerCase());
    pageContext.setAttribute("buttonStyle",buttonStyle);
    pageContext.setAttribute("onclick",onclick);  
    pageContext.setAttribute("buttonTarget",buttonTarget);
    pageContext.setAttribute("iconClass", iconClass);
%>
<c:if test="${not empty properties.campaignCode}">
    <c:set var="campaignCode" value=' data-campaign-code="${fn:escapeXml(properties.campaignCode)}"'/>
</c:if>
<c:choose>
    <c:when test="${empty properties.text}">
Please Author Button Text
    </c:when>
    <c:otherwise>
        <cq:includeClientLib css="nextgen.button" />
<div class="clearBoth ${horizontalAlignment}">
    <a class="btn sub-section-margin ${buttonSize} ${buttonStyle} ${iconClass}" ${onclick}${campaignCode}>${not empty iconClass ? '<span class="icon"></span>' : ''}${properties.text}</a>
</div>
    </c:otherwise>
</c:choose>
````