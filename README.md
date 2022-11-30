#### 실행
```bash
./build.sh
```

#### 마스터 DB / 테이블 생성 및 데이터 입력

```bash
docker exec mysql_master sh -c "export MYSQL_PWD=111; mysql -u root auth -e 'create table code(code int); insert into code values (100), (200)'"
```

#### 슬레이브 DB / 데이터 확인
```bash
docker exec mysql_slave sh -c "export MYSQL_PWD=111; mysql -u root auth -e 'select * from code \G'"
```

#### Run command inside "mysql_master"

```bash
docker exec mysql_master sh -c 'mysql -u root -p111 -e "SHOW MASTER STATUS \G"'
```

#### Run command inside "mysql_slave"

```bash
docker exec mysql_slave sh -c 'mysql -u root -p111 -e "SHOW SLAVE STATUS \G"'
```

#### Enter into "mysql_master"

```bash
docker exec -it mysql_master bash
```

#### Enter into "mysql_slave"

```bash
docker exec -it mysql_slave bash
```
