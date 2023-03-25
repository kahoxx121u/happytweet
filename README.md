# README

# アプリケーション名
HappyTweet

# アプリケーション概要
毎日幸せに感じたことを呟き、世界中にハッピーをシェアすることができる

# URL
https://happytweet.onrender.com

# テスト用アカウント
Basic認証パスワード：2222

Basic認証 ID：admin

メールアドレス：222@222

パスワード：2222ww

# 利用方法
ちょっとしたハッピーなことを世界中に共有することができる

第三者が投稿した内容にコメントを残すことができ、ハッピーの連鎖に繋げることができる

# アプリケーションを作成した背景
毎日嫌なことや不満に思うことをつぶやくより、

楽しいことや嬉しいことをつぶやく癖をつけると、

気持ちが前向きになるということに気づいたので、

前向きなことしか呟けないSNSを開発しようと思いました。

# 洗い出した要件

 ＜トップページ＞

【ボタン】
サインイン/ログインページへ遷移できるボタンがある

ログイン時は、ログアウトできるボタンがある

ツイートを投稿する投稿ボタンがある

編集/削除ができるドロップダウン形式のボタンがある

共有された写真の詳細ページへ遷移できるボタンがある

【表示】
共有された写真を一覧で見ることができる

共有者のニックネームを見ることができる

＜ユーザー登録ページ＞

【ボタン】
サインインできるボタンがある

【表示】
サインインページを見ることができる

＜ログインページ＞

【ボタン】
ログインできるボタンがある

【表示】
ログインページを見ることができる

＜詳細ページ＞ 

【ボタン】
コメントできるボタンがある

【表示】
他の人のコメントを見ることができる

# 実装した機能について画像やGIFおよびその説明

* 呟きの投稿の画像

https://gyazo.com/b9cce26b3c3ca104acaa5589732e06b8

* トップページの表示

https://gyazo.com/ab90667113b28ccf71124e87a097b983

* サインイン画像

https://gyazo.com/886dad9e29af9c7bfde384bc2ff7d31a

* ログイン画像

https://gyazo.com/37e8c9ff4ef89c9f98f5aba2f2d85a22


# データベース設計

### usersテーブル
| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| nickname            | string | null: false |
| email               | string | null: false |
| encrypted_password  | string | null: false |

- has_many :tweets
- has_many :comments

### tweetsテーブル
| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| text   | string     | null: false  |

- belongs_to :user
- has_many :comments
- has_one_attached :image

### commentsテーブル
| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user_id   | integer    | null: false |
| tweet_id  | integer    | null: false |
| text      | text       | null: false |

- belongs_to :tweet 
- belongs_to :user   


# 開発環境
・フロントエンド

・バックエンド

・インフラ

・テキストエディタ

・タスク管理

# ローカルでの動作方法
% cd xxxxx

% bundle install

% yarn install





