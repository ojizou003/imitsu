# アイミツ スクレイパー (imitsu Scraper)

「アイミツ（imitsu.jp）」から企業情報を自動的に収集するためのスクレイピングツール群です。
カテゴリ別に Jupyter Notebook が用意されており、必要な企業の詳細情報を CSV 形式で一括取得できます。

## 🚀 主な機能

- **詳細 URL の抽出**: 各カテゴリの検索結果ページから、企業詳細ページの URL を全件取得します。
- **企業情報の取得**: 詳細ページから以下の情報を抽出します。
  - 会社名
  - 設立年
  - 代表者名
  - 従業員数
  - 住所
  - 公式サイト URL
- **CSV 出力**: 取得したデータは、解析しやすいように CSV 形式（UTF-8 with BOM）で保存されます。

## 🛠️ 技術スタック

- **Language**: Python 3.11+
- **Package Manager**: [uv](https://github.com/astral-sh/uv)
- **Libraries**:
  - `BeautifulSoup4`: HTML 解析用
  - `Requests`: HTTP 通信用
  - `Pandas`: データフレーム処理・CSV 出力用
  - `tqdm`: 進捗状況の表示用
  - `Jupyter Notebook`: 実行環境

## 📦 セットアップ

このプロジェクトでは `uv` を使用して依存関係を管理しています。

1. **リポジトリのクローン**

   ```bash
   git clone <repository-url>
   cd imitsu
   ```

2. **依存関係のインストール**
   ```bash
   uv sync
   ```

## 📖 使用方法

各カテゴリに対応する `.ipynb` ファイル（Jupyter Notebook）を開き、セルを順番に実行してください。

1. **ノートブックの起動**

   ```bash
   uv run jupyter notebook
   ```

2. **対象カテゴリの選択**

   - `homepage.ipynb`: ホームページ制作
   - `system.ipynb`: システム開発
   - `app.ipynb`: アプリ開発
   - `movie.ipynb`: 動画制作
   - ...など、主要なカテゴリごとにファイルが分かれています。

3. **データの保存先**
   実行結果は `./data/` ディレクトリ内に CSV ファイルとして保存されます。

## ⚠️ 注意事項

- 本ツールは教育目的または個人利用を想定しています。
- スクレイピングを行う際は、対象サイトの `robots.txt` や利用規約を遵守し、サーバーに過度な負荷をかけないよう適切な待機時間（`sleep`）を設けてください（各ノートブックにはデフォルトで待機処理が含まれています）。
