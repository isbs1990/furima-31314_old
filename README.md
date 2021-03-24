# テーブル設計

## usersテーブル(ユーザー情報テーブル)
| Column                               | Type    | Options     |
| -------------------------            | ------- | ----------- |
| nickname(ニックネーム)                 | string  | null: false |
| user_email（メールアドレス）            | string  | null: false, unique: true |
| encrypted_password（パスワード）       | string  | null: false |
| knj_first_name（漢字姓）              | string  | null: false |
| knj_last_name（漢字名）               | string  | null: false |
| kana_first_name（カナ姓）             | string    | null: false |
| kana_last_name（カナ名）              | string  | null: false |
| birth_day（生年月日）                 | date    | null: false |

### Association
- has_many :item_sales
- has_many :orders

## item_salesテーブル(出品物テーブル)
| Column                         | Type               | Options     |
| -------------------------      | -------            | ----------- |
| name（出品名）                   | string             | null: false |
| description(出品物詳細)          | text               | null: false |
| detail_category_id(カテゴリー    | string             | null: false |
| detail_status_id(状態)          | string             | null: false |
| delivery_cost_id(負担額)        | integer            | null: false |
| pref_id(県)                    | integer            | null: false |
| delivery_day_id(発送日)         | string             | null: false |
| price(販売価格)              | integer            | null: false |

### Association
- has_many :orders

## item_buysテーブル(購入物テーブル)
| Column                                   | Type               | Options     |
| -------------------------               | -------            | ----------- |
| buy_delivery_address(配送先郵便番号)      | string             | null: false |
| pref_id(県)                             | integer            | null: false |
| buy_derivery_city(配送先市)              | string             | null: false |
| buy_derivery_num(配送先番地)             | string             | null: false |
| buy_derivery_bld(配送先建物名)            | string             | null: true  |
| buy_tell_num(購入者電話番号)              | string            | null: false |

### Association
- has_one :orders

## ordersテーブル(購入情報テーブル)
| Column                                    | Type               | Options     |
| -------------------------                 | -------            | ----------- |
| user_id                                   | integer             | null: false |
| item_sale_id                              | integer             | null: false |

### Association
- has_one :item_buys
- belongs_to :item_sales
- belongs_to :item_buys