# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

#テーブル設計

##usersテーブル

| Column      | Type   | Options     |
| --------    | ------ | ----------- |
| email       | string | null: false |
| password    | string | null: false |
| profile     | text   | null: false |
| occupation  | text   | null: false |
| position    | text   | null: false |
| name        | string | null: false |

### Association

- has_many :prototypes
- has_many :comments

##prototypesテーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| title     | string | null: false |
| catch_copy| text   | null: false |
| concept   | text   | null: false |
| images    | ActiveStorageで実装   |
| user      | references型         |


### Association

- belongs_to :users
- has_many :comments

##commentsテーブル
| Column     | Type       | Options     |
| --------   | ------     | ----------- |
| text       | text       | null: false |
| user       | references型              |
| prototype | references型              | 


### Association

- belongs_to :users
- belongs_to :prototypes


