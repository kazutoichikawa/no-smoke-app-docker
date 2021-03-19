# README
# アプリケーション名
禁煙カレンダー

# アプリケーション概要
喫煙状態をチェックするカレンダー
# URL
デプロイ後追加

# テスト用アカウント


# 利用方法


# 目指した課題解決
禁煙を目指すカレンダー
既存の禁煙サポートアプリでは「○○日禁煙中できています」など禁煙期間にフォーカスし、褒めて達成させる傾向が強いですが、本アプリは徐々に本数を減らすことを目的とし、褒めて達成させるのではなく「たばこ１本につき14.4分の寿命が減るという統計データを利用し、日本の平均寿命である84歳を基軸として算出した「残りの寿命」と、たばこ１本を26円とした、これまで使った「金額の累計」を見える化することで、危機感を煽り、最終的な禁煙達成を目指すアプリです。

# 要件定義
○ユーザー管理機能  
サインアップ/サインイン/サインアウトに加え、管理者用アカウントが登録されています。  
○入力機能

# テーブル設計

## User テーブル
| Column          | Type    |Options                    |
| --------------- | ------- | ------------------------- |
| name            | string  | null:false                |
| email           | string  | null: false, unique:true  |
| password        | string  | null:false                | 
| birthday        | date    | null:false                |
| cigarette_count | integer | null:false                |
| cigarette_price | integer | null:false                |
| ave_count       | integer | null:false                |
| admin           | boolean |                           |

### Association
- has_many :events

## Events テーブル
| Column        | Type       | Options     |
| ------------- | ---------- | ----------- |
| name          | string     | null: false |
| count         | integer    | null: false |
| profile       | text       | null: false |

### Association
- belongs_to :user
