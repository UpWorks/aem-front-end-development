Template Structures
===================


Lets take a quick look at the maincontent.jsp under the `pages/testingtemplate` path:
````
<%@include file="/apps/af-foundation/components/shared/global.jsp"%>
<c:choose>
	<c:when test="${not pageProperties.hideTitleBar}">
		<c:set var="titleBarBackground" value=" ns-title-wide"/>
	</c:when>
	<c:otherwise>
		<c:set var="titleBarBackground" value=""/>
	</c:otherwise>
</c:choose>

<div class="ns-body-wide ${titleBarBackground} fullwidth">
    <div class="ns-outer-control">
        <div class="ns-body container">
            <div class="row">
                <div class="span12">
                	<c:if test="${not pageProperties.hideTitleBar}">
						<cq:include path="titleBar" resourceType="/apps/nextgen/components/layout/title-bar"/>
					</c:if>						
                    <div class="ns-main-parsys">
                        <cq:include path="mainParsys" resourceType="foundation/components/parsys"/>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
````