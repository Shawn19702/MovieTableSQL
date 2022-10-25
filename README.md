mysql> describe movies;
+----------+--------------+------+-----+---------+----------------+
| Field    | Type         | Null | Key | Default | Extra          |
+----------+--------------+------+-----+---------+----------------+
| id       | int unsigned | NO   | PRI | NULL    | auto_increment |
| title    | varchar(20)  | NO   |     |         |                |
| genre    | varchar(100) | NO   |     |         |                |
| duration | int unsigned | NO   |     | 0       |                |
+----------+--------------+------+-----+---------+----------------+
4 rows in set (0.04 sec)

mysql> insert into movies(title, genre, duration)
    -> values('Metropolis', 'Sci-Fi', 153);
Query OK, 1 row affected (0.05 sec)

mysql> select * from movies;
+----+------------+--------+----------+
| id | title      | genre  | duration |
+----+------------+--------+----------+
|  1 | Metropolis | Sci-Fi |      153 |
+----+------------+--------+----------+
1 row in set (0.00 sec)

mysql> insert into movies (title,genre,duration) values('Noseferatu', 'Horror', 94);
Query OK, 1 row affected (0.00 sec)

mysql> select * from movies;
+----+------------+--------+----------+
| id | title      | genre  | duration |
+----+------------+--------+----------+
|  1 | Metropolis | Sci-Fi |      153 |
|  2 | Noseferatu | Horror |       94 |
+----+------------+--------+----------+
2 rows in set (0.00 sec)

mysql> insert into movies (title,genre,duration) values('The Kid', 'Comedy', 68);
Query OK, 1 row affected (0.00 sec)

mysql> insert into movies (titles,genre,duration) values('The Gold Rush', 'Adventure', 95);
ERROR 1054 (42S22): Unknown column 'titles' in 'field list'
mysql> insert into movies (title,genre,duration) values('The Gold Rush', 'Adventure', 95);
Query OK, 1 row affected (0.00 sec)

mysql> select * from movies;
+----+---------------+-----------+----------+
| id | title         | genre     | duration |
+----+---------------+-----------+----------+
|  1 | Metropolis    | Sci-Fi    |      153 |
|  2 | Noseferatu    | Horror    |       94 |
|  3 | The Kid       | Comedy    |       68 |
|  4 | The Gold Rush | Adventure |       95 |
+----+---------------+-----------+----------+
4 rows in set (0.00 sec)
