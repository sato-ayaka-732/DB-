# データベース（MySQL） セットアップ手順

## 前提条件

- [ ]【Windowsの方】[WSLインストール](https://respawn.littleheroes.jp/w/courses/2285/2351/2352/1284?lhsct=content-1284)、[Gitで作業を始める準備](https://respawn.littleheroes.jp/w/courses/2285/2351/2353/1286?lhsct=content-1286)、[GitHubとSSH接続](https://respawn.littleheroes.jp/w/courses/2285/2351/2353/1287?lhsct=content-1287)、[Dockerの設定](https://respawn.littleheroes.jp/w/courses/2285/2351/2354/1288?lhsct=content-1288)を終えていること。
- [ ] 【Macの方】は[Docker Desktop for Macのインストール](https://respawn.littleheroes.jp/w/courses/596/1357/1380/797?lhsct=content-797)、[Gitの導入＞Macにインストール](https://respawn.littleheroes.jp/w/courses/595/640/742/277?lhsct=content-277)、[Gitの使い方](https://respawn.littleheroes.jp/w/courses/595/641)の「GitHubについて」〜「GitHubへSSH接続」までを終えていること。
- [ ] [Docker Composeのインストール](https://respawn.littleheroes.jp/w/courses/596/1356/1375/781?lhsct=content-781)を終えていること。
- [ ] [DBeaverのインストール](https://respawn.littleheroes.jp/w/courses/1977/1978/1979/1031?lhsct=content-1031)を終えていること。

## セットアップ手順

1. Macは、ターミナル、WindowsはターミナルのUbuntuを開き、Desctopに移動し、MySQL用のコンテナリポジトリをクローンします。

**Macのターミナル初期画面**

<img width="573" height="364" alt="スクリーンショット 2025-08-06 12 11 50" src="https://github.com/user-attachments/assets/96b46c81-590c-4099-9e89-2acbe73b5338" />

**WindowsのターミナルのUbuntuの初期画面**
<スクショ貼りたい>

以下のコマンドを実行します。
Macのデスクトップに移動
```bash
cd Desktop
```

Windowsのデスクトップに移動
```bash
あとで追加
```

```bash
git clone git@github.com:pygmalin-info/db-training.git
cd db-training
```

cloneに成功すれば以下のようなメッセージが表示されます。
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
 ✔ Container mysql  Started  
```

<img width="1264" height="724" alt="スクリーンショット 2025-08-06 12 23 02" src="https://github.com/user-attachments/assets/8495973f-ae68-4176-845b-c3f0aa70a938" />


3. MySQL に接続する場合

まず、MySQL コンテナに入ります。

```bash
docker exec -it mysql bash
```

次に、コンテナ内で以下のコマンドを実行して MySQL にログインします。

```bash
mysql -u test_user -p
```

パスワードを求められたら `pass` を入力してください。

これでデータベース課題をこなす環境構築ができました！！


4. 終了する場合（コンテナの停止・削除）

```bash
docker compose down
```

作業が終わりましたら、コンテナの停止・削除もお忘れなく。コンテナを立ち上げたままにするとPCが重くなります。

## 補足

- 初期データは `init/init.sql` で投入されます。
- 設定は `config/my.cnf` でカスタマイズできます。
