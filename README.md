# README
# chat-spaceb DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :comments
- has_many :imge


## groupテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user

## imgeテーブル
|Column|Type|Options|
|------|----|-------|
|imge|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many :group_comments_imge　through: :imge
- belongs_to :user


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user

## group_comments_imgeテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|comments_id|integer|null: false, foreign_key: true|
|imge_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- has_many :comments
- has_many :imge