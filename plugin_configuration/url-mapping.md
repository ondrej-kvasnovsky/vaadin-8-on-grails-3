### Mapping

We can provide multiple Vaadin UI classes that extends `com.vaadin.ui.UI` and they will be mapped to specified URL patterns. There must be at least one UI class.

Let's look at this example where we map three URL paters, each to separate UI class.

``` java
    mapping = [
        "/*": "app.MyUI",
        "/admin/*": "app.AdminUI",
        "/client/*": "app.ClientUI"
    ]
```

The application UIs will then become available at:
* http://localhost:8080/grails-vaadin7-demo
* http://localhost:8080/grails-vaadin7-demo/client
* http://localhost:8080/grails-vaadin7-demo/admin

> Be aware, creating multiple UIs is not the way how to navigate in the Vaadin applicatin. Use [views navigator](https://vaadin.com/book/-/page/application.architecture.html#application.architecture.navigation) for this.


