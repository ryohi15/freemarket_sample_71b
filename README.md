# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|user_last_name|string|null: false|
|user_first_name|string|null: false|
|user_last_name_kana|string|null: false|
|user_first_name_kana|string|null: false|
|birthday|data|null: false|
|receiver_last_name|string|null: false|
|receiver_first_name|string|null: false|
|receiver_last_name_kana|string|null: false|
|receiver_first_name_kana|string|null: false|
|postcode|integer|null:false|
|prefecture|string|null: false|
|city|string|null: false|
|block|string|null: false|

### Association
- has_many :items
- has_one  :card

## itemsテーブル  
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|content|text|null: false|
|status|string|null: false|
|price|integer|null: false|
|cost|string|null: false|
|date|string|null: false|
|image1|string|null: false|
|image2|string|null: false|
|image3|string|null: false|

### Association
- belongs_to :user
- belongs_to :category1
- belongs_to :category2

## cardsテーブル  
|Column|Type|Options|
|------|----|-------|
|number|integer|null: false, unique: true|
|month|integer|null: false|
|year|integer|null: false|
|security|integer|null: false, unique: true|

### Association
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