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
  

## URL
  

## BASIC認証
ユーザー名：masaomi  
パスワード：1111

## テスト用アカウント
  メールアドレス：test1@sample  
  パスワード：111111 

## 利用方法
  新規登録・ログインしていただき、    
  また、ログインしていない方でも商品の詳細を見ることができます。

## 目指した課題解決
  家にある不要なものを必要と思っていただける方に売買ができるシステムです。

## 洗い出した要件
  

## 実装した機能についてのGIFと説明

  
## 実装予定の機能
  コメント投稿機能

## データベース設計

## ローカルでの動作方法


ruby 2.6.5  
rails 6.0.3.4  

git clone  

bundle install  

rails db:migrate  

rails s  
