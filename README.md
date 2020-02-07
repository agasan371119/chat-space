# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|user_id|integer|null: false|
- belongs_to :user
- has_many :messages
- has_many :groups_users
- has_many :users, through: :groups_users

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
- belongs_to :group
- belongs_to :user

|Column|Type|Options|
|------|----|-------|
|image|string|index|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
- has_many :messages_photos
- has_many :messages, through: messages_photos

|Column|Type|Options|
|------|----|-------|
|photo_id|integer|null: false, foreign_key: true|
|message_id|integer|null: false, foreign_key: true|
- belongs_to :message
- belongs_to :photo

|Column|Type|Options|
|------|----|-------|
|body|text|null: false, index|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
- has_many :messages_photos
- has_mane :photos, through: messages_photos
- belongs_to :user
- belongs_to :group 

