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
 has_many :usesrs_group
 has_many :group

## grousテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|users_id|integer|null: false, foreign_key: true|
### Association
 has_many :comments
 has_many :usesrs_groups
 belongs_to :user

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|message|text|null: false|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
 belongs_to :user
 belongs_to :group

## usesrs_groupテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false, foreign_key: true|
|groops_id|integer|null: false, foreign_key: true|
### Association
 belongs_to :user
 belongs_to :group