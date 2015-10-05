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

## Example using Docker
Tested with Docker 1.8, SonarQube server 5.1 and Gradle 2.3.  This setup is **NOT** recommened for public / production use.

* Install and Start Docker
* Pull the SonarQube image:  `docker pull sonarqube`
* Start the SonarQube server:  `docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube`
* Setup OpenLMIS's `gradle.properties` with:
 
  ```
  sonarServer = http://localhost:9000
  sonarJdbc = jdbc:h2:tcp://localhost/sonar
  sonarProject = OpenLMIS
  sonarProjectVersion = 2.0
  ```
 
  Where `localhost` is the IP address (note with Boot2Docker you may need to run `boot2docker ip` to get this address) or the docker image.
* Navigate to the analysis at: [http://localhost:9000](http://localhost:9000)


## Todo
* add URL to public sonar server
* somehow document which rulesets are in use for CheckStyle, Java, etc
