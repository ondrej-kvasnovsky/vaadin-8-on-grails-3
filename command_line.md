# Command line

> Source code for this tutorial is available on [github.com/vaadin-on-grails-3/hello-world-cmd](https://github.com/vaadin-on-grails-3/hello-world-cmd).

Using [Grails command line](http://grails.org/doc/latest/guide/single.html#commandLine) to create a new application is probably the most reliable way. We can basically say that if you are not able to create project using the command line, you will be not able to work with Grails at all and you need to re-install Grails or fix its configuration.

## Create application

Follow these steps and run the commands in your terminal.

#### Step 1

Open your console or terminal and run `grails create-app hello-world` that will create new directory called `hello-world` with a sample Grails application.

#### Step 2

Go to that directory `cd hello-world` and open that folder in a text editor of your choice.

#### Step 3

Open `build.gradle` and add latest version of [vaadin plugin](https://bintray.com/ondrej-kvasnovsky/plugins).

```groovy
buildscript {
    repositories {
        //...
        maven { url 'https://dl.bintray.com/ondrej-kvasnovsky/plugins/' }
    }
    dependencies {
        classpath 'com.vaadinongrails:vaadin-gradle-plugin:2.0.2'
        // ... 
    }
}
```

Then apply `com.vaadinongrails.vaadin-gradle-plugin` \(in section where other plugins are applied\).

```
apply plugin: 'com.vaadinongrails.vaadin-gradle-plugin'
```

Now we need to add repository for `grails-vaadin-plugin`.

```groovy
repositories {
    // ...
    maven { url 'https://dl.bintray.com/ondrej-kvasnovsky/plugins' }
}
```

Now we can add dependency to `grails-vaadin-plugin`. Do not forget to exclude `vaadin-client-compiler` because then we won't be able to start up the application because of library version collision.

```groovy
dependencies {
    compile ('com.vaadinongrails:grails-vaadin-plugin:2.0.3') {
        exclude group: 'com.vaadin', module: 'vaadin-client-compiler'
    }
}
```

#### Step 4

We can create all the files manually or we can use `gradle vaadin-quickstart` command. That command generates sample application for us and that is what we are going to use in this tutorial.

![Generated Vaadin files](/assets/cmd-files.png)

#### Step 5

We need to prevent Grails to take over URL mapping. Open `UrlMappings.groovy` and make sure the URL mapping is empty.

```java
class UrlMappings {
    static mappings = {
    }
}
```

#### Step 6

We are ready to start up the application. Run `grails run-app` command. Vaadin application running on [http://localhost:8080](http://localhost:8080) will become accessible in couple of seconds.

![Generated Vaadin sample code](/assets/idea-10.png)

Here is how output in the console should look like.

```
> grails run-app
| Running application...
Grails application running at http://localhost:8080 in environment: development
```



