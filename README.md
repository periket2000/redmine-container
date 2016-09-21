# Dockerfile for building a redmine 3.3 image

Dockerfile for generating a redmine image that allows the user configure a SVN repository
with non trusted certificates.

With the original one, if you try to configure and connect to a self-signed certfificate 
SVN server, you can't.

## Usage

> 1. docker run --name redmine-db -v /your/host/persistent/db_directory:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=redmine -d mysql:5.5
> 2. docker run -d --name redmine -v /your/host/persistent/redmine_directory:/usr/src/redmine/files -p 3000:3000 --link redmine-db:mysql periket2000/redmine-container:latest

After that, you can connect to http://localhost:3000 and use Redmine
