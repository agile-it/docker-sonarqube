# Sonarqube
## Overview
based on [`library/sonarqube:5.1.1`](https://github.com/SonarSource/docker-sonarqube/blob/e7ac925f3ae123fa01daa30c5c79da66ed41983f/5.1.1/Dockerfile) with added plugins and correct fonts for jFreeChart rendering.

## Versions
* [`latest`, `1.1` *(1.1 Dockerfile)*](https://github.com/agile-it/docker-sonarqube/blob/master/Dockerfile)

## Usage

This image needs a postgres-container. You can use 

`docker run -d --name psql_sonar -e DB_NAME=sonar -p 12345:5432 agileit/postgres`

This starts a postgres which is also listening on the mapped port 12345 (needed for the sonarrunner etc.)

To start the sonarqube container use:

`docker run -d --link psql_sonar:db --name sonarqube -p 9000:9000 -e SONARQUBE_JDBC_URL=jdbc:postgresql://db/sonar agileit/sonarqube`
