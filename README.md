# README
# chat-spaceb DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
 has_many :comments
 has_many :comments_group
 

## groopsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|user_id|integer|null: false|
### Association
 has_many :comments
 has_many :comments_group

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|comments|text|null: false|
|users_id|integer|null: false, foreign_key: true|
### Association
 belongs_to :user
 belongs_to :group

## usesr_groupテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false, foreign_key: true|
|comments_id|integer|null: false, foreign_key: true|
|groops_id|integer|null: false, foreign_key: true|
### Association
 belongs_to :user
 belongs_to :group