---
marp: true
title: BigQuery リリース振り返り 2021年4月
_paginate: false
paginate: true
_header: "#bq_sushi #17 BigQueryのデータパイプラインってどうしてる？"
header: BigQuery リリース振り返り 2021年4月
---

# BigQuery リリース振り返り 2021-04

@na0fu3y

![bg right:25% 100%](bigquery-512-color.png)

---

## Naofumi Yamada [@na0fu3y](https://twitter.com/na0fu3y)
![h:25](https://corp.mfkessai.co.jp/images/info/Money-Forward-Kessai-Logo.png)

[BQ FUN Slackワークスペース]を運営してます

[BQ FUN Slackワークスペース]: https://join.slack.com/t/bqfun/shared_invite/zt-p14l1byc-rIZ2WmndLdzFBT63HRVgfA

![bg right:25% 90%](https://avatars.githubusercontent.com/u/17900178)

---

## カバー範囲

- [BigQueryの2020年アップデートを（だいたい）全部振り返る]の後から

[BigQueryの2020年アップデートを（だいたい）全部振り返る]: https://medium.com/google-cloud-jp/bigquery-2020-update-summary-dfd245e77e44

- Magnitude Simba JDBC and ODBC driversのリリースは省略

---

## UI
- 新Cloud Consoleがプレビュー:tada:

![bg right:60% 100%](https://cloud.google.com/bigquery/images/web-ui-components.png)

---

## UI
- BigQuery管理リソースグラフ（Reservations利用者向け）がプレビュー:tada:

![bg right:60% 100%](https://cloud.google.com/bigquery/images/admin-chart-overview.png)

---

## SQL

### GA:confetti_ball:
- 高精度計算のための`BIGNUMERIC`型

- JSON文字列の配列を処理する`JSON_(EXTRACT_STRING|QUERY|VALUE)_ARRAY`関数

- データセットを作成、設定、削除する`(CREATE|ALTER|DROP) SCHEMA`ステートメント

---

## SQL

### プレビュー:tada:
- テーブルから列を削除する`ALTER TABLE DROP COLUMN`ステートメント

- 大きなテーブルのランダムなサブセットをクエリする`TABLESAMPLE`句

---

## SQL

### プレビュー:tada:

- パーティションの詳細を確認する`INFORMATION_SCHEMA.PARTITIONS`ビュー

- テーブルの再作成に使用できるDDLステートメント`DDL`が`INFORMATION_SCHEMA.TABLES`ビューに追加

---

## リージョン
- アイオワ（us-central1）リージョンが利用可能に:confetti_ball:
- ワルシャワ（europe-central2）リージョンで利用可能に:confetti_ball:

---

## 性能改善

- マテリアライズドビューがGAに:confetti_ball:
    - 異なるデータセットとプロジェクト内でも作成可能に
    - 追加の集計関数、`CROSS/LEFT JOIN UNNEST`、`INFORMATION_SCHEMA`、顧客管理の暗号鍵もサポート

- DATETIME列のクラスター化テーブルがGAに:confetti_ball:

---

## 性能改善

- Cloud Storageへのクエリがクエリ結果のキャッシュ対象に:confetti_ball:

- 以下のBigQueryフィールドの最大長が128文字から300文字に増加:confetti_ball:
    - テーブルの列名、列のエイリアス名、ユーザー定義の関数名

---

## データ読み込み

- Storage Read APIのネットワーク課金が2021年第3四半期の初めから開始

- Parquet形式の読み込み改善
  - Enum論理型はSTRING または BYTES に変換されるように:confetti_ball:
  - LIST論理型でスキーマ推定できるように:confetti_ball:

---

## データ書き込み

- Storage Write APIがプレビューに:tada:
- Parquet形式でのテーブルデータのエクスポートをプレビュー:tada:

---

## BI Engine
- BI Engine SQL インターフェースを使って、他のBIツールと統合可能に

![bg right:60% 100%](https://cloud.google.com/bi-engine/images/sql-interface-diagram.png)

---

## Data Transfer Service
- Cloud Storageからの転送の最小ファイル有効期間1時間の要件が廃止

- Cloud Storageからの定期的な転送の最小間隔が1時間から15分に短縮

- VPC Service Controlsで完全サポート

---

## 個人的、今後に期待:hourglass:

- Omni、Data QnAのパブリックプレビュー
- Looker、Dataformの統合
- Feature Store

---

## 引用元

### リリースノート
- https://cloud.google.com/bigquery/docs/release-notes
- https://cloud.google.com/bi-engine/docs/release-notes
- https://cloud.google.com/bigquery-transfer/docs/release-notes

### 画像
- https://corp.mfkessai.co.jp/press/2020/11/02/
- https://cloud.google.com/bigquery/docs/bigquery-web-ui
- https://cloud.google.com/bigquery/docs/admin-resource-charts
- https://cloud.google.com/bi-engine/docs/sql-interface-overview
