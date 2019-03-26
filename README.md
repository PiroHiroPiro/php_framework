# PHP Framework
パーフェクトPHP第7章

## Setup
1. MySQLの設定ファイルをコピーし編集する
```
$ cp docker/mysql/.env_db.example docker/mysql/.env_db
$ [vim/emacs/nano or your favorite editor] docker/mysql/.env_db
```

2. コンテナ起動
```
$ docker-compose up　-d
```

3. MySQLでユーザ作成する
```
$ mysql -u root -p -h 127.0.0.1
mysql> GRANT ALL ON YOUR_DATABASE.* to NEW_USER IDENTIFIED BY 'NEW_USER_PASSWORD'
```

4. コンテナ終了
```
$ docker-compose down
```

## Run
```
$ docker-compose up
```

## Connect to MySQL
```
$ mysql -u NEW_USER -p -h 127.0.0.1
```

## Connect to bash
```
$ docker ps
$ docker exec -it [CONTAINER ID] /bin/bash
```
