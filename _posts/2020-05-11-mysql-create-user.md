---
title: "MySQL 계정 생성하기"
excerpt: "MySQL 계정생성 방법 & 패스워드 생성규칙"
toc: true
toc_sticky: true

categories:
 - MySQL
tags:
 - DB
 - MySQL
 - grant
 - revoke
 - database
 - user
 - password
---

# MySQL user 생성하기

## 1. root계정으로 login 

```shell
>mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2942
Server version: 5.7.30-0ubuntu0.16.04.1 (Ubuntu)

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
``` 
## 2. 데이터베이스 생성 
``` shell
mysql> create database new_db;
Query OK, 1 row affected (0.01 sec)
``` 

## 3. 사용자 계정 생성
>create user 'new_user'@'%' identified by '1234';  
이렇게 하면 에러난다. 비밀번호 정책을 만족하지 못한다고.  

```shell
mysql> create user 'new_user'@'%' identified by '1234';
ERROR 1819 (HY000): Your password does not satisfy the current policy requirements
```  

MySQL 비밀번호 정책은 아래와 같다.  
show variables like 'validate_password%';
명령어로 확인가능 
```shell
mysql> show variables like 'validate_password%';
+--------------------------------------+--------+
| Variable_name                        | Value  |
+--------------------------------------+--------+
| validate_password_check_user_name    | OFF    |
| validate_password_dictionary_file    |        |
| validate_password_length             | 8      |
| validate_password_mixed_case_count   | 1      |
| validate_password_number_count       | 1      |
| validate_password_policy             | MEDIUM |
| validate_password_special_char_count | 1      |
+--------------------------------------+--------+
7 rows in set (0.01 sec)
```
8자 이상, 대소문자 1개 이상씩, 숫자 1개이상, 특수문자 1개이상.


## 4. 사용자 계정 권한 부여 
>grant all privileges on 'db스키마'.'테이블' to '계정'@'접근권한' with grant option;   

grant all privileges on 'new_db'.'*' to 'new_user'@'%' with grant option; 
 -> 'new_db' 데이터베이스의 '모든' 테이블에 대한 권한을 'new_user' 에게 주고 '원격'접속 가능한 권한을 부여함.  


 grant all privileges on 'new_db'.'test' to 'new_user'@'localhost' with grant option; 
 -> 'new_db' 데이터베이스의 'test' 테이블에 대한 권한을 'new_user' 에게 주고 'localhost'접속 가능한 권한을 부여함. 

```shell
mysql> grant all privileges on 'new_db'.'*' to 'new_user'@'%' with grant option;
Query OK, 0 rows affected (0.00 sec)
```  


## 5. 사용자 계정 권한 확인
```shell
mysql> show grants for 'new_user';
+----------------------------------------------------------------------+
| Grants for oytrio@%                                                  |
+----------------------------------------------------------------------+
| GRANT USAGE ON *.* TO 'new_user'@'%' WITH GRANT OPTION                 |
| GRANT ALL PRIVILEGES ON `new_db`.* TO 'new_user'@'%' WITH GRANT OPTION |
+----------------------------------------------------------------------+
```  


## 6. 사용자 계정 권한 삭제
```shell
mysql> revoke all on 'new_db'.'*' from 'new_user'@'%';
Query OK, 0 rows affected (0.00 sec)
```  


## 7. 사용자 계정 삭제
```shell
mysql> drop user 'new_user'@'%';
Query OK, 0 rows affected (0.00 sec)
```  

## 8. 데이터베이스 삭제
```shell
mysql> drop database new_db;
Query OK, 0 rows affected (0.00 sec)
```