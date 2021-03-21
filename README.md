# テーブル設計

## usersテーブル
| Column                    | Type    | Options     |
| ------------------------- | ------- | ----------- |
| nickname                  | string  | null: false |
| user_email                | string  | null: false |
| password                  | string  | null: false |
| knj_first_name            | string  | null: false |
| knj_last_name             | text    | null: false |
| kana_first_name           | text    | null: false |
| kana_last_name            | text    | null: false |
| birth_year                | integer | null: false |
| birth_month               | integer | null: false |
| birth_day                 | integer | null: false |

### Association
- has_many :item_sales
- has_many :item_buys

## item_salesテーブル
| Column                    | Type               | Options     |
| ------------------------- | -------            | ----------- |
| item_saler_name           | string             | null: false |
| item_image                | ActiveStorageで実装 | null: false |
| item_name                 | string             | null: false |
| item_description          | text               | null: false |
| item_detail_category      | string             | null: false |
| item_detail_status        | string             | null: false |
| item_delivery_cost        | integer            | null: false |
| item_delivery_pref        | string             | null: false |
| item_delivery_day         | string             | null: false |
| item_price                | integer            | null: false |

## item_buysテーブル
| Column                    | Type               | Options     |
| ------------------------- | -------            | ----------- |
| item_buyer_name           | string             | null: false |
| item_card_num             | string             | null: false |
| item_card_limit           | string             | null: false |
| item_card_cord            | string             | null: false |
| buy_delivery_address      | string             | null: false |
| buy_derivery_pref         | string             | null: false |
| buy_derivery_city         | string             | null: false |
| buy_derivery_num          | string             | null: false |
| buy_derivery_bld          | string             | null: true  |
| buy_tell_num              | integer            | null: false |