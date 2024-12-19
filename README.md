#Проект по созданию сервера базданных.

##Сервер базданных на clickhouse создается с помощью docker-comppose, а через dbeaver  подключаемся к нему и создаем БД.

#Пример запросов через dbeaver:
CREATE DATABASE IF NOT EXISTS test_12;
CREATE DATABASE IF NOT EXISTS main_12;
CREATE ROLE IF NOT EXISTS reader;
CREATE ROLE IF NOT EXISTS writer;
GRANT READ ON DATABASE main_1 TO role reader;
GRANT WRITE ON DATABASE main_1 TO role writer;
CREATE USER IF NOT EXISTS 'luser_1'@'localhost' IDENTIFIED BY '12345678';
CREATE USER IF NOT EXISTS 'some'@'localhost' IDENTIFIED BY '12345678';
GRANT reader TO 'luser_1'@'localhost';
GRANT writer TO 'luser_1'@'localhost';
