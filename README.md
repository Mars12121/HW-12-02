# Домашнее задание к занятию "Работа с данными (DDL/DML)" - Морозов Александр

---

Задание можно выполнить как в любом IDE, так и в командной строке.

### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp. 

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

![alt text](https://github.com/Mars12121/hw-12-02/blob/main/img/1.png)

1.4. Дайте все права для пользователя sys_temp. 

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

![alt text](https://github.com/Mars12121/hw-12-02/blob/main/img/2.png)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

![alt text](https://github.com/Mars12121/hw-12-02/blob/main/img/3.png)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*

Используемы запросы:
```
CREATE DATABASE `netology`;

SELECT user FROM mysql.user;

GRANT ALL PRIVILEGES ON *.* TO 'sys_temp';

SHOW GRANTS FOR 'sys_temp';

ALTER USER 'sys_test' IDENTIFIED WITH mysql_native_password BY 'password';

SELECT user();

mysql -h 127.0.0.1 -u sys_temp -p netology < sakila-db/sakila-schema.sql
mysql -h 127.0.0.1 -u sys_temp -p netology < sakila-db/sakila-data.sql  

USE sakila;

SHOW TABLES;
```

### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы | Название первичного ключа
customer         | customer_id
```

Ответ:
```
Название таблицы            | Название первичного ключа
actor                       | actor_id
actor_info                  |
address                     | address_id
category                    | category_id
city                        | city_id
country                     | country_id
customer                    | customer_id
customer_list               |
film                        | film_id
film_actor                  | actor_id, film_id
film_category               | film_id, category_id
film_list                   | 
film_text                   |
inventory                   | inventory_id
language                    | language_id
nicer_but_slower_film_list  | 
payment                     | payment_id
rental                      | rental_id
sales_by_film_category      | 
sales_by_store              |
staff                       | staff_id
staff_list                  | 
store                       | store_id
```

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 3*
3.1. Уберите у пользователя sys_temp права на внесение, изменение и удаление данных из базы sakila.

3.2. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*