## users テーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association

- has_many :prototypes
- has_many :messages

## prototypes テーブル

| Column             | Type   | Options                        |
| ------------------ | ------ | ------------------------------ |
| title              | string | null: false                    |
| catch_copy         | string | null: false                    |
| concept            | string | null: false                    |
| user               | text   | null: false, foreign_key: true |

### Association

- belongs_to :users
- has_many :comments

## comments テーブル

| Column             | Type   | Options                         |
| ------------------ | ------ | ------------------------------- |
| email              | string | null: false                     |
| encrypted_password | string | null: false, foreign_key: true  |
| name               | string | null: false, foreign_key: true  |

### Association

- belongs_to :users
- belongs_to :prototypes