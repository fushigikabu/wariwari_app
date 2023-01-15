## usersテーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |

### Association
- has_many :event_users
- has_many :events, through: :event_users
- has_many :moneys

## eventsテーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |

### Association
- has_many :event_users
- has_many :users, through: :event_users
- has_many :moneys

## event_users テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| user    | references | null: false, foreign_key: true |
| event   | references | null: false, foreign_key: true |

### Association
- belongs_to :event
- belongs_to :user

## moneys テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| pay     | integer    | null: false                    |
| user    | references | null: false, foreign_key: true |
| event   | references | null: false, foreign_key: true |

### Association
- belongs_to :event
- belongs_to :user

## comments テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     | null: false                    |
| user    | references | null: false, foreign_key: true |
| event   | references | null: false, foreign_key: true |

### Association
- belongs_to :event
- belongs_to :user

