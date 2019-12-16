# README

## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true, unique: true|

### Association
-has_many messages
-has_many group_users
-has_many groups, through: :group_users

## message
|Column|Type|Option|
|------|----|------|
|text|string|
|image|string|
|user|reference|null: false, foreign_key: true|
|group|reference|null: false, foreign_key: true|

### Association
-belongs_to user
-belongs_to group

## groupテーブル
|Column|Type|Option|
|------|----|------|
|name|string|null: false, unique: true|

### Association
-has_many massages
-has_many group_users
-has_many users, through: :group_users

## group_usersテーブル
|Column|Type|Option|
|------|----|------|
|user|reference|null: false, foreign_key: true|
|group|reference|null: false, foreign_key: true|

### Association
-belongs_to user
-belongs_to group