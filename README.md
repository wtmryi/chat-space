## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|nickname|strings|null: false, foreign_key: true|
|mail_adress|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|

### Association

- has_many :groups
- has_many :comments
- has_many :members, through: :member


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|group_name|strings|null: false, foreign_key: true|

### Association

- has_many :users
- has_many :members, through: :member


## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association

- belongs_to :group
- belongs_to :user



## commentsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|comment|strings|null: false, foreign_key: true|

### Association

- belongs_to :user
