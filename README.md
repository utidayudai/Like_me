# README

## usersテーブル

| colum              | types  | option                    |
| ------------------ | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| birthday           | date   | null: false               |

## Association

- has_many :items
- has_many :records
- has_many :carts

## admin_user

| colum | types | option |
| ----- | ----- | ------ |

## Association

- has_many :items


## itemsテーブル

| colum       | types      | option                         |
| ----------- | ---------- | ------------------------------ |
| title       | string     | null: false                    |
| content     | text       | null: false                    |
| price       | integer    | null: false                    |
| category_id | integer    | null: false                    |
| admin_user  | references | null: false, foreign_key: true |

## Association

- belongs_to :user
- has_one :records
- has_one :carts
- has_one :admin_user

## ordersテーブル

| colum          | types      | option                         |
| -------------- | ---------- | ------------------------------ |
| address_number | string     | null: false                    |
| place_id       | integer    | null: false                    |
| address        | string     | null: false                    |
| type_id        | integer    | null: false                    |
| phone          | string     | null: false                    |
| record         | references | null: false, foreign_key: true |

## Association

- belongs_to :record



## recordsテーブル

| colum | types      | option                         |
| ----- | ---------- | ------------------------------ |
| user  | references | null: false, foreign_key: true |
| sell  | references | null: false, foreign_key: true |

## Association

- belongs_to :user
- has_one :order
- belongs_to :item



## cartsテーブル

| colum | types      | option                         |
| ----- | ---------- | ------------------------------ |
| user  | references | null: false, foreign_key: true |
| sell  | references | null: false, foreign_key: true |

## Association

- belongs_to :user
- belongs_to :item