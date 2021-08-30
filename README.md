# cities-api-project
API Rest de consulta de cidades do Brasil com dados comparativos.
Cities API
Requirements

    Linux
    Git
    Java 8
    Docker
    IntelliJ Community
    Heroku CLI
    Travis CLI

DataBase
Postgres

    Postgres Docker Hub

docker run --name cities-db -d -p 5432:5432 -e POSTGRES_USER=postgres_user_city -e POSTGRES_PASSWORD=super_password -e POSTGRES_DB=cities postgres

    Postgres Earth distance
    earthdistance--1.0--1.1.sql
    OPERATOR <@>
    postgrescheatsheet
    datatype-geometric

Access

docker exec -it cities-db /bin/bash

psql -U postgres_user_city cities

Query Earth Distance

Point

select ((select lat_lon from cidade where id = 4929) <@> (select lat_lon from cidade where id=5254)) as distance;

Cube

select earth_distance(
    ll_to_earth(-21.95840072631836,-47.98820114135742), 
    ll_to_earth(-22.01740074157715,-47.88600158691406)
) as distance;

Spring Boot

    https://start.spring.io/

    Java 8
    Gradle Project
    Jar
    Spring Web
    Spring Data JPA
    PostgreSQL Driver

Spring Data

    jpa.query-methods

Properties

    appendix-application-properties
    jdbc-database-connectio

Types

    JsonTypes
    UserType

Heroku

    DevCenter

heroku create dio-cities-api --addons=heroku-postgresql

Code Quality
PMD

    https://pmd.github.io/pmd-6.8.0/index.html

Checkstyle

    https://checkstyle.org/

    https://checkstyle.org/google_style.html

    http://google.github.io/styleguide/javaguide.html

wget https://raw.githubusercontent.com/checkstyle/checkstyle/master/src/main/resources/google_checks.xml

InMemory Database Testing

    http://www.h2database.com/html/features.html

Migrations

    https://flywaydb.org/

CI
Travis

    https://github.com/travis-ci/travis.rb#readme

    https://docs.travis-ci.com/user/tutorial/

extra

    https://docs.travis-ci.com/user/conditional-builds-stages-jobs/

    https://docs.travis-ci.com/user/deployment-v2/conditional

    Heroku Deployment
