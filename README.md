# DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|e-mail|string|null: false,   |
|password|string|null: false|
### Association
- has_many :groups_users
- has_many :groups, through :groups_users
- has_many :comments

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :groups_user
- has_many :users, through :groups_users
- has_many :comments

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|string|
|image|string|
|groups|references|null: false, foreign_key: true|
|users|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :groups

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|groups_id|references|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :user