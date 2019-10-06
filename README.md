# README
# chat-spaceb DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false ,index: true|
### Association
 has_many :comments
 has_many :usesrs_groups
 has_many :group,through: :usesrs_groups

## grousテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
 has_many :comments
 has_many :usesrs_groups
 has_many :usesrs, through: :usesrs_groups

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|
|image|string|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
 belongs_to :user
 belongs_to :group

## usesrs_groupテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
 belongs_to :user
 belongs_to :group