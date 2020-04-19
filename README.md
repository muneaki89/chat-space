# DB設計
aaaa
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
- has_many :groups_users
- has_many :users, through :groups_users
- has_many :comments

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|string|
|image|string|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|groups|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user