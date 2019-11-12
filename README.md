## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|varchar|index: true, null: false|
|email|varchar|null: false|
|password|varchar|null: false|

### Association
- has_many :groups through: groups_users
- has_many :messages

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|varchar|index: true, null: false|

### Association
- has_many :users through: groups_users
- has_many :messages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|group_id|integer|null: false|
|user_id|integer|null: false|

### Association
- belongs_to :user
- belongs_to :group