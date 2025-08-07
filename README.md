# 事前準備（学習前に必ず終えておくこと）
### 1. Windowsの方
- [WSLのインストール](https://respawn.littleheroes.jp/w/courses/2285/2351/2352/1284?lhsct=content-1284)
- [Gitで作業を始める準備](https://respawn.littleheroes.jp/w/courses/2285/2351/2353/1286?lhsct=content-1286)
- [GitHubとSSH接続](https://respawn.littleheroes.jp/w/courses/2285/2351/2353/1287?lhsct=content-1287)
- [Dockerの設定](https://respawn.littleheroes.jp/w/courses/2285/2351/2354/1288?lhsct=content-1288)

### 2. Macの方
- [Docker Desktop for Macのインストール](https://respawn.littleheroes.jp/w/courses/596/1357/1380/797?lhsct=content-797)
- [Gitの導入＞Macにインストール](https://respawn.littleheroes.jp/w/courses/595/640/742/277?lhsct=content-277)
- [Gitの使い方](https://respawn.littleheroes.jp/w/courses/595/641)の「GitHubについて」〜「GitHubへSSH接続」まで
- [Docker Composeのインストール](https://respawn.littleheroes.jp/w/courses/596/1356/1375/781?lhsct=content-781)

- [DBeaverのインストール（全員共通）](https://respawn.littleheroes.jp/w/courses/1977/1978/1979/1031?lhsct=content-1031)

# セットアップ手順

1. デスクトップにリポジトリをクローン

**Macのターミナル初期画面　↓**

<img width="573" height="364" alt="スクリーンショット 2025-08-06 12 11 50" src="https://github.com/user-attachments/assets/96b46c81-590c-4099-9e89-2acbe73b5338" />



**WindowsのターミナルのUbuntuの初期画面　↓**
/mnt/c/Users/<ユーザー名>

以下のコマンドを実行します。
Mac の場合
```bash
cd ~/Desktop
```

Windows（Ubuntu on WSL）の場合
```bash
cd ~/デスクトップ
```

デスクトップに移動したら、リポジトリをクローンします。
```bash
git clone git@github.com:pygmalin-info/db-training.git
cd db-training
```

成功すると以下のようなメッセージが表示されます：
```bash
Cloning into 'db-training'...
remote: Enumerating objects: ...
...
```

2. **2. Docker Desktop を起動し、MySQL コンテナを立ち上げ

```bash
docker compose up -d
```

起動に成功すれば、以下のようなメッセージが表示されます：

```bash
[+] Running 1/1
 ✔ Container mysql  Running  0.0s 
```

<img width="1264" height="724" alt="スクリーンショット 2025-08-06 12 23 02" src="https://github.com/user-attachments/assets/8495973f-ae68-4176-845b-c3f0aa70a938" />


3. MySQL に接続する方法

コンテナに入ります：

```bash
docker exec -it mysql bash
```

MySQLにログインします：

```bash
mysql -u user -p
```

パスワードを求められたら `pass` を入力してください。


ログイン成功時の画面：
```bash
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is ...
...
mysql>
```

これでデータベース課題をこなす環境構築ができました！！


4. 作業を終了する手順

#### MySQL から出る
```bash
exit
```

```bash
mysql> exit
Bye
bash-5.1#
```


さらにもう一度 `exit` でコンテナからも抜け出せます。

コンテナの停止
```bash
docker compose down
```
![20141121_ubuntu_ter_1-546x349](https://github.com/user-attachments/assets/398c9e8a-7280-466c-bdbb-4bb0eb8d53d1)

```bash

[+] Running 1/1
 ✔ Container mysql              Removed 
 ✔ Network db-training_default Removed
```

## これで完了！

これで、MySQL に接続してデータベースの操作ができる状態になりました。  
次回からは以下の流れで作業開始できます：

1. `cd db-training`
2. `docker compose up -d` で起動
3. `docker exec -it mysql bash` で MySQL に入る
4. 作業後は `exit` → `exit` → `docker compose down`

> ⚠ コンテナを放置するとPCに負荷がかかるので、使い終わったら忘れずに停止してください。
