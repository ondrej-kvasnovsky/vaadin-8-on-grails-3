# Project setup

You are going to learn how to create and configure Grails application with Vaadin plugin in this chapter.

There are two libraries that add support for development of Vaadin applications for Grails. 

 - ```com.vaadinongrails:grails-vaadin-plugin``` adds all required jars on classpath and makes it possible to run Vaadin application instead of Grails .gsp files.
 - ```com.vaadinongrails:vaadin-gradle-plugin``` provides support for development of Vaadin applications. This plugin adds new tasks:
   -  ```vaadin-quickstart``` generates boilerplate Vaadin project
   -  ```vaadin-spring-quickstart``` generates boilerplate Vaadin project with Spring support
   -  ```vaadin-compile-sass``` compiles SASS into CSS
   -  ```vaadin-compile-widgetset``` compiles Widgetset