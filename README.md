## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|mail|strind|null: false, unique: true|

### Association

- has_many :groups, throudh: :group_users
- has_many :group_users
- has_many :comments


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|

### Association

- has_many :users, through: :group_users
- has_many :group_users
- has_many :comments


## group_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group|references|index: true, foreign_key: true, null: false|
|user|references|index: true, foreign_key: true, null: false|

### Association

- belongs_to :group
- belongs_to :user



## commentsテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group|references|foreign_key: true|
|user|references|foreign_key: true|

### Association

- belongs_to :user
- belongs_to :group

