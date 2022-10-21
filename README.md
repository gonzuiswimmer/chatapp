# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation
#テーブル設計

## users テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| encrypted_password | string | null: false |
| email              | string | null: false |

## Association
- has_many :room_users
- has_many :rooms, through: :room_users
- has_many :massages



## rooms テーブル
| Column            | Type   | Options     |
| ----------------- | ------ | ----------- |
| name              | string | null: false |

## Association
- has_many :room_users
- has_many :users, through: :room_users
- has_many :messages

## room_users テーブル
| Column            | Type      | Options                        |
| ----------------- | --------- | ------------------------------ |
| user              | reference | null: false, foreign_key: true |
| room              | reference | null: false, foreign_key: true |

## Association
- belongs_to :room
- belongs_to :user

## messages テーブル
| Column            | Type   | Options                       |
| ----------------- | ------ | ----------------------------- |
| content           | string |                               |
| user              | string | null: false, foreign_key:true |
| room              | string | null: false, foreign_key:true |

## Association
- belongs_to :room
- belongs_to :user

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
