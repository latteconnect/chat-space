# README

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## users テーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups_users
- has_many :groups, through :groups_users
- has_many :messages

## groups テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null :false|

### Association
- has_many :groups_users
- has_many :users, through :groups_users
- has_many :messages

## messages テーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|string|null: false|
|users|references|null: false|
|groups|references|null: false|

### Association
- belongs_to :groups
- belongs_to :users
