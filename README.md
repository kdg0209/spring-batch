

### Docker Mysql Container 생성 및 접속

- 나는 로컬에 설치된 MySQL도 사용하고 있기 때문에 mysql docker container 포트를 3306으로 설정시 충돌이 발생하므로 3307로 설정하고, 내부 3306 포트와 연결했다.

```text
> docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=1234567890 -p 3307:3306 mysql:8.0.30
> docker exec -it mysql-container bin/bash
> mysql -u root -p [1234567890]
> CREATE DATABASE spring_batch CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
> CREATE USER 'tester' IDENTIFIED BY '1234567890';
> GRANT ALL PRIVILEGES ON spring_batch.* TO 'tester';
> FLUSH PRIVILEGES;
```




