Docker APSL tomcat app server
================================

Tomcat / Java app server

Usage
-----

Mount your java app on /app, or inherit from your Dockerfile and ADD /app

::

    docker run -e MANAGER_USER=admin -e MANAGER_PASSWORD=1234 -v /workspace/my_app:/app -p 8080:8080 apsl/tomcat6


Description
-----------

* Parent: apsl/java. 
* Based on apsl/circusbase https://registry.hub.docker.com/u/apsl/circusbase/
  * circus for process management
  * envtpl for variables
* Tomcat configurable from env vars (with envtpl)
* Tomcat process managed by circus http://circus.readthedocs.org 
 
Env vars: 
---------

Tomcat manager user / passwd::

    -e MANAGER_USER=admin
    -e MANAGER_PASSWORD=yourpasswd

JAVA_OPTS::

    -e JAVA_OPTS=-Xms=512m

TIMEOUT::

    -e TOMCAT_CONNECTION_TIMEOUT=20000

And other options from apsl/circusbase: https://registry.hub.docker.com/u/apsl/circusbase/

Versions
--------

* Legacy tomcat5 with oracle/java5
* Tomcat6 / Oracle Java6
* Tomcat7/ Oracle Java7
