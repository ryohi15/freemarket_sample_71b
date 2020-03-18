# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|last_name|string|null: false|
|first_name|string|null: false|
|last_name_kana|string|null: false|
|first_name_kana|string|null: false|
|birthday|data|null: false|
|receiver_last_name|string|null: false|
|receiver_first_name|string|null: false|
|receiver_last_name_kana|string|null: false|
|receiver_first_name_kana|string|null: false|

### Association
- has_many :items
- has_one  :card
- has_many :addresses

## cardsテーブル  
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|number|integer|null: false, unique: true|
|month|integer|null: false|
|year|integer|null: false|
|security|integer|null: false, unique: true|

### Association
- belongs_to :user

## addresses
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|postcode|integer|null:false|
|prefecture|string|null: false|
|city|string|null: false|
|block|string|null: false|

### Association
- belongs_to :user


## itemsテーブル  
|Column|Type|Options|
|------|----|-------|
|item_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|name|string|null: false|
|content|text|null: false|
|status|string|null: false|
|price|integer|null: false|
|cost|string|null: false|
|date|string|null: false|

### Association
- belongs_to :user
- belongs_to :category1
- belongs_to :category2


## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

## Association
- belongs_to :user

## categories1テーブル  
|Column|Type|Options|
|------|----|-------|
|category|string|null: false|

## Association
- has_many :items
- has_many :categories2

## categories2テーブル  
|Column|Type|Options|
|------|----|-------|
|category|string|null: false|

## Association
- has_many :items
- belongs_to :category1