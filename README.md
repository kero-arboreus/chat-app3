# README

## usersテーブル

| column   | Type   | options     | 
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association
 has_many: messages
 has_many: room_users
 has_many: rooms, through room_users 

## roomsテーブル

| column   | Type   | options     | 
| -------- | ------ | ----------- |
| name     | string | null: false |

### Association
 has_many :messages
 has_many :room_users
 has_many :users, through room_users

## room_usersテーブル

| column   | Type       | options                        | 
| -------- | ---------  | ------------------------------ |
| user     | references | null: false, foreign_key: true |
| room     | references | null: false, foreign_key: true | 

### Association
 belongs_to :user
 belongs_to :room


## messages テーブル

| column   | Type       | options                        | 
| -------- | ---------  | ------------------------------ |
| user     | references | null: false, foreign_key: true |
| room     | references | null: false, foreign_key: true | 
| content  | string     | null: false,                   |

### Association
 belongs_to :user
 belongs_to :room
