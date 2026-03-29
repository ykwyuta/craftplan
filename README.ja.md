<p align="center">
  <img width="80" alt="GitHub-Banner" src="https://github.com/user-attachments/assets/7277558e-dd2a-4f4a-8853-e3a7caa816e7" />
  <h3 align="center">Craftplan</h3>
  <p align="center">小規模な手工業・クラフトビジネス向けのオープンソースERP</p>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-AGPLv3-blue.svg" alt="License: AGPLv3"></a>
  <img src="https://img.shields.io/badge/elixir-%7E%3E%201.15-purple.svg" alt="Elixir ~> 1.15">
  <img src="https://img.shields.io/badge/phoenix-%7E%3E%201.8-orange.svg" alt="Phoenix ~> 1.8">
</p>


<div align="center">

[![ライブデモ](https://img.shields.io/badge/ライブデモ-craftplan.fly.dev-blue)](https://craftplan.fly.dev)

<details>
<summary>🔑 デモ用ログイン情報</summary>
<br>

**メールアドレス**: `test@test.com`
**パスワード**: `Aa123123123123`

</details>
</div>

Craftplanは、カタログ管理・在庫管理・受注処理・生産計画・購買・CRMといったビジネスに必要なすべてのツールを1つのプラットフォームに統合しています。複数の別々なプラットフォームに費用をかけることなく、すぐにビジネスを始められます。

![スケジュール・製造シート・完了スナップショットを含む管理概要](screenshots/plan.webp)

## 機能

**カタログ & BOM（部品表）**
- 写真・ラベル付き製品カタログ
- バージョン管理された部品表 — 最新バージョンのみ編集可、旧バージョンは読み取り専用
- ネストされたBOM全体にわたる自動コストロールアップ
- 時間・コスト追跡付きの労働ステップ

**受注 & 請求書**
- カレンダーベースのスケジュール機能付き顧客受注処理
- 請求書の生成
- 生産バッチへの受注明細の割り当て

**生産管理**
- 自動材料消費付きの生産バッチ管理
- バッチごとのコストスナップショット
- 生産数量トラッキング付きの完了ワークフロー

**在庫管理**
- ロットトレーサビリティ付きの原材料管理
- 在庫移動（消費・受入・調整）
- アレルゲン・栄養成分のトラッキング
- 需要予測と発注計画

**購買管理**
- 発注書とサプライヤー管理
- ロット作成付きの在庫受入

**CRM**
- 顧客・サプライヤーデータベース
- 受注履歴と統計

**インポート / エクスポート**
- 製品・材料・顧客のCSV一括インポート
- CSVエクスポート

**メール**
- UIから設定可能なトランザクションメール配信
- SMTP・SendGrid・Mailgun・Postmark・Brevo・Amazon SES対応
- APIキーは暗号化保存

**カレンダーフィード**
- Googleカレンダー・AppleカレンダーなどのiCal対応アプリ向けiCal（.ics）サブスクリプションURL
- 受注納期・生産バッチスケジュールを含む
- 設定画面からフィードの生成・失効が可能

**API**
- プログラムアクセス用のJSON:API・GraphQLエンドポイント
- 暗号化保存付きのAPIキー認証
- CORS設定

**アクセス制御**
- 管理者・スタッフのロール管理
- 全リソースへのポリシーベースの認可

**グローバル検索**
- 任意のレコードへ即時アクセスできるコマンドパレット（`Cmd+K` / `Ctrl+K`）
- 製品・材料・受注・顧客・バッチにわたるあいまい検索

## スクリーンショット

<table>
  <tr>
    <td><img src="screenshots/catalog-recipe.webp" alt="BOMエディタ" width="400"></td>
    <td><img src="screenshots/orders.webp" alt="受注管理" width="400"></td>
  </tr>
  <tr>
    <td><img src="screenshots/inventory-forecast.webp" alt="在庫予測" width="400"></td>
    <td><img src="screenshots/search.webp" alt="グローバル検索コマンドパレット" width="400"></td>
  </tr>
  <tr>
    <td><img src="screenshots/settings.webp" alt="設定とメール設定" width="400"></td>
    <td></td>
  </tr>
</table>

## 技術スタック

Elixir · [Ash Framework](https://ash-hq.org/) · Phoenix LiveView · PostgreSQL · Tailwind CSS

## はじめに

Craftplanを自分のサーバーにデプロイします。リポジトリのクローンは不要です:

```bash
curl -O https://raw.githubusercontent.com/puemos/craftplan/main/docker-compose.yml
curl -O https://raw.githubusercontent.com/puemos/craftplan/main/.env.example
cp .env.example .env   # 必要なシークレットを入力（.env.exampleを参照）
docker compose up -d
```

これにより、Craftplan・PostgreSQL・MinIOが起動し、マイグレーションが自動的に実行されます。

シングルコンテナモード・Railwayデプロイ・リバースプロキシ設定などの詳細は[セルフホスティングガイド](https://puemos.github.io/craftplan/docs/self-hosting/)を参照してください。

## 開発環境のセットアップ

> コードベースに取り組むコントリビューター向けです。**前提条件:** Docker・Elixir ~> 1.15・Erlang/OTP 27

```bash
docker compose -f docker-compose.dev.yml up -d   # PostgreSQL + MinIO + Mailpitを起動
mix setup               # 依存関係インストール・マイグレーション・アセットビルド・シード
mix phx.server          # localhost:4000 で起動
```

詳細な手順は[開発環境セットアップガイド](https://puemos.github.io/craftplan/docs/getting-started/)を参照してください。

## なぜCraftplanなのか?

- **手工業製造向けに特化** — 汎用ERPの転用ではなく、小ロット・受注生産のワークフローに合わせて設計
- **アレルゲン & 栄養成分のトラッキング** — 原材料の追跡・栄養ラベル生成が必要な食品・飲料メーカーへの一流サポート
- **コストロールアップ付きBOMバージョン管理** — 完全な履歴と正確なコスト計算を維持しながらレシピや配合を改善
- **セルフホスト・ベンダーロックインなし** — データはPostgreSQLを基盤とした自分のインフラに保管

## ドキュメント

- [完全ドキュメント](https://puemos.github.io/craftplan/docs/)
- [APIリファレンス（JSON:API & GraphQL）](https://puemos.github.io/craftplan/docs/api/)

## コントリビューション

コントリビューションを歓迎します。大きな変更を加える場合は、まず[Issueを開いて](https://github.com/puemos/craftplan/issues)提案を議論してください。

```bash
mix test       # テストスイートを実行
mix format     # コードをフォーマット（Styler・Spark・Tailwind・HEEx）
```

コミットは以下の規約に従います: `type(scope): description`（例: `feat(batching):`・`fix(orders):`・`ui(production):`）

## ライセンス

このプロジェクトはAGPLv3ライセンスの下で提供されています。詳細は[LICENSE](LICENSE)ファイルを参照してください。

## サポート

- [Issueを開く](https://github.com/puemos/craftplan/issues)
- [ドキュメントを読む](https://puemos.github.io/craftplan/docs/)
