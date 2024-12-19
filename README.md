---

# Проект по созданию сервера баз данных

Сервер баз данных на ClickHouse создаётся с использованием Docker Compose, а подключение к нему осуществляется через DBeaver для создания баз данных.

## Пример запросов через DBeaver

Для создания баз данных, ролей и пользователей, а также назначения прав доступа, используются следующие запросы:

CREATE DATABASE IF NOT EXISTS test_12;

CREATE DATABASE IF NOT EXISTS main_12;

CREATE ROLE IF NOT EXISTS reader;

CREATE ROLE IF NOT EXISTS writer;

GRANT READ ON DATABASE main_12 TO role reader;

GRANT WRITE ON DATABASE main_12 TO role writer;

CREATE USER IF NOT EXISTS 'luser_1'@'localhost' IDENTIFIED BY '12345678';

CREATE USER IF NOT EXISTS 'some'@'localhost' IDENTIFIED BY '12345678';

GRANT reader TO 'luser_1'@'localhost';

GRANT writer TO 'luser_1'@'localhost';



Обратите внимание, что эти запросы выполняются в контексте ClickHouse, где управление доступом и создание пользователей реализовано иначе, чем в других системах управления базами данных.

---
