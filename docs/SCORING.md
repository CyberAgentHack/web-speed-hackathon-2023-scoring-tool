# 採点方法

1. [Lighthouse](https://github.com/GoogleChrome/lighthouse) を用いて、次の2つを検査します
  - ページランディング
  - ユーザーフロー
1. 検査したそれぞれのスコアを合算し、得点とします
1. レギュレーションに違反している場合、順位対象外とします

## ページランディング
1. [Lighthouse](https://github.com/GoogleChrome/lighthouse) を用いて、次の計4つのページを検査します
  - ホームページ
  - 商品詳細ページ
  - 購入手続きページ
  - 404ページ
1. 各ページごと [Lighthouse v10 Performance Scoring](https://web.dev/performance-scoring/#lighthouse-10) に基づき、次の総和をページのスコアとします
  - First Contentful Paint のスコア × 10 (0-10 点)
  - Speed Index のスコア × 10 (0-10 点)
  - Largest Contentful Paint のスコア × 25 (0-25 点)
  - Total Blocking Time のスコア × 30 (0-30 点)
  - Cumulative Layout Shift のスコア × 25 (0-25 点)

※重み付けが同じなので、ページのスコアは Lighthouse が出すスコアと一致します。ただし、Lighthouse のスコアは整数に丸められているのに対し、本競技のスコアは丸める前の値をそのまま使用しています。

## ユーザーフロー
1. [Lighthouse](https://github.com/GoogleChrome/lighthouse) を用いて、次の計3つのユーザーフローを検査します
  - レビューを書く
  - 注文する
  - 初めてのユーザーが商品を買うまで

1. 各ユーザーフローごと 、次の総和をユーザーフローのスコアとします
  - Total Blocking Time のスコア × 25 (0-25 点)
  - Interaction to Next Paint のスコア × 25 (0-25 点)

### 「レビューを書く」について
以下の様に検査します

1. 特定の商品詳細ページに遷移します
1. 特定のユーザーでログインを行います
1. レビューフォームを利用してレビューを書き込み送信を行います

### 「注文する」について
以下の様に検査します

1. ホームページに遷移します
1. 既にカートに商品を追加済みのユーザーでログインを行います
1. 購入手続きページへ遷移します
1. 購入手続きを行います

### 「初めてのユーザーが商品を買うまで」について
以下の様に検査します

1. 特定の商品詳細ページに遷移します
1. 会員登録を行います
1. 商品をカートに追加します
1. 購入手続きページへ遷移します
1. 購入手続きを行います
