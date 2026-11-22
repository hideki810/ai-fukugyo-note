# 40代からのAI副業ノート

本業を持つ40代が、実際に試したAI活用・副業・確定申告の実践だけを記録する静的サイトです。HTMLとCSSだけで構成しています。

公開URL：<https://hideki810.github.io/ai-fukugyo-note/>

## ファイル構成

```text
index.html                 トップページ
about/index.html           プロフィール
pr-policy/index.html       広告ポリシー
privacy/index.html         プライバシーポリシー・免責
contact/index.html         お問い合わせ
tax/index.html             確定申告・会計ソフト
ai-tools/index.html        AIツール・業務効率化
care-work/index.html       介護の働き方・転職
money/index.html           副業・お金の実践記
articles/_template.html    記事テンプレート
assets/css/style.css       共通スタイル
sitemap.xml                サイトマップ
robots.txt                 クローラー向け設定
```

## 記事の追加手順

1. `articles/_template.html` を `articles/記事名.html` にコピーします。
2. `noindex` の行を削除します。
3. `title`、`description`、`og:title`、`og:description`、`og:url`、`canonical`、公開日・更新日、本文を書き換えます（広告が無い記事では PR 表記枠と上部CTA枠を削除）。
4. パンくずHTMLと `BreadcrumbList` JSON-LD の2番目（カテゴリ名とURL）・3番目（記事名とURL）を書き換えます。
5. `Article` JSON-LD の `headline`、`datePublished`、`dateModified` を書き換えます（画像を使う場合は `image` プロパティに絶対URLを追加）。
6. 目次のリンク先（`#sec-1` 等）と本文の章見出し（`h2`）の `id` を一致させます。
7. 該当カテゴリページの記事一覧と、トップの最新記事欄にリンクを追加します。
8. 準備中表示を外します。
9. `sitemap.xml` に記事URLを追加します。

## PR表記ルール

広告リンクを含む記事の冒頭には「PR」と表記し、広告リンクだと分かるようにします。リンク経由の購入・申込みで運営者に報酬が発生する場合があります。評価やランキングは、報酬の有無で変えません。詳しくは [広告ポリシー](pr-policy/index.html) を確認してください。

## 追加部品の使い方（コピペ用HTML断片）

### 大ボタン（CTA・PRラベル・マイクロコピー付き）

広告リンクの場合はボタン直前に PR ラベルを置き、`rel="sponsored noopener"` を維持します。

```html
<div class="cta">
  <span class="button-label">PR（広告リンク）</span>
  <p>案内文をここに入れます。</p>
  <a class="button" href="https://example.com" rel="sponsored noopener">公式ページを見る</a>
  <p class="cta-microcopy">公式ページで最新条件を確認できます</p>
</div>
```

### 小ボタン（テキストリンク型）

文章の流れの中で控えめにリンクを置く場合に使います。

```html
<p><a class="small-button" href="https://example.com" rel="sponsored noopener">詳細を見る（PR）</a></p>
```

### 比較表（スマホ横スクロール対応）

ページ全体が横スクロールしないよう、必ず `.table-scroll` で囲みます。

```html
<div class="table-scroll">
  <table>
    <thead>
      <tr><th>項目</th><th>選択肢A</th><th>選択肢B</th></tr>
    </thead>
    <tbody>
      <tr><td>特徴</td><td>内容A</td><td>内容B</td></tr>
    </tbody>
  </table>
</div>
```

### 結論ボックス・「この記事で分かること」

```html
<section class="key-points">
  <h2>この記事で分かること</h2>
  <ul>
    <li>要点1</li>
    <li>要点2</li>
    <li>要点3</li>
  </ul>
</section>

<section class="conclusion-box">
  <h2>結論</h2>
  <p>結論を先に書きます。</p>
</section>
```

### 目次

記事内の `h2` に `id="sec-1"` 等を付けてリンクします。

```html
<nav class="toc" aria-label="目次">
  <h2>目次</h2>
  <ol>
    <li><a href="#sec-1">見出し1</a></li>
    <li><a href="#sec-2">見出し2</a></li>
  </ol>
</nav>
```

### note枠・引用

```html
<aside class="note-box">
  <p>補足や注意書きをここに入れます。</p>
</aside>

<blockquote>
  <p>引用文をここに入れます。</p>
</blockquote>
```

### 関連カード（「次に読む」）

```html
<section>
  <h2>次に読む</h2>
  <div class="related-grid">
    <article class="card">
      <span class="category-chip">関連記事</span>
      <h3>記事タイトル1</h3>
      <p>記事の要約</p>
      <a class="text-link" href="./other-article.html">記事を読む</a>
    </article>
    <article class="card">
      <span class="category-chip">関連記事</span>
      <h3>記事タイトル2</h3>
      <p>記事の要約</p>
      <a class="text-link" href="../tax/index.html">カテゴリを見る</a>
    </article>
  </div>
</section>
```

### 著者ボックス

```html
<aside class="author-box">
  <p class="eyebrow">Author</p>
  <h2>この記事を書いた人：介護AIおじさん</h2>
  <p>40代後半・大阪市在住。介護施設の主任として勤務する介護福祉士です。本業を持ちながら、実践したことと、申し込む前に調べたことを分けて記録しています。</p>
  <p><a href="../about/index.html">プロフィール・運営者情報を見る</a></p>
  <ul class="social-links">
    <li><a href="https://note.com/kaigo_ai_ojisan" target="_blank" rel="noopener noreferrer">note</a></li>
    <li><a href="https://x.com/kaigoaiojisan" target="_blank" rel="noopener noreferrer">X</a></li>
    <li><a href="https://www.instagram.com/kaigo.ai.ojisan" target="_blank" rel="noopener noreferrer">Instagram</a></li>
  </ul>
</aside>
```

### パンくずリスト＋構造化データ（JSON-LD）

トップ以外の全ページにパンくず表示と `BreadcrumbList` の JSON-LD を入れます。JSON-LD の `item` は `https://hideki810.github.io/ai-fukugyo-note/` 基点の絶対URL（`og:url` と一致）にします。

```html
<nav class="breadcrumb" aria-label="パンくずリスト">
  <ol>
    <li><a href="../index.html">トップ</a></li>
    <li><a href="../ai-tools/index.html">カテゴリ名</a></li>
    <li aria-current="page">記事タイトル</li>
  </ol>
</nav>
```

```html
<script type="application/ld+json">
{"@context":"https://schema.org","@type":"BreadcrumbList","itemListElement":[{"@type":"ListItem","position":1,"name":"トップ","item":"https://hideki810.github.io/ai-fukugyo-note/"},{"@type":"ListItem","position":2,"name":"カテゴリ名","item":"https://hideki810.github.io/ai-fukugyo-note/ai-tools/"},{"@type":"ListItem","position":3,"name":"記事タイトル","item":"https://hideki810.github.io/ai-fukugyo-note/articles/記事名.html"}]}
</script>
```

記事ページでは `Article` の JSON-LD も `<head>` に置きます（FAQPage・Review・AggregateRating・星評価は入れません）。

```html
<script type="application/ld+json">
{"@context":"https://schema.org","@type":"Article","headline":"記事タイトル","datePublished":"2026-11-23","dateModified":"2026-11-23","author":{"@type":"Person","name":"介護AIおじさん","url":"https://hideki810.github.io/ai-fukugyo-note/about/"},"publisher":{"@type":"Organization","name":"40代からのAI副業ノート","url":"https://hideki810.github.io/ai-fukugyo-note/"}}
</script>
```

## 画像を使う場合のルール

- 外部画像は使わず、リポジトリ内の画像（例：`../assets/img/...`）を使います。
- CLS（レイアウトシフト）を防ぐため、`<img>` には必ず `width` と `height` 属性を指定します。
- 本文中の画像には `loading="lazy"` を付けます。
- ファーストビューに入る画像には `loading="lazy"` を付けません（LCP 悪化を防ぐため）。
