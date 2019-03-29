# PHP Framework
パーフェクトPHP第7章

## セットアップ
1. MySQLの設定ファイルをコピーし編集する
```
$ cp docker/mysql/.env.example docker/mysql/.env
$ [vim/emacs/nano or your favorite editor] docker/mysql/.env
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

## サーバ起動
```
$ docker-compose up
```

## MySQLへの接続
```
$ mysql -u NEW_USER -p -h 127.0.0.1
```

## 開発内容
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
