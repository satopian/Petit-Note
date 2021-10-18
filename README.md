# Petit Note
- 1スレッド1ログファイル形式のスレッド式の画像掲示板です。  
- PaintBBS NEOとChickenPaintが使えるお絵かき掲示板です。

## v0.9.5以前のPetit Noteをご利用の方へのお願い

- テーマのHTMLの｢BASIC｣ディレクトリと、index.php、functions.php、config.phpの更新が必要です。  
セキュリティリスクを回避するためのアップデートをお願いします。

## ダウンロード

- [リリース](https://github.com/satopian/Petit_Note/releases)から安定版をダウンロードできます。

## DEMO
- [Petit Note](https://pbbs.sakura.ne.jp/cgi/neosample/petitnote/)  
- [イラスト投稿サイトPetit Note](https://pbbs.sakura.ne.jp/petit/)
  
![image](https://user-images.githubusercontent.com/44894014/134553433-d50e05be-a483-4b94-a575-3cead96b6720.png)

## 履歴

## 21/10/13 v0.9.8.0 
- 削除ボタンを押した時に記事が選択されていない時はエラー画面になるようにした。これまでは削除に失敗しても何も起きませんでした。
- 指定した日付より古い記事のユーザーによる編集を禁止。これまでは古い記事の編集が可能でした。しかし、半年前の記事を編集するとしたらそれはスパムかもしれないので、記事の編集をロックします。管理者は従来どおり編集できます。またユーザーによる削除はこれまで通り可能です。

## 21/10/13 v0.9.7.3 
-　新しいスレッドを行末に追加する仕様を変更し行頭に。従来の`alllog.log`を逆順に。  
[v0.9.7で仕様変更、v0.9.6.3以前のalllog.log(全体ログ)の変換が必要になりました。 · Issue #6 · satopian/Petit_Note](https://github.com/satopian/Petit_Note/issues/6)  
ログファイルの変換が必要になりました。  
上記リンク先にログファイルの変換方法の詳細をまとめました。お手数をおかけしますがよろしくお願いいたします。  

安定版をリリースからダウンロードできます。  

[Petit Note v0.9.7.3 リリース](https://github.com/satopian/Petit_Note/releases/tag/v0.9.7.3)

## 21/10/11 v0.9.6.3

- 管理者編集モードで編集に失敗するバグを修正。
- 最下部の｢管理｣メニューが2重に表示されるバグを修正。
- 管理パス、第2パス未設定時にはパス不一致とする処理を追加。


## 21/10/11 v0.9.6.1

- 名前の入力を必須にする、しないを設定できるようにしました。
- sage機能を追加しました。
- config.phpに新規設定項目。第2パスワードを使って管理者である事を再確認する処理を追加。 

## 21/10/09 v0.9.3.3

- セキュリティ対策。
- ログイン時にsessionIDを再発行してsession固定攻撃対策。
- 編集･削除時にcsrfによる処理が行われないようにトークンをセット。  
これまでは、削除の時にはトークンがセットされていませんでした。
- sessionのクッキーの範囲を掲示板のカレントディレクトリに限定。  
これまでは複数設置したPetit Noteのモードが同時に変更されていました。  
操作する人は同じ人とはいえ、他のディレクトリのアプリに影響がでるのはよくない事なので、アプリのカレントディレクトリ別のsession IDとクッキーを使用する形に変更しました。

## 21/10/06 v0.8.1

- 日記モードで使用していても画像でレスができる状態だったため、レスで画像アップロードを使う･使わないを設定できるようにしました。

## 21/09/23 v0.7.5

- 編集時にタイトル欄を空にした時にも｢無題｣と入るようにした。レスの題名をスレッドの親のタイトルにRe:を付けたものに。
- レスの時は親のタイトルを自動で入れる。ただし掲示板には表示されない。外部プログラム使用時に必要。
- お絵かきコメントのJavaScriptの修正。
レスでお絵かきの時に題名欄が表示されないようにする工夫ですが、動作していれば従来通りでも問題ありません。 

## 21/09/23 v0.6

- 記事の編集･削除。続きを描く、管理者認証マークの表示。カタログ機能。投稿者名の名前で記事の一覧。メール通知機能。  
ログファイルの拡張に区切をつけて、ログファイルの形式をいったん確定。

## 21/09/06 v0.02
- 投稿時のパスワードをパスワードハッシュで保存。
- ユーザー削除機能を追加しました。
- 日記モードができました。
- 日記モードの時は、スレ立てができるのは管理者のみになり、フォームを偽装して投稿してもエラーになります。
- 管理者削除と日記モードログインのための管理者ログインページができました。

## 21/09/03 v0.01
- ~~続きを描く機能はありませんが、~~ NEOとChickenPaintで絵を描いて投稿する事ができます。
- 管理者モードにログインすると記事の削除が可能になります。
- ~~ユーザーのパスワード入力欄はまだないので、ユーザーによる編集や削除もできません。~~
- 合言葉機能を使えば、合言葉を知っている人しか投稿できなくなります。入力フォームもでません。
- 1スレッドに投稿できるレスの数を超えると入力フォームが消えます。さらにフォームを偽装して投稿してもエラーになります。
- レスがついたスレッドが一番上に表示される仕様。
- 古いスレッド判定も投稿順ではなく、最新レス順です。
- レスポンシブデザイン。スマホ･タブレットに対応しています。
- HTMLファイルを外部化して、1枚のHTMLファイルとして扱う事ができるため、ユーザーによるデザインの変更が容易です。
