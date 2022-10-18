# README

## usersテーブル

| colum    | types  | option                    |
| -------- | ------ | ------------------------- |
| nickname | string | null: false               |
| email    | string | null: false, unique: true |
| birthday | date   | null: false               |



## itemsテーブル

| colum       | types      | option                         |
| ----------- | ---------- | ------------------------------ |
| title       | string     | null: false                    |
| content     | text       | null: false                    |
| price       | integer    | null: false                    |
| category_id | integer    | null: false                    |
| admin_user  | references | null: false, foreign_key: true |



## ordersテーブル

| colum          | types      | option                         |
| -------------- | ---------- | ------------------------------ |
| place_id       | integer    | null: false                    |

| address        | string     | null: false                    |
| phone   | string     | null: false                    |
| record     | references | null: false, foreign_key: true |
