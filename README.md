# DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|e-mail|string|null: false,   |
|password|string|null: false|
### Association
- belongs_to :user
- has_many :comments

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- belongs_to :user
- has_many :comments

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|message|string|null: false|
|image|string|null: false,   |
|groups.id|integer|null: false|
|users.id|integer|null: false|
|timestamo|integer|null: false|
### Association
- belongs_to :user
- has_many :comments

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

