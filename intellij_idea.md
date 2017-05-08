# IntelliJ IDEA

> Source code for this tutorial is available on [github.com/vaadin-on-grails-3/hello-world](https://github.com/vaadin-on-grails-3/hello-world).

Grails support in [IntelliJ IDEA](http://www.jetbrains.com/idea) is added through [Grails plugin](http://www.jetbrains.com/idea/webhelp/grails.html). Make sure it is installed in your IntelliJ IDEA before you start with the tutorial.

### Step 1

Create new project from IDEA menu. Click on  `New..` item in the menu and then on `Project...`.

![](/assets/idea-1.0.png)

### Step 2

If it is your first Grails project in IDEA, click on `...` next to Grails SDK Home and provide path to your Grails folder. It will add Grails into IDEA. When you are done, click on `Next`.

![](/assets/idea-2.png)

### Step 3

Fill in the name of the project and where the project should be created. Then click on `Finish` button.

![](/assets/idea-3.png)

> Warning: sometimes, IDEA is not able to create Grails project and you end up with weird errors. In that case, try to upgrade IDEA version or run`grails create-app my-app`  in console. Then open the project in IDEA and follow the next steps.
>
> It takes more time to create new project first time.

### Step 4

When IDEA opens the newly created project, find and open build.gradle file. We need to add build and project dependencies to get the integration with Vaadin working.

Copy paste these lines into buildscript section. Check the print screen for places where to put these lines.

```
maven { url 'https://dl.bintray.com/ondrej-kvasnovsky/plugins/' }

classpath 'com.vaadinongrails:vaadin-gradle-plugin:2.0.0'

apply plugin: 'com.vaadinongrails.vaadin-gradle-plugin'
```

Then add these two lines into project dependency section:

```
maven { url 'https://dl.bintray.com/ondrej-kvasnovsky/plugins' }

compile ('com.vaadinongrails:grails-vaadin-plugin:2.0.0') {
    exclude group: 'com.vaadin', module: 'vaadin-client-compiler'
}
```

> The latest version of the plugin is always available on [http://grails.org/plugin/vaadin](http://grails.org/plugin/vaadin)

![](/assets/idea-4.png)

### Step 5

Now we have all dependencies available and we can run `vaadin-quick-start` Gradle target to create mandatory files.

![](/assets/idea-5.png)

### Step 6

Run `grails vaadin-quickstart` that will generate sample code to easier project configuration.

![Vaadin plugin](http://vaadinongrails.com/book/1_1_2_quickstart.png)

The command `vaadin-quickstart` will generate `MyUI.groovy` and remove URL mapping inside `UrlMapping.groovy`.

##### Optional

We have to disable Grails to take control over the URLs, so Vaadin can do it instead. Open `UrlMappings.groovy` file and make sure the URL mapping is empty, so the content of the file is the following.

```java
class UrlMappings {
    static mappings = {
    }
}
```

> If you see `unable to resolve class com.vaadin.grails.VaadinConfiguration` error during compile, compile the project once more. There an issue with Grails together with IntelliJ IDEA and it is not possible to compile the project in the first run. Note that everything will work properly and you can ingnore that error.

### Step 8

We are ready to run the application. Click on the little green triangle in toolbar.

![Compile app](http://vaadinongrails.com/img/run-app-idea.png)

> You can also press `Alt+Cmd+G` on Mac OS or `Ctrl+Alt+G` on Windows and type `run-app` in order to run the application.

### Step 9

Run the application again and a Vaadin application with a single Home label will be available on [http://localhost:8080/ria-app](http://localhost:8080/ria-app) in your browser.

![Running app](http://vaadinongrails.com/img/first-run.png)

