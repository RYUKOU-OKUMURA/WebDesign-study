# レイアウト・構造

WEBページのレイアウトと構造に関する用語をまとめています。

## 目次
- [グリッドシステム](#グリッドシステム)
- [レスポンシブデザイン](#レスポンシブデザイン)
- [レイアウト手法](#レイアウト手法)
- [ページ構成要素](#ページ構成要素)
- [ナビゲーション](#ナビゲーション)

---

## グリッドシステム

### グリッド (Grid) ⭐⭐⭐
ページを規則的な格子状に分割するレイアウト手法。整然とした配置を実現します。

**構成要素:**
- **カラム (Column)**: 縦の分割
- **ロー (Row)**: 横の分割
- **ガター (Gutter)**: カラム間の余白
- **マージン (Margin)**: 外側の余白

**例:**
```css
.container {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 20px;
}
```

**関連用語:** [CSS Grid](#css-grid-⭐⭐⭐), [12カラムグリッド](#12カラムグリッド-⭐⭐)

### CSS Grid ⭐⭐⭐
CSSの2次元レイアウトシステム。行と列を同時に制御できます。

**主なプロパティ:**
```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: auto;
  gap: 16px;
}
```

**メリット:**
- 複雑なレイアウトが簡単
- レスポンシブ対応が容易
- コードの可読性向上

**関連用語:** [Flexbox](#flexbox-⭐⭐⭐), [グリッド](#グリッド-grid-⭐⭐⭐)

### 12カラムグリッド (12-Column Grid) ⭐⭐
ページを12等分するグリッドシステム。Bootstrapなどで採用されています。

**メリット:**
- 柔軟な分割が可能（2, 3, 4, 6等分）
- 業界標準
- フレームワークが豊富

**例:**
```html
<div class="row">
  <div class="col-6">50%幅</div>
  <div class="col-6">50%幅</div>
</div>
```

**関連用語:** [Bootstrap](#bootstrap-⭐⭐), [グリッド](#グリッド-grid-⭐⭐⭐)

### ガター (Gutter) ⭐⭐
グリッドのカラム間の余白。

**例:**
```css
.grid {
  display: grid;
  gap: 20px; /* ガター */
}
```

**関連用語:** [グリッド](#グリッド-grid-⭐⭐⭐), [余白](#余白-⭐⭐⭐)

---

## レスポンシブデザイン

### レスポンシブデザイン (Responsive Design) ⭐⭐⭐
画面サイズに応じてレイアウトを最適化するデザイン手法。

**原則:**
- 流動的なグリッド
- 柔軟な画像
- メディアクエリの使用

**メリット:**
- 様々なデバイスに対応
- メンテナンスコストの削減
- SEOに有利

**関連用語:** [メディアクエリ](#メディアクエリ-media-query-⭐⭐⭐), [ブレークポイント](#ブレークポイント-breakpoint-⭐⭐⭐)

### メディアクエリ (Media Query) ⭐⭐⭐
画面サイズや特性に応じてCSSを切り替える仕組み。

**例:**
```css
/* スマホ */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}

/* タブレット */
@media (min-width: 769px) and (max-width: 1024px) {
  .container {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* デスクトップ */
@media (min-width: 1025px) {
  .container {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

**関連用語:** [ブレークポイント](#ブレークポイント-breakpoint-⭐⭐⭐), [レスポンシブ](#レスポンシブデザイン-responsive-design-⭐⭐⭐)

### ブレークポイント (Breakpoint) ⭐⭐⭐
レイアウトが切り替わる画面サイズの境界値。

**一般的なブレークポイント:**
```css
/* モバイル */
320px - 480px

/* タブレット */
481px - 768px

/* 小型ラップトップ */
769px - 1024px

/* デスクトップ */
1025px - 1200px

/* 大型ディスプレイ */
1201px 以上
```

**関連用語:** [メディアクエリ](#メディアクエリ-media-query-⭐⭐⭐), [レスポンシブ](#レスポンシブデザイン-responsive-design-⭐⭐⭐)

### モバイルファースト (Mobile First) ⭐⭐⭐
スマホ向けのデザインから始めて、大きな画面に対応していく設計手法。

**メリット:**
- パフォーマンス優先
- 本質的な機能に集中
- 段階的な機能追加

**例:**
```css
/* デフォルト（モバイル） */
.container {
  flex-direction: column;
}

/* タブレット以上 */
@media (min-width: 768px) {
  .container {
    flex-direction: row;
  }
}
```

**関連用語:** [レスポンシブ](#レスポンシブデザイン-responsive-design-⭐⭐⭐), [プログレッシブエンハンスメント](#プログレッシブエンハンスメント-⭐)

### ビューポート (Viewport) ⭐⭐⭐
ブラウザの表示領域。レスポンシブデザインの基準となります。

**設定:**
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

**プロパティ:**
- `width`: ビューポートの幅
- `initial-scale`: 初期ズーム倍率
- `maximum-scale`: 最大ズーム倍率
- `user-scalable`: ユーザーによる拡大縮小の可否

**関連用語:** [レスポンシブ](#レスポンシブデザイン-responsive-design-⭐⭐⭐), [メタタグ](#メタタグ-⭐⭐)

### フルード/リキッドレイアウト (Fluid Layout) ⭐⭐
要素の幅をパーセンテージで指定し、画面サイズに応じて伸縮するレイアウト。

**例:**
```css
.container {
  width: 90%;
  max-width: 1200px;
}

.column {
  width: 50%;
}
```

**関連用語:** [レスポンシブ](#レスポンシブデザイン-responsive-design-⭐⭐⭐), [固定レイアウト](#固定レイアウト-⭐⭐)

---

## レイアウト手法

### Flexbox ⭐⭐⭐
1次元のレイアウトを作るCSSモジュール。行または列方向の配置に優れています。

**主なプロパティ:**
```css
.container {
  display: flex;
  justify-content: center;  /* 主軸の配置 */
  align-items: center;      /* 交差軸の配置 */
  gap: 16px;
}

.item {
  flex: 1;  /* 伸縮比率 */
}
```

**使用例:**
- ナビゲーションメニュー
- カードの並び
- 中央揃え

**関連用語:** [CSS Grid](#css-grid-⭐⭐⭐), [justify-content](#justify-content-⭐⭐)

### フロート (Float) ⭐⭐
要素を左右に寄せるCSS技法。昔はレイアウトに使われましたが、現在は画像回り込みなどに使用。

**例:**
```css
.image {
  float: left;
  margin-right: 16px;
}

.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

**関連用語:** [クリアフィックス](#クリアフィックス-⭐), [Flexbox](#flexbox-⭐⭐⭐)

### ポジショニング (Positioning) ⭐⭐⭐
要素の配置方法を指定するCSS。

**種類:**
```css
/* 通常のフロー */
position: static;

/* 相対位置 */
position: relative;
top: 10px;

/* 絶対位置 */
position: absolute;
top: 0;
right: 0;

/* 固定位置 */
position: fixed;
bottom: 20px;

/* スティッキー */
position: sticky;
top: 0;
```

**関連用語:** [z-index](#z-index-⭐⭐), [レイヤー](#レイヤー-⭐⭐)

### z-index ⭐⭐
要素の重なり順序を制御するプロパティ。数値が大きいほど前面に表示されます。

**例:**
```css
.modal {
  position: fixed;
  z-index: 1000;
}

.overlay {
  position: fixed;
  z-index: 999;
}
```

**注意:**
- `position: static`以外で有効
- 同一スタッキングコンテキスト内で比較される

**関連用語:** [ポジショニング](#ポジショニング-positioning-⭐⭐⭐), [レイヤー](#レイヤー-⭐⭐)

### カラム (Column) ⭐⭐⭐
縦に区切られたレイアウトの単位。新聞のような段組みレイアウトも可能。

**グリッドでの使用:**
```css
.grid {
  grid-template-columns: repeat(3, 1fr);
}
```

**マルチカラムレイアウト:**
```css
.text {
  column-count: 3;
  column-gap: 40px;
}
```

**関連用語:** [グリッド](#グリッド-grid-⭐⭐⭐), [CSS Grid](#css-grid-⭐⭐⭐)

---

## ページ構成要素

### ヘッダー (Header) ⭐⭐⭐
ページ上部の領域。ロゴ、ナビゲーション、検索などを配置します。

**HTML:**
```html
<header>
  <div class="logo">サイト名</div>
  <nav>
    <ul>
      <li><a href="#">ホーム</a></li>
      <li><a href="#">サービス</a></li>
    </ul>
  </nav>
</header>
```

**関連用語:** [ナビゲーション](#ナビゲーション-⭐⭐⭐), [ロゴ](#ロゴ-⭐⭐⭐)

### フッター (Footer) ⭐⭐⭐
ページ下部の領域。著作権情報、リンク、SNSアイコンなどを配置します。

**HTML:**
```html
<footer>
  <div class="footer-links">
    <a href="#">プライバシーポリシー</a>
    <a href="#">お問い合わせ</a>
  </div>
  <p>&copy; 2024 会社名</p>
</footer>
```

**関連用語:** [著作権](#著作権-⭐⭐), [サイトマップ](#サイトマップ-⭐⭐)

### サイドバー (Sidebar) ⭐⭐
メインコンテンツの横に配置される補助的な領域。

**用途:**
- ナビゲーション
- 広告
- 関連記事
- カテゴリー一覧

**例:**
```css
.layout {
  display: grid;
  grid-template-columns: 250px 1fr;
}

.sidebar {
  background: #f5f5f5;
}
```

**関連用語:** [メインコンテンツ](#メインコンテンツ-⭐⭐⭐), [レイアウト](#レイアウト-⭐⭐⭐)

### メインコンテンツ (Main Content) ⭐⭐⭐
ページの主要な内容を含む領域。

**HTML:**
```html
<main>
  <article>
    <h1>記事タイトル</h1>
    <p>本文...</p>
  </article>
</main>
```

**関連用語:** [セクション](#セクション-section-⭐⭐), [article](#article-⭐⭐)

### セクション (Section) ⭐⭐
内容のまとまりを表す領域。テーマごとに区切ります。

**HTML:**
```html
<section>
  <h2>セクションタイトル</h2>
  <p>セクションの内容...</p>
</section>
```

**関連用語:** [article](#article-⭐⭐), [セマンティックHTML](#セマンティックhtml-⭐⭐)

### ヒーロー (Hero) ⭐⭐⭐
ページ最上部の大きな画像やビジュアルエリア。第一印象を決定づけます。

**例:**
```html
<section class="hero">
  <h1>キャッチコピー</h1>
  <p>サブタイトル</p>
  <button>詳しく見る</button>
</section>
```

```css
.hero {
  height: 100vh;
  background-image: url('hero.jpg');
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

**関連用語:** [ファーストビュー](#ファーストビュー-⭐⭐⭐), [CTA](#cta-⭐⭐⭐)

### カード (Card) ⭐⭐⭐
情報をまとめた矩形の要素。画像、タイトル、説明などを含みます。

**例:**
```html
<div class="card">
  <img src="thumbnail.jpg" alt="">
  <div class="card-body">
    <h3>カードタイトル</h3>
    <p>説明文...</p>
    <a href="#">詳細を見る</a>
  </div>
</div>
```

```css
.card {
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  overflow: hidden;
}
```

**関連用語:** [グリッド](#グリッド-grid-⭐⭐⭐), [シャドウ](#シャドウ-shadow-⭐⭐)

### モーダル (Modal) ⭐⭐⭐
ページ上に重なって表示されるダイアログウィンドウ。

**用途:**
- ログインフォーム
- 画像の拡大表示
- 確認ダイアログ
- 追加情報の表示

**例:**
```html
<div class="modal">
  <div class="modal-content">
    <span class="close">&times;</span>
    <h2>モーダルタイトル</h2>
    <p>内容...</p>
  </div>
</div>
```

```css
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  z-index: 1000;
}
```

**関連用語:** [オーバーレイ](#オーバーレイ-⭐⭐), [z-index](#z-index-⭐⭐)

---

## ナビゲーション

### ナビゲーション (Navigation) ⭐⭐⭐
サイト内を移動するためのメニューやリンク。

**種類:**
- グローバルナビゲーション
- ローカルナビゲーション
- パンくずリスト
- フッターナビゲーション

**HTML:**
```html
<nav>
  <ul>
    <li><a href="#">ホーム</a></li>
    <li><a href="#">サービス</a></li>
    <li><a href="#">会社概要</a></li>
  </ul>
</nav>
```

**関連用語:** [メニュー](#メニュー-⭐⭐⭐), [リンク](#リンク-⭐⭐⭐)

### ハンバーガーメニュー (Hamburger Menu) ⭐⭐⭐
3本線のアイコンで表されるモバイル用メニュー。タップで展開します。

**例:**
```html
<button class="hamburger">
  <span></span>
  <span></span>
  <span></span>
</button>
```

```css
.hamburger span {
  display: block;
  width: 25px;
  height: 3px;
  background: black;
  margin: 5px 0;
}
```

**関連用語:** [モバイルファースト](#モバイルファースト-mobile-first-⭐⭐⭐), [ナビゲーション](#ナビゲーション-navigation-⭐⭐⭐)

### パンくずリスト (Breadcrumb) ⭐⭐
現在のページ位置を階層的に示すナビゲーション。

**例:**
```html
<nav aria-label="パンくずリスト">
  <ol class="breadcrumb">
    <li><a href="/">ホーム</a></li>
    <li><a href="/category">カテゴリー</a></li>
    <li>現在のページ</li>
  </ol>
</nav>
```

**メリット:**
- ユーザーの現在地把握
- SEOに有利
- 上位階層への移動が容易

**関連用語:** [ナビゲーション](#ナビゲーション-navigation-⭐⭐⭐), [階層構造](#階層構造-⭐⭐)

### ドロップダウンメニュー (Dropdown Menu) ⭐⭐
ホバーやクリックで表示されるサブメニュー。

**例:**
```html
<nav>
  <ul>
    <li>
      <a href="#">サービス</a>
      <ul class="dropdown">
        <li><a href="#">サービス1</a></li>
        <li><a href="#">サービス2</a></li>
      </ul>
    </li>
  </ul>
</nav>
```

```css
.dropdown {
  display: none;
  position: absolute;
}

li:hover .dropdown {
  display: block;
}
```

**関連用語:** [ナビゲーション](#ナビゲーション-navigation-⭐⭐⭐), [ホバー](#ホバー-hover-⭐⭐)

### タブナビゲーション (Tab Navigation) ⭐⭐
タブを切り替えてコンテンツを表示するインターフェース。

**例:**
```html
<div class="tabs">
  <button class="tab active">タブ1</button>
  <button class="tab">タブ2</button>
  <button class="tab">タブ3</button>
</div>

<div class="tab-content">
  <div class="panel active">コンテンツ1</div>
  <div class="panel">コンテンツ2</div>
  <div class="panel">コンテンツ3</div>
</div>
```

**用途:**
- 情報の整理
- スペースの節約
- 関連情報のグループ化

**関連用語:** [UI](#ui-⭐⭐⭐), [インタラクション](#インタラクション-⭐⭐)

### ページネーション (Pagination) ⭐⭐
複数ページに分割されたコンテンツを移動するインターフェース。

**例:**
```html
<nav class="pagination">
  <a href="#">前へ</a>
  <a href="#">1</a>
  <a href="#" class="active">2</a>
  <a href="#">3</a>
  <a href="#">次へ</a>
</nav>
```

**関連用語:** [ナビゲーション](#ナビゲーション-navigation-⭐⭐⭐), [無限スクロール](#無限スクロール-⭐)

---

## その他のレイアウト用語

### コンテナ (Container) ⭐⭐⭐
コンテンツを囲む外枠の要素。最大幅を設定して中央配置することが多いです。

**例:**
```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}
```

**関連用語:** [ラッパー](#ラッパー-⭐⭐), [レイアウト](#レイアウト-⭐⭐⭐)

### ラッパー (Wrapper) ⭐⭐
要素をまとめて囲む要素。コンテナと同義で使われることも。

**例:**
```html
<div class="wrapper">
  <header>...</header>
  <main>...</main>
  <footer>...</footer>
</div>
```

**関連用語:** [コンテナ](#コンテナ-container-⭐⭐⭐)

### ファーストビュー (First View / Above the Fold) ⭐⭐⭐
スクロールせずに最初に見える領域。

**重要性:**
- 第一印象を決定
- 離脱率に影響
- CTAの配置場所

**最適化:**
- 魅力的なビジュアル
- 明確なメッセージ
- CTAの配置
- 読み込み速度の最適化

**関連用語:** [ヒーロー](#ヒーロー-hero-⭐⭐⭐), [CTA](#cta-⭐⭐⭐)

### スティッキーヘッダー (Sticky Header) ⭐⭐
スクロールしても画面上部に固定されるヘッダー。

**例:**
```css
header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

**メリット:**
- ナビゲーションへの常時アクセス
- ブランディング
- UXの向上

**関連用語:** [ポジショニング](#ポジショニング-positioning-⭐⭐⭐), [ヘッダー](#ヘッダー-header-⭐⭐⭐)

---

## より詳しく学ぶ

次のステップ:
- [色・タイポグラフィ](./04-color-typography.md) - 色とフォントを学ぶ
- [技術・実装](./06-technical.md) - 実装方法を学ぶ
- [基礎用語](./01-basics.md) - CSS Gridなどの基礎を復習

[用語集トップに戻る](./README.md)
