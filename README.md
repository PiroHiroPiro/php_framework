# PHP Framework

パーフェクトPHP第7章

## Requirement

- [docker](https://www.docker.com/)
  - docker-compose
- [MySQL](https://www.mysql.com/)

## Usage

Run server:

```console
$ docker-compose up
```

Go to `http://localhost:80` and you'll see the website.

## Install

Clone repository:

```console
$ git clone https://github.com/PiroHiroPiro/php_framework.git
$ cd php_framework
```

Copy MySQL configuration file:

```console
$ cp docker/mysql/.env.example docker/mysql/.env
$ [vim/emacs/nano or your favorite editor] docker/mysql/.env
```

Enter the database name and root user password in the copied configuration file `docker/mysql/.env`:

Create db user:

```console:
$ docker-compose up　-d
$ mysql -u root -p -h 127.0.0.1
mysql> GRANT ALL ON YOUR_DATABASE.* to NEW_USER IDENTIFIED BY 'NEW_USER_PASSWORD'
$ docker-compose down
```

## What you need to develop(Japanese only)
- Applicationクラス
    - ルートディレクトリの指定
    - アクションにあわせたルーティング定義
    - 接続するデータベースの指定(DbManagerクラスを操作)
    - ログインアクションの指定
- index.php
    - Applicationの呼び出しと実行
- Controllerクラス
    - 役割に合わせて子クラスの作成
    - 作成する画面にあわせたアクション定義，処理の実装
    - ログインが必要なアクションの指定
- DbRepositoryクラス
    - データベース上のテーブルごとに子クラスの作成
    - データベースアクセス処理の実装
- Viewファイル
    - アクションにあわせたHTMLの記述
    - レイアウトファイルの記述

## Author

[Hiroyuki Nishizawa](https://github.com/PiroHiroPiro)
