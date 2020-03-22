> To install maraiabd server in the Ec2 instance

```
yum install mariadb-server
```

> To allow ports for the maraiadb service in the security grop

```
Type            protocol port range     Source

Mysql	           TCP	 3306            0.0.0.0/0
```


> To start the maraidb service
```
systemctl start mariadb
```

> To create a new database
```
MariaDB [(none)]> create database testdb;
Query OK, 0 rows affected (0.00 sec)
```

> To create a new mysql user
```
MariaDB [(none)]> create user 'newuser'@'localhost'identified by 'passwd';
Query OK, 0 rows affected (0.00 sec)
```

> To assign privileges to the user in the new database
```
MariaDB [(none)]> grant all privileges on testdb.* TO 'newuser'@'localhost';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> flush privileges;
Query OK, 0 rows affected (0.00 sec)
```

> To show the priveleges of a mysql user
```
MariaDB [(none)]> show grants for 'newuser'@'localhost';
```

> To list all mysql users
```
MariaDB [(none)]> select user from mysql.user;
+---------+
| user    |
+---------+
| root    |
| root    |
|         |
| root    |
|         |
| newuser |
| root    |
+---------+
7 rows in set (0.00 sec)
```
> To show the user, host and password fields
```
MariaDB [(none)]> select user,host,password from mysql.user;
+---------+----------------------------------------------+-------------------------------------------+
| user    | host                                         | password                                  |
+---------+----------------------------------------------+-------------------------------------------+
| root    | localhost                                    |                                           |
| root    | ip-172-31-35-186.ap-south-1.compute.internal |                                           |
| root    | 127.0.0.1                                    |                                           |
| root    | ::1                                          |                                           |
|         | localhost                                    |                                           |
|         | ip-172-31-35-186.ap-south-1.compute.internal |                                           |
| newuser | localhost                                    | *59C70DA2F3E3A5BDF46B68F5C8B8F25762BCCEF0 |
+---------+----------------------------------------------+-------------------------------------------+
```
	
