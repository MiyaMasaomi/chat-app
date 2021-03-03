# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association

- has_many :room_users
- has_many :rooms, through: room_users
- has_many :messages

## rooms テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association

- has_many :room_users
- has_many :rooms, through: room_users
- has_many :messages

## room_users テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user

## messages テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true

### Association

- belongs_to :room
- belongs_to :user

# アプリケーション名
  チャットアプリ

## アプリケーション概要
  コミュニケーションのすべてがメールなので、いつ誰とどのようなテーマでコミュニケーションをとっていたのか分かりにくい  
  勤務時間外でもメールでのコミュニケーションしか方法がないので、手軽さに欠ける  
  メールに写真を添付/ダウンロードすることが煩わしい  

## URL
  

## BASIC認証
ユーザー名：masaomi  
パスワード：1111

## テスト用アカウント
  テスト  
  メールアドレス：test1@sample  
  パスワード：aaaaaa  

  テスト２  
  メールアドレス：test2@sample  
  パスワード：aaaaaa  

## 利用方法
  新規登録・ログインしていただき、チャットルームを作成してコメントと画像を残せます。  
  ※画像は、JPG,PNG以外を投稿したり、画像が大きすぎるとエラーが起きてしまうため避けていただきますようお願いします。  

## 目指した課題解決
  気軽にチャットをする事ができる環境が必要と考え作成  

## 洗い出した要件
  ユーザー管理機能  
  チャットルーム作成機能  
  写真付きメッセージ投稿機能  

## 実装した機能についてのGIFと説明
  https://i.gyazo.com/e6ef753b4881830b6589d619b780d835.gif
  
## データベース設計
  https://i.gyazo.com/68e521ca8c46ec82faf87ce06a79ed17.png

## ローカルでの動作方法


ruby 2.6.5  
rails 6.0.3.5  

git clone  https://github.com/MiyaMasaomi/chat-app.git  

bundle install  

rails db:migrate  

rails s  
