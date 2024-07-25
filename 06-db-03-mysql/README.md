# Домашнее задание к занятию "`MySQL`" - `Кандала Кирилл`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1


1. `Решение задач приведено в поле для вставки кода`


```

#executing status
STATUS;
#result
--------------
mysql  Ver 8.0.21 for Linux on x86_64 (MySQL Community Server - GPL)

Connection id:		11
Current database:	
Current user:		root@localhost
SSL:			Not in use
Current pager:		stdout
Using outfile:		''
Using delimiter:	;
Server version:		8.0.21 MySQL Community Server - GPL
Protocol version:	10
Connection:		Localhost via UNIX socket
Server characterset:	utf8mb4
Db     characterset:	utf8mb4
Client characterset:	utf8mb4
Conn.  characterset:	utf8mb4
UNIQUE_CHECKS:		0
TEMPORARY       		false (OFF)
Skip database 	(false OFF)
Timeouts.commit   	χουνς ΓλŽε

#getting list of tables from the database
USE test_db;
SHOW TABLES;
SELECT COUNT(*) FROM orders WHERE price > 300;
#result
+----------+
| COUNT(*) |
+----------+
|        2 |
+----------+

```
---

### Задание 2

1. `Решение задач приведено в поле для вставки кода`

```

#getting data for user test from INFORMATION_SCHEMA.USER_ATTRIBUTES
SELECT * FROM INFORMATION_SCHEMA.USER_ATTRIBUTES WHERE USER = 'test';
#result
+------+-----------+-------------------------------+
| USER | HOST      | ATTRIBUTE                     |
+------+-----------+-------------------------------+
| test | %         | {"name": "James", "surname": "Pretty"} |
+------+-----------+-------------------------------+

```
---

### Задание 3

1. `Решение задач приведено в поле для вставки кода` 

```

#checking the table engine
SHOW TABLE STATUS LIKE 'orders';
#result
+-------+--------+---------+------------+------+----------------+-------------+---------------------+------------+-----------------+---------------------+----------------+---------------
| Name  | Engine | Version | Row_format | Rows | Avg_row_length | Data_length | Max_data_length | Index_length | Data_free |
+-------+--------+---------+------------+------+----------------+-------------+---------------------+------------+-----------------+---------------------+----------------+---------------
| orders| InnoDB |      10 | Dynamic    |    5 |          3276  |       16384 |  0                |       0    |              0  |
+-------+--------+---------+------------+------+----------------+-------------+---------------------+------------+-----------------+---------------------+----------------+---------------

#changing the engine to MyISAM
ALTER TABLE orders ENGINE = MyISAM;
SHOW PROFILES;
#result
Query_ID | Duration | Query
---------+----------+-------------------------------
1        | 0.025366 | ALTER TABLE orders ENGINE = MyISAM

#changing the engine to MyISAM
ALTER TABLE orders ENGINE = InnoDB;
SHOW PROFILES;
#result
Query_ID | Duration | Query
---------+----------+-------------------------------
2        | 0.027913 | ALTER TABLE orders ENGINE = InnoDB

```

### Задание 4

1. `Решение задач приведено в поле для вставки кода` 

```
Поле для вставки кода...
[mysqld]
# Basic InnoDB settings
innodb_flush_log_at_trx_commit = 0
innodb_file_per_table = 1
innodb_log_file_size = 100M
innodb_buffer_pool_size = 30G 

```

---

