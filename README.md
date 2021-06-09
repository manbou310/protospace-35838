
#テーブル設計

## users テーブル
| Column       | Type       | Options     |
| ------------ | ---------- | ----------- |
| email        | string     | null: false |
| password     | string     | null: false |
| name         | string     | null: false |
| profile      | text       | null: false |
| occupation   | text       | null: false |
| position     | text       | null: false |

### Association
- has many :comments
- has many :prototypes



## commentsテーブル
| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

### Association
- blogs_to :user
- blogs_to :prototype



## prototypesテーブル
| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
- blogs_to :user
- has many :comments