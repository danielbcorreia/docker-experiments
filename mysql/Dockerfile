FROM mysql/mysql-server:latest

# ROOT PASSWORD
# to secure your installation, you should avoid MYSQL_ROOT_PASSWORD and 
# instead set MYSQL_RANDOM_ROOT_PASSWORD and MYSQL_ONETIME_PASSWORD to yes

ENV MYSQL_ROOT_PASSWORD=secret
#ENV MYSQL_RANDOM_ROOT_PASSWORD=yes
#ENV MYSQL_ONETIME_PASSWORD=yes

# NEW USER AND DATABASE
# you can specify the name of a database to be created during initialization.
# if you specify also an username and password, the mysql user will be created 
# with full control over that database.

ENV MYSQL_DATABASE=sample-database
#ENV MYSQL_USER=sample-username
#ENV MYSQL_PASSWORD=sample-password

# SERVER DEFAULT CHARSET AND COLLATION

RUN sed -i "/default-character-set/d" /etc/my.cnf
RUN sed -i "/\[mysqld]/a skip-character-set-client-handshake" /etc/my.cnf
RUN sed -i "/\[mysqld]/a collation-server=utf8mb4_general_ci" /etc/my.cnf
RUN sed -i "/\[mysqld]/a character-set-server=utf8mb4" /etc/my.cnf
RUN sed -i "/\[mysqld]/a init_connect= 'SET NAMES utf8mb4' " /etc/my.cnf
RUN sed -i "/\[mysqld]/a init_connect=‘SET collation_connection = utf8mb4_general_ci' " /etc/my.cnf

EXPOSE 3306