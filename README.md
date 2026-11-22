# 40代からのAI副業ノート

介護施設主任「介護AIおじさん」のアフィリエイト専用サイト（GitHub Pages、素のHTML/CSS、ビルドなし）。
公開URL： https://hideki810.github.io/ai-fukugyo-note/

## 構成
- `index.html`：トップ
- `tax/` `ai-tools/` `care-work/` `money/`：カテゴリページ
- `about/` `pr-policy/` `privacy/` `contact/`：必須ページ
- `articles/`：記事置き場（`_template.html` が記事テンプレート）
- `assets/css/style.css`：共通スタイル

## 記事の追加手順
1. `articles/_template.html` を `articles/<slug>.html` にコピーして本文を書く
   - アフィリエイトリンクを含む記事はPRボックスを必ず残す
   - 未使用のサービスを「使ってみた」と書かない（運営ルール）
2. 該当カテゴリページの「記事一覧」にリンクを追加する
3. トップページの「最新記事」にもリンクを追加する
4. `sitemap.xml` に記事URLを追加する
5. GitHubへ反映（push）すると GitHub Pages に自動で公開される

## 公開前チェック（運営ルール）
- 実践したことだけ書いているか／盛っていないか
- PR表記があるか
- 勤務先の施設名・利用者情報が含まれていないか
