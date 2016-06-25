# GORM

Grails Object Relational Mapping (GORM) provides easy way to define your database model and it comes for free with Grails.

The place you need to configure to get GORM up and running is `application.yml`. Grails will create bean `dataSource` based on what we set in `application.yml`. That bean is used for CRUD operations when we work with our database.

> If you want to provide external configuration file, for example you deploy application to several production environments, you can define [external config](http://grails.org/doc/latest/guide/conf.html#configExternalized) and set the database configuration there.
