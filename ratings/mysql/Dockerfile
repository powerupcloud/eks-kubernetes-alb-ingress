FROM mysql
ADD mysqldb-init.sql /docker-entrypoint-initdb.d/
ENV MYSQL_ROOT_PASSWORD="powercloud123"
CMD ["mysqld"]
