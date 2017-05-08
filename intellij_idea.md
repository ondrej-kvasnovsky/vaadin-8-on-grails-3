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

> The latest version of the plugin is always available on [https://bintray.com/ondrej-kvasnovsky/plugins](https://bintray.com/ondrej-kvasnovsky/plugins).

![](/assets/idea-4.png)

### Step 5

Now we have all dependencies available and we can run `vaadin-quick-start` Gradle target to create mandatory files. `vaadin-quickstart` command creates `MyUI.groovy`, `VaadinConfig.groovy` and removes URL mapping inside `UrlMapping.groovy`.

![](/assets/idea-5.png)

### Step 6

Now we are able to run our application.

![Run application](/assets/idea-7.png)

Here is how Grails run configuration looks like, in case we need to create it for our project. 

![](/assets/idea-8.png)

When the application is successfully started, we should see this UI in the browser. 

![](/assets/idea-10.png)

### Step 7

In this step, we are going to do change in our Vaadin code and we will observe how changes are reflected in UI without server restart. 

First we need to enable `auto recompile` in IDEA. Open IDEA settings and check on `Build project automatically` box. 

![](/assets/idea-6.png)



### Step 8

We are ready to run the application. Click on the little green triangle in toolbar.

![Compile app](http://vaadinongrails.com/img/run-app-idea.png)

> You can also press `Alt+Cmd+G` on Mac OS or `Ctrl+Alt+G` on Windows and type `run-app` in order to run the application.

### Step 9

Run the application again and a Vaadin application with a single Home label will be available on [http://localhost:8080/ria-app](http://localhost:8080/ria-app) in your browser.

![Running app](http://vaadinongrails.com/img/first-run.png)

