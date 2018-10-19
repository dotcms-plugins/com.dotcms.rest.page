
# Page as a Service
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
