# sonar-configuration
Standard steps for setting up a SonarQube server for analyzing OpenLMIS sources.

## Server

Either
* Install a SonarQube server from [SonarQube.org](http://www.sonarqube.org/)
* Install a Docker image from the [Docker Hub repository](https://hub.docker.com/_/sonarqube/)
 

## Plugins
Install the following plugins:
* Checkstyle 2.3
* Cobertura 1.6
* CSS 1.5
* Java 3.5
* JavaScript 2.8
* Git 1.1


## Todo
* add URL to public sonar server
* somehow document which rulesets are in use for CheckStyle, Java, etc
