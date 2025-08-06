# データベースの学習をする環境を揃えましょう 
- 【Windowsの方】[WSLインストール](https://respawn.littleheroes.jp/w/courses/2285/2351/2352/1284?lhsct=content-1284)、[Gitで作業を始める準備](https://respawn.littleheroes.jp/w/courses/2285/2351/2353/1286?lhsct=content-1286)、[GitHubとSSH接続](https://respawn.littleheroes.jp/w/courses/2285/2351/2353/1287?lhsct=content-1287)、[Dockerの設定](https://respawn.littleheroes.jp/w/courses/2285/2351/2354/1288?lhsct=content-1288)を終えていること。
- 【Macの方】は[Docker Desktop for Macのインストール](https://respawn.littleheroes.jp/w/courses/596/1357/1380/797?lhsct=content-797)、[Gitの導入＞Macにインストール](https://respawn.littleheroes.jp/w/courses/595/640/742/277?lhsct=content-277)、[Gitの使い方](https://respawn.littleheroes.jp/w/courses/595/641)の「GitHubについて」〜「GitHubへSSH接続」までを終えていること。
-  [Docker Composeのインストール](https://respawn.littleheroes.jp/w/courses/596/1356/1375/781?lhsct=content-781)を終えていること。
-  [DBeaverのインストール](https://respawn.littleheroes.jp/w/courses/1977/1978/1979/1031?lhsct=content-1031)を終えていること。

# セットアップ手順

1. Macは、ターミナル、WindowsはターミナルのUbuntuを開き、Desktopに移動し、MySQL用のコンテナリポジトリをクローンします。

**Macのターミナル初期画面　↓**

<img width="573" height="364" alt="スクリーンショット 2025-08-06 12 11 50" src="https://github.com/user-attachments/assets/96b46c81-590c-4099-9e89-2acbe73b5338" />



**WindowsのターミナルのUbuntuの初期画面　↓**
/mnt/c/Users/<ユーザー名>

以下のコマンドを実行します。
Macのデスクトップに移動
```bash
cd Desktop
```

Windowsのデスクトップに移動
```bash
cd デスクトップ
```

デスクトップに移動したら、以下を実行します。

```bash
git clone git@github.com:pygmalin-info/db-training.git
cd db-training
```

クローンに成功すれば以下のようなメッセージが表示されます。自分のデスクトップ画面にdb-trainingというフォルダがあれば、クローン成功です。
```bash
Cloning into 'db-training'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 6 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (6/6), done.
```

2. **Docker Desktop のアプリケーションを起動**して、MySQL コンテナを起動します。

```bash
docker compose up -d
```

コンテナの起動に成功すれば、以下のようなメッセージが表示され、	Docker Desktopの画面は以下のようになります。
```bash

[+] Running 1/1
 ✔ Container mysql  Running                                                0.0s 
```

<img width="1264" height="724" alt="スクリーンショット 2025-08-06 12 23 02" src="https://github.com/user-attachments/assets/8495973f-ae68-4176-845b-c3f0aa70a938" />


3. MySQL に接続する場合

まず、MySQL コンテナに入ります。

```bash
docker exec -it mysql bash
```

次に、コンテナ内で以下のコマンドを実行して MySQL にログインします。

```bash
mysql -u user -p
```

パスワードを求められたら `pass` を入力してください。

以下のような画面が表示されます。
```bash
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.43 MySQL Community Server - GPL

Copyright (c) 2000, 2025, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 

```

これでデータベース課題をこなす環境構築ができました！！


4. 終了する場合（MySQLから出る、コンテナの停止・削除）
```bash
exit
```
結果が以下のようになると、MySQLの操作ができる環境から抜け出します。
```bash
mysql> exit
Bye
bash-5.1# 
```
もう一度、`exit`と打つと、コンテナから抜け出します。
```bash
bash-5.1# exit
exit
```
そのあと、Dockerのコンテナを停止するコマンドを打ちます。
```bash
docker compose down
```
以下のようになればコンテナの停止になります。
```bash
[+] Running 2/2
 ✔ Container mysql              Removed                                    2.3s 
 ✔ Network db-training_default  Removed    
```

作業が終わりましたら、コンテナの停止・削除もお忘れなく。コンテナを立ち上げたままにするとPCが重くなります。
