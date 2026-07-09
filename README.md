# あさかつ スタンプカード

朝活（Zoom）に来てくれた子に、主催者がスタンプを押す → 子ども・保護者がオンラインで自分のカードを見て喜べる、をオンラインだけで完結させる仕組みです。夏休みのラジオ体操スタンプカードのWeb版。

- **子ども向けカード**: `index.html` … あいことばを入れると自分のカードが表示され、今日のスタンプが「ポン！」と押される演出＋効果音。節目でごほうびバッジ（🌱→🌿→🌷→🌸→🌳）
- **管理ページ**: `admin.html` … 朝活中にスマホで名前をタップしてスタンプを押す（主催者専用）
- **バックエンド**: Google スプレッドシート + Google Apps Script（`gas/Code.gs`）… すべて無料

## セットアップ

[SETUP.md](SETUP.md) を参照。スプレッドシート作成 → GAS デプロイ → URL 設定 → GitHub Pages 公開、の順で10〜15分です。

## デモ

デプロイ前でも `index.html?demo=1` / `admin.html?demo=1` でサンプルデータで動きを確認できます。

## 開発

- 素の HTML/CSS/JS（ビルド不要）。ロジックは `stamp-logic.js`（UMD）に分離
- テスト: `node --test stamp-logic.test.mjs`
- `main` への push で GitHub Actions がテスト実行後、GitHub Pages へ自動デプロイ
