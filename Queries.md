### 1. Create a DATABASE - *create database startsql;*
---
### 2. Set as Default Schema - *use startsql;*
---
### 3. Create a Table - 
create table users (

    id int auto_increment primary key,
    name varchar(100) not null,
    email varchar(100) unique not null,
    gender enum('male', 'female', 'other'),
    date_of_birth date,
    created_at timestamp default current_timestamp
);
---
### SELECT - *select *from users*
---
### Drop the Database - *drop database startsql;*