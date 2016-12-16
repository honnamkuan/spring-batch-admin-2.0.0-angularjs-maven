## Spring Batch Admin - AngularJS

AngularJS is a popular javascript MVC framework developed by Google.  This sample 
application demonstrates a sample UI developed using AngularJS consuming Spring Batch 
Admin's REST endpoints.
 
### Dependencies

This project requires the following to be built:

* Java 7 or higher

### Configuration

This sample app contains two configuration files, all residing in `src/main/resources`:

**application.properties**  
This is the standard Spring Boot configuration file used to specify environment specific values.

**batch-*.properties**  
This file is used to configure your database.  The * is replaced with whatever the database type you're using.  This should match the value of the `ENVIRONMENT` property in the `application.properties` file.  This project comes with an HSQLDB preconfigured.

### Build and lauch application

To build this project, is a two step process:

**Build the client**  
The first time you build the front end, you'll need to install the dependencies.  To do 
that:

1. Activate Maven Profile 'buildUI'
2. Perform a Maven Compile (Will take sometimes for first compile)

The result of this will place all the compiled client static resources into `src/main/resources/public`.

**Launching the Spring Boot application**
Once the client has been built, you can compile and start up the application using **spring-boot:run** plugin goal.

### Sample jobs
There are two sample jobs provided in this example.  One is XML based and can be found in `src/main/resources/META-INF/spring/batch/jobs`.  The other is a Java config based job.  The Java configured job (`job`), takes an optional parameter `fail` to indicate if it should fail or not.

### Development Profile
The front end for this project was generated using [Yeoman](http://yeoman.io) and uses the [Grunt](http://gruntjs.com) build system.  The development profile provides the ability to iterate on the front end independently of the back end.  To do so:

* Run the Spring Boot based app using your method of choice (`java -jar`, IDE, etc) with the `spring.profiles.active=development` configured in the `application.properties`.
* From the client directory, run `$ grunt serve`.  This will launch a separate server on port 9000 that will serve the static resources.  It includes functionality like automatic reloading of the page in the browser as changes are made, etc.

The development profile makes this dual server configuration possible via the CORSFilter.  It is disabled by default and should not be run in a production environment.

Screenshots:
![d877e5cd20a0fe8e26641a882800d82b.png](https://pictr.com/images/2016/12/17/d877e5cd20a0fe8e26641a882800d82b.png)

![6c385cff74835c5295b29e60b009d6be.png](https://pictr.com/images/2016/12/17/6c385cff74835c5295b29e60b009d6be.png)

![db2f0b7c683c1fa025736a8c40f3419b.png](https://pictr.com/images/2016/12/17/db2f0b7c683c1fa025736a8c40f3419b.png)


