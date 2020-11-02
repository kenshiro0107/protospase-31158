＃＃usersテーブル

| Colum    | Type   | Options    |
|----------|--------|------------|
|email     |string  |null: false |
|password  |string  |null: false |
|name      |string  |null: false |
|profile   |text    |null: false |
|occupation|text    |null: false |
|position  |text    |null: false |

＃＃＃Association
- has_many: prototypes
- has_many: comments

##prototypesテーブル

| Colum    | Type        | Options         |
|----------|-------------|-----------------|
|title     |string       |null: false      |
|catch_copy|text         |null: false      |
|concept   |text         |null: false      |
|image     |ActiveStorage|                 |
|user      |references   |foreign_key: true|

###Association
- has_many: comments
- belongs_to: user

##commentsテーブル

| Colum    | Type     | Options         |
|----------|----------|-----------------|
|text      |text      |null: false      |
|user      |references|foreign_key: true|
|prototype |references|foreign_key: true|


- belongs_to: prototype
- belongs_to: user