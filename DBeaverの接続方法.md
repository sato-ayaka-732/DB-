https://respawn.littleheroes.jp/a/courses/2311/content-4d7c6f8b-d86b-43ed-8fdf-0bfde2448d76/edit?skipcfm=1


# DBeaverとは

DBeaver（ディービーバー、デービーバー）は、パソコンでデータベースを操作するためのツールです。  
難しいコマンドを覚えなくても、グラフィカルな画面（GUI）でテーブルを見たり、データを追加・編集・検索したりできます。


詳しくは[データベースツールについて](https://respawn.littleheroes.jp/w/courses/1977/1981/1982/1032?lhsct=content-1032)を参考にしてください。


# 学習用の『データベース』を作成しましょう
    前回のセクションで構築した環境をDBeaverと接続します。
※前回のセクションでDBの学習環境が整っていることが前提です。


1. DBeaverでデータベースの接続情報を入力します。
DBeaverの左上アイコンのコンセントマークをクリックしてください。

<img width="1268" height="711" alt="スクリーンショット 2025-08-08 14 25 02" src="https://github.com/user-attachments/assets/18907733-07cb-447b-8b2b-e71b0dc9f1c6" />


2. お使いのデータベース（今回はMysql）を選択し、『次へ』ボタンをクリックしましょう。

<img width="984" height="379" alt="スクリーンショット 2025-08-08 14 31 05" src="https://github.com/user-attachments/assets/d3fd44d2-5335-43a8-98fd-eeb7231f45a1" />

3. データベースの接続情報を入力していきます
Server Host：
設定しているホスト（デフォルトは`localhost`）
Port：
設定しているポート番号（デフォルトは`3306`、今回は`13306`）
ユーザー名：
設定しているユーザー名（デフォルトは`root`、今回は`user`）
パスワード：
設定しているパスワード（今回は`pass`）

<img width="989" height="645" alt="スクリーンショット 2025-08-08 14 33 32" src="https://github.com/user-attachments/assets/d86ea42d-bd43-4659-90ef-a3dcb485b812" />

4. 入力が完了したら、左下の『テスト接続』ボタンをクリックしましょう。

<img width="992" height="178" alt="スクリーンショット 2025-08-08 14 34 29" src="https://github.com/user-attachments/assets/c3a47593-6b45-4dce-8a71-0714c822a36a" />

5. 以下の画像のように接続済みになっていれば接続完了です『OK』ボタンをクリックしましょう。


<img width="444" height="240" alt="スクリーンショット 2025-08-08 14 35 21" src="https://github.com/user-attachments/assets/42fd766f-718c-4a06-bf7c-269bf76ab7bb" />


新しく接続情報が追加されています！

<img width="435" height="212" alt="スクリーンショット 2025-08-08 14 35 47" src="https://github.com/user-attachments/assets/66037d86-7c9a-4561-bb80-68e63b7b4ec1" />

