Project - Containerizing mysql database

You need to have sql exports file included in the project with file name as 'init.sql'

Steps :::

- to build image
    docker build -t my-mysql-image .

- to run the container from the image
    docker run --name my_mysql_container -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=whiteboxqa -p 3306:3306 -d my-mysql-image

- to verify if the tables and data has been imported correctly or not
    docker exec -it my_mysql_container mysql -u root -p
      # Enter the password `root` when prompted
This will connect to mysql server and mysql> is visible to run sql commands.

- Then check the databases and tables
    show databases;
    use database;
    show tables;
  and so on..
