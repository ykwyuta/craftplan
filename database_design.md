# データベース設計の調査結果

ファイル `file_list.md` の記載をもとに、本システムのデータベース設計（Ashリソースおよび関連するテーブル等）を以下にまとめます。

## 1. アカウント (Accounts)
アカウント関連（ユーザー、トークン、APIキーなど）のドメイン・リソース。Ash Authenticationを利用しています。
- **APIキー (`accounts_api_keys`)**: APIキーのリソース。APIからのリクエスト時の認証に使用される。
- **トークン (`accounts_tokens`)**: 認証トークン（発行、無効化、有効期限切れなど）を管理。
- **ユーザー (`accounts_users`)**: ユーザーアカウント情報。認証（パスワード等）や役割（admin, staff）を管理。

## 2. カタログ (Catalog)
製品カタログ、BOM、作業工程などをまとめるドメインです。
- **製品 (`catalog_products`)**: 製品そのもののリソース。原価計算、アレルゲン情報、栄養成分、1日の最大数量、ステータスなどを管理。
- **BOM (`catalog_boms`)**: 製品の部品表（Bill of Materials）。アクティブなBOMのバージョン管理などを含む。
- **BOMコンポーネント (`catalog_bom_components`)**: BOMを構成する要素（材料または別の製品）。
- **BOMロールアップ (`catalog_bom_rollups`)**: BOMのコスト集計情報を保持するテーブル。
- **作業工程 (`catalog_labor_steps`)**: 製造工程における作業ステップ（所要時間、コスト、1実行あたりの単位数など）。

## 3. CRM (Customer Relationship Management)
顧客情報を管理するドメインです。
- **顧客 (`crm_customers`)**: 顧客情報（名前、メール、電話番号、住所など）。

## 4. 在庫管理 (Inventory)
材料、ロット、発注、アレルゲン、栄養成分などの在庫管理に関連するドメインです。
- **材料 (`inventory_materials`)**: 在庫として管理される材料・原材料（名前、SKU、単位、価格、適正在庫など）。
- **ロット (`inventory_lots`)**: 材料のロット番号、有効期限、入庫日などを管理。
- **在庫移動 (`inventory_movements`)**: 材料やロットの在庫の増減（在庫調整、入庫、消費など）の履歴。
- **アレルゲン (`inventory_allergens`)**: 材料などに含まれるアレルゲン情報。
  - **材料-アレルゲン関連 (`inventory_material_allergen`)**: 中間テーブル。
- **栄養成分 (`inventory_nutritional_facts`)**: 材料や製品に含まれる栄養成分の項目。
  - **材料-栄養成分関連 (`inventory_material_nutritional_fact`)**: 中間テーブル。
- **サプライヤー (`inventory_suppliers`)**: 材料の仕入先情報。
- **購買発注 (`inventory_purchase_orders`)**: 購買発注全体を管理（ステータス、発注先情報など）。
  - **購買発注アイテム (`inventory_purchase_order_items`)**: 個々の発注アイテム（材料、数量、単価）。

## 5. 注文・生産管理 (Orders)
注文および関連する生産バッチなどを管理するドメインです。
- **注文 (`orders_orders`)**: 顧客からの注文情報。納期、ステータス、通貨、小計、税、割引、合計、配送方法などを管理。
- **注文アイテム (`orders_items`)**: 注文に含まれる商品（製品）とその数量、価格、ステータス、消費日時などを管理。
- **生産バッチ (`orders_production_batches`)**: 製品の生産バッチ（計画数量、使用BOM、ステータス、コストなど）。
- **生産バッチ・ロット割り当て (`orders_production_batch_lots`)**: 生産バッチに割り当てられた特定の材料ロット情報。
- **注文アイテム・ロット割り当て (`orders_item_lots`)**: 注文アイテムに割り当てられた特定のロット情報。
- **注文アイテム・バッチ割り当て (`orders_item_batch_allocations`)**: 注文アイテムと生産バッチの紐付け。

## 6. 設定 (Settings)
アプリケーションの各種設定を管理するドメインです。
- **設定 (`settings`)**: グローバルな設定情報（通貨、税率、デフォルトのリードタイム、メール設定、在庫予測の設定など）を保持。

## 特記事項
- 各ドメインのエンティティはAsh Frameworkのリソースとして定義されており、スナップショット（`priv/resource_snapshots/repo/`配下）によりマイグレーションが生成・管理されています。
- マイグレーションファイルによると、一部の機能にはPostgreSQLの拡張機能（例: GINインデックスやカスタム関数等）も用いられています。
