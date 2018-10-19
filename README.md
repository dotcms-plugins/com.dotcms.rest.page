
# README
----
This plugin offers a custom REST endpoint that was the precursor to the layout as a service found here:
https://doc.dotcms.com/docs/latest/page-rest-api-layout-as-a-service-laas

## 1. PageResource

This resoruce will give you all the objects on an associated page (template, theme, containers) and optionally render them.

To call this method, send:

`http://localhost:8080/api/v0/page/json/{path-to-your-page}`

e.g.

`http://localhost:8080/api/page/v0/json/about-us/locations/index`


To render the page contents, send "render" instead of "json"  

`http://localhost:8080/api/page/v0/render/about-us/locations/index`



## How to build this example
----

To install all you need to do is build the JAR. To do this run from this directory:

`./gradlew jar`

or for windows

`.\gradlew.bat jar`

This will build a jar in the build/libs directory



## Authentication
----
This API supports the same REST auth infrastructure as other 
rest apis in dotcms. There are 4 ways to authenticate.

* user/xxx/password/yyy in the URI
* basic http/https authentication (base64 encoded)
* DOTAUTH header similar to basic auth and base64 encoded, e.g. setHeader("DOTAUTH", base64.encode("admin@dotcms.com:admin"))
* Session based (form based login) for frontend or backend logged in user

Curl Example:
`curl -u admin@dotcms.com:admin --head http://localhost:8080/api/page/json/index`



## Exports needed to get this to work
```
javax.management,
javax.servlet.resources,
com.dotcms.mock.response,
com.dotcms.repackage.javax.ws.rs,
com.dotcms.repackage.javax.ws.rs.core,
com.dotcms.repackage.javax.ws.rs.core.Response,
com.dotcms.rest,
com.dotcms.rest.annotation,
com.dotcms.rest.config,
com.dotmarketing.beans,
com.dotmarketing.business,
com.dotmarketing.business.web,
com.dotmarketing.exception,
com.dotmarketing.osgi,
com.dotmarketing.portlets.containers.business,
com.dotmarketing.portlets.containers.model,
com.dotmarketing.portlets.contentlet.business,
com.dotmarketing.portlets.contentlet.model,
com.dotmarketing.portlets.contentlet.util,
com.dotmarketing.portlets.htmlpageasset.business,
com.dotmarketing.portlets.htmlpageasset.model,
com.dotmarketing.portlets.languagesmanager.business,
com.dotmarketing.portlets.languagesmanager.model,
com.dotmarketing.portlets.structure.model,
com.dotmarketing.portlets.structure.model.ContentletRelationships,
com.dotmarketing.portlets.templates.business,
com.dotmarketing.portlets.templates.design.bean,
com.dotmarketing.portlets.templates.model,
com.dotmarketing.util,
com.dotmarketing.util.json,
com.dotmarketing.viewtools,
com.dotmarketing.viewtools.content.util,
com.fasterxml.jackson.annotation,
com.fasterxml.jackson.core,
com.fasterxml.jackson.databind,
com.liferay.portal.model,
javax.servlet;javax.servlet.http;version=3.1.0,
org.apache.velocity.context,
org.apache.velocity.exception,
org.apache.velocity.tools.view.context,
org.osgi.framework
```





