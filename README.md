# Docker で らくらく WordPress ローカル環境構築
## はじめに
DockerでWordpressのローカル環境を簡単に構築できるテンプレートがほしいなと思って作りました。
自由に使用していただいて構いませんが、自己責任にてお願いいたします m(_ _)m

## 使い方
### 起動
以下のコマンドを実行してください。
`docker compose up -d`

初回起動時のみ、上記コマンドを実行後に、さらに以下のコマンドを実行してください。
`make init`

その後、 http://localhost:8000 にアクセスしてみてください。WordPressサイトが起動していると思います。

※まれに上記のコマンドでエラーが発生することがあります。それはDockerコンテナが完全に起動していない状態でコマンドを実行したためです。その場合、時間を置いて（10秒ぐらい）もう一度コマンドを実行するとうまくいきます。

※上記のコマンド実行時に、wp-init.shファイルがDockerコンテナにコピーされて実行されます。それで、あらかじめwp-init.shを編集しておけば、WordPressの初期設定を変えることができます（自己責任でお願いします）。

### 終了
以下のコマンドを実行してください。
`docker compose down`

### 削除（リセット）
以下のコマンドを実行してください（コンテナ起動中に実行することを想定していますが、終了状態で実行しても動きます）。
`make destroy`

**上記コマンドを実行すると、WordPressのファイルやDBがすべて削除されます。ご注意ください。**
