LHのリンク：https://respawn.littleheroes.jp/w/courses/63/472/498/92

# 環境別のファイルの保存場所
作成したファイルは、『docker-php-envフォルダ』→『phpフォルダ』→『htdocsフォルダ』→『php_testフォルダ』→『index.php』に記述しましょう。

# HTML内にPHPを書く
HTMLの中にPHPを記述する方法を学びましょう。
下記の参考では＜?php echo 'Hello World'; ?＞の部分がPHPの記述になります。
index.phpのファイルを以下のように書き直します。
```bash
<!DOCTYPE html>
<html lang = "ja">
  <head>
    <meta charset = "utf-8">
    <title>PHPの学習</title>
  </head>
  <body>
    <?php echo 'Hello World'; ?>
  </body>
</html>
```

ブラウザのURL入力で[http://localhost:8081/php_test](http://localhost:8081/php_test)と入力し確認してみましょう。
下記のように“Hello World”と表示されたら成功です！！

写真〜〜〜〜〜〜〜〜〜〜

下記のような書き方も出来ます。
h1タグの中にPHPのコードが記述されています。

参考：先ほどのファイル「index.php」を修正して保存しブラウザで確認してみましょう。

<!DOCTYPE html>
<html lang = "ja">
  <head>
    <meta charset = "utf-8">
    <title>PHPの学習</title>
  </head>
  <body>
    <h1><?php echo 'Hello World'; ?></h1>
  </body>
</html>

下記のように、h1タグが効いている形で表示されます。

写真〜〜〜〜〜〜〜〜〜〜

このように開始タグ『＜？php』で始まり、終了タグ『？＞』で終わる間に書かれている物がPHPのプログラムとして認識されます。


# PHPのみでの書き方

PHPのみでコードを記述する書き方
ファイルの一番最初に、開始タグ『＜？php』を書き、PHPのコード（命令文、プログラム）を記述します。
終了タグ『？＞』はいりません。
※一般的に「PHPコードのみのファイルでは終了タグを書かないこと」がルールとなっています。



このセクションは書き直さなくて良さそう！！！！！！！！！！！！
