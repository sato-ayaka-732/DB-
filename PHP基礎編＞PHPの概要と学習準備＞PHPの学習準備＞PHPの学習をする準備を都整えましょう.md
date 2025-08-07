# PHPの学習をする環境を揃えましょう
##### ・『PHP』のプログラムを書くエディター⇒『VSCode』<br>・『PHP』の動作確認をするサーバーなどの環境⇒『Docker』

# PHPの環境のリポジトリをクローンする
VSCodeを開き、`Command`+`J`でターミナルを開きましょう。（Windowsの方はVScodeがWSLでリモート接続されていることを確認してください）
<img width="1204" height="933" alt="スクリーンショット 2025-08-06 20 28 44" src="https://github.com/user-attachments/assets/62a49526-cf63-4f12-89e5-94151c2aac2a" />


1. デスクトップに移動する
Macの人
```bash
cd Desktop
```
Windowsの人
```bash
cd デスクトップ
```

2. php環境用のリポジトリをクローンする
```bash
git clone git@github.com:pygmalin-info/docker-php-env.git
```
<img width="718" height="115" alt="スクリーンショット 2025-08-06 20 30 29" src="https://github.com/user-attachments/assets/83bc6e9e-be62-4469-80e8-4b953ca0c1b6" />


3. デスクトップにあるdocker-php-envリポジトリに移動する
```bash
cd docker-php-env
```

4. Dockerのコンテナを立ち上げる
```bash
docker compose up -d
```
Docker Desktopの画面が以下のようになっていれば、PHPの環境用のコンテナは立ち上がっています。
<img width="1271" height="716" alt="スクリーンショット 2025-08-06 19 52 13" src="https://github.com/user-attachments/assets/0441b79c-111e-4356-b37e-d1d1d3728793" />

5. MySQLのコンテナに入る
```bash
docker exec -it mysql bash
```

6. MySQLにログインする
```bash
mysql -u root -p
```
パスワードを求められたら、`pass`と入力する

7. `mysql>`となっていれば、SQL文が打てる状態です。（コンテナを抜ける場合は`exit`と入力します。`Bye`と表示されれば、コンテナからは抜け出しています。）


8. 接続確認のため、ブラウザで[http://localhost:8081](http://localhost:8081/)にアクセスする
<img width="1284" height="34" alt="スクリーンショット 2025-08-06 20 22 56" src="https://github.com/user-attachments/assets/8ef09063-6674-40d5-a680-69ff7ead8d00" />


9. 下記のように表示されていればOKです。
<img width="601" height="382" alt="スクリーンショット 2025-08-07 11 53 19" src="https://github.com/user-attachments/assets/e7d9f199-7f6e-4e5a-88e3-dd49c551f69d" />

