# Command line

> Source code for this tutorial is available on [github.com/vaadin-on-grails-3/hello-world](https://github.com/vaadin-on-grails-3/hello-world).

Using [Grails command line](http://grails.org/doc/latest/guide/single.html#commandLine) to create a new application is probably the most reliable way. We can basically say that if you are not able to create project using the command line, you will be not able to work with Grails at all and you need to re-install Grails or fix its configuration.

## Create application

Follow these steps and run the commands in your terminal.

#### Step 1

Open your console or terminal and run `grails create-app hello-world` that will create new directory called **my-app** with sample Grails application.

#### Step 2

Go to that directory `cd hello-world` and open that folder in a text editor of your choice.

#### Step 3

Open `build.gradle` and add latest version of [vaadin](http://grails.org/plugin/vaadin) plugin into compile scope `compile ":vaadin:7.6.1"`.

```groovy
buildscript {
    ext {
        grailsVersion = project.grailsVersion
    }
    repositories {
        mavenLocal()
        maven { url "https://repo.grails.org/grails/core" }
        maven { url 'https://dl.bintray.com/ondrej-kvasnovsky/plugins/' }
    }
    dependencies {
        classpath 'com.vaadinongrails:vaadin-gradle-plugin:1.0.5'
        // ... 
    }
}
```

```
apply plugin: 'com.vaadinongrails.vaadin-gradle-plugin'
```

```groovy
repositories {
    mavenLocal()
    maven { url "https://repo.grails.org/grails/core" }
    maven { url 'https://dl.bintray.com/ondrej-kvasnovsky/plugins' }
}
```

```groovy
dependencies {
    compile 'com.vaadinongrails:grails-vaadin-plugin:1.0.5'
    // ....
}
```

![BuildConfig.groovy](http://vaadinongrails.com/book/1_1_build_config.png)

#### Step 4

Now we need to run `grails vaadin-quickstart`, so Vaadin plugin can generate sample application for us.

![Generated Vaadin sample code](http://vaadinongrails.com/book/1_1_vaadin_sample_app.png)

#### Step 5

We want to prevent Grails to take over URL mapping. Open `UrlMappings.groovy` and make sure the URL mapping is empty.

```java
    class UrlMappings {
        static mappings = {
        }
}
```

#### Step 6

We are ready to start up the application. Run grails run-app command. Vaadin application running on [http://localhost:8080/my-app](http://localhost:8080/my-app) will become accessible after a while.  
  ![Generated Vaadin sample code](http://vaadinongrails.com/book/1_1_run_app.png)

