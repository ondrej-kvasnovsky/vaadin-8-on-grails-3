# Project setup

You are going to learn how to create and configure Grails application with Vaadin plugin in this chapter.

There are two libraries that add support for development of Vaadin applications in Grails. 

 - ```com.vaadinongrails:grails-vaadin-plugin``` adds all required jars on classpath and makes it possible to run Vaadin application instead of Grails .gsp files.
 - ```com.vaadinongrails:vaadin-gradle-plugin``` provides support for development of Vaadin applications. This plugin adds new tasks:
   -  ```vaadin-quickstart``` generates boilerplate Vaadin project
   -  ```vaadin-spring-quickstart``` generates boilerplate Vaadin project with Spring support
   -  ```vaadin-compile-sass``` compiles SASS into CSS
   -  ```vaadin-compile-widgetset``` compiles Widgetset

### Before you start

Before you start, make sure you have Java installed on your machine. If not, follow the [instructions by Oracle](how to install java, oracle) for macOS, Linux or Windows.

Also make sure you have got the latest version of Grails on your local machine. Type `grails --version` in your console to find out what version is installed. You should see something like this: 

```
| Grails Version: 3.1.7
| Groovy Version: 2.4.6
| JVM Version: 1.8.0_60
```

In case you do not have Grails installed on your machine, follow the instructions in the next sections. 

## Unix based systems

This section describes hot to install Grails on Mac OS X and Linux. You will use [SdkMan](http://sdkman.io/usage.html) to install all the requited tools. 

### Step 1

Install SdkMan with this command in your console: ```curl -s "https://get.sdkman.io" | bash```.

If you face to any kind of issues, open [http://sdkman.io/install.html](http://sdkman.io/install.html) and follow instructions to install SdkMan.

### Step 2

Install the following tools: 
 - Gradle ```sdk install gradle```
 - Grails ```sdk install grails```


## Windows

In case you run into troubles, follow this tutorial on the following web page: [Setup Grails 3 Windows Development Environment](http://grails.asia/grails-3-tutorial-setup-your-windows-development-environment).

Now you can proceed to other 