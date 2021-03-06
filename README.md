# テーブル設計

## usersテーブル

| column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association
- has_many: :comments
- has_many: :prototypes


## prototypesテーブル

| column     | Type      | Options                        |
| ---------- | --------- | -------------------------------|
| title      | string    | null: false                    |
| catch_copy | text      | null: false                    |
| concept    | text      | null: false                    |
| user       | reference | null: false, foreign_key: true |

### Association
- belongs_to: :users
- has_many: :comments


## commentsテーブル

| column    | Type      | Options                        |
| --------- | --------- | ------------------------------ |
| text      | text      | null: false                    |
| user      | reference | null: false                    |
| prototype | reference | null: false, foreign_key: true |

### Association
- belongs_to: :user
- belongs_to: :prototype