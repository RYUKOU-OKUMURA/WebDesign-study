# 技術・実装

WEBデザインの技術的な実装に関する用語をまとめています。

## 目次
- [CSS設計手法](#css設計手法)
- [アニメーション](#アニメーション)
- [パフォーマンス](#パフォーマンス)
- [画像・メディア](#画像メディア)
- [フレームワーク・ツール](#フレームワークツール)
- [モダンCSS](#モダンcss)

---

## CSS設計手法

### BEM (Block Element Modifier) ⭐⭐
CSS設計手法の一つ。クラス名の命名規則を定めます。

**命名規則:**
```css
/* Block */
.card { }

/* Element */
.card__title { }
.card__body { }
.card__image { }

/* Modifier */
.card--featured { }
.card__title--large { }
```

**HTML:**
```html
<div class="card card--featured">
  <img class="card__image" src="image.jpg">
  <h3 class="card__title card__title--large">タイトル</h3>
  <p class="card__body">本文</p>
</div>
```

**メリット:**
- 命名が明確
- 影響範囲が分かりやすい
- 保守性が高い

**関連用語:** [CSS設計](#css設計-⭐⭐), [命名規則](#命名規則-⭐⭐)

### CSS変数 (Custom Properties) ⭐⭐⭐
CSSで使える変数。値を一箇所で管理できます。

**定義:**
```css
:root {
  --primary-color: #007bff;
  --secondary-color: #6c757d;
  --spacing-unit: 8px;
  --border-radius: 4px;
}
```

**使用:**
```css
.button {
  background: var(--primary-color);
  padding: calc(var(--spacing-unit) * 2);
  border-radius: var(--border-radius);
}

/* フォールバック値 */
.button {
  color: var(--text-color, black);
}
```

**メリット:**
- 一元管理
- テーマ切り替えが容易
- JavaScriptから変更可能

**関連用語:** [CSS](#css-⭐⭐⭐), [テーマ](#テーマ-⭐⭐)

### リセットCSS (CSS Reset) ⭐⭐
ブラウザのデフォルトスタイルを初期化するCSS。

**例:**
```css
/* シンプルなリセット */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* または normalize.css を使用 */
```

**目的:**
- ブラウザ間の差異を解消
- 予測可能なスタイリング
- 一貫性のある表示

**関連用語:** [Normalize.css](#normalizecss-⭐⭐), [クロスブラウザ](#クロスブラウザ-⭐⭐)

### Normalize.css ⭐⭐
ブラウザのスタイルを統一するCSS。リセットよりも穏やか。

**特徴:**
- 有用なデフォルトスタイルを保持
- ブラウザのバグを修正
- モジュール化されている

**使用:**
```html
<link rel="stylesheet" href="normalize.css">
```

**関連用語:** [リセットCSS](#リセットcss-css-reset-⭐⭐), [クロスブラウザ](#クロスブラウザ-⭐⭐)

### CSS Modules ⭐
CSSをモジュール化してスコープを限定する手法。

**例:**
```css
/* Button.module.css */
.button {
  background: blue;
}

.primary {
  background: red;
}
```

```javascript
// React での使用例
import styles from './Button.module.css';

function Button() {
  return (
    <button className={styles.button}>
      ボタン
    </button>
  );
}
```

**メリット:**
- クラス名の衝突を防ぐ
- スコープが明確
- 保守性が高い

**関連用語:** [BEM](#bem-block-element-modifier-⭐⭐), [CSS-in-JS](#css-in-js-⭐)

---

## アニメーション

### アニメーション (Animation) ⭐⭐
要素に動きを付ける技術。

**CSS アニメーション:**
```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.element {
  animation: fadeIn 1s ease-out;
}
```

**用途:**
- 注意を引く
- 状態変化を示す
- UXの向上
- ブランディング

**関連用語:** [トランジション](#トランジション-transition-⭐⭐), [キーフレーム](#キーフレーム-keyframes-⭐⭐)

### トランジション (Transition) ⭐⭐
プロパティの変化を滑らかにする効果。

**基本:**
```css
.button {
  background: blue;
  transition: background 0.3s ease;
}

.button:hover {
  background: darkblue;
}
```

**詳細設定:**
```css
.element {
  transition-property: all;
  transition-duration: 0.3s;
  transition-timing-function: ease-in-out;
  transition-delay: 0.1s;

  /* 短縮形 */
  transition: all 0.3s ease-in-out 0.1s;
}
```

**複数プロパティ:**
```css
.element {
  transition:
    background 0.3s ease,
    transform 0.2s ease-out;
}
```

**関連用語:** [アニメーション](#アニメーション-animation-⭐⭐), [イージング](#イージング-⭐⭐)

### キーフレーム (Keyframes) ⭐⭐
アニメーションの各段階を定義する。

**例:**
```css
@keyframes slideIn {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  50% {
    opacity: 0.5;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

.element {
  animation: slideIn 1s ease-out;
}
```

**複雑な例:**
```css
@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-30px);
  }
  60% {
    transform: translateY(-15px);
  }
}
```

**関連用語:** [アニメーション](#アニメーション-animation-⭐⭐)

### トランスフォーム (Transform) ⭐⭐⭐
要素の変形・移動・回転・拡大縮小。

**種類:**
```css
/* 移動 */
transform: translate(50px, 100px);
transform: translateX(50px);
transform: translateY(100px);

/* 回転 */
transform: rotate(45deg);

/* 拡大縮小 */
transform: scale(1.5);
transform: scale(2, 0.5); /* X軸2倍、Y軸0.5倍 */

/* 傾斜 */
transform: skew(10deg, 5deg);

/* 複数組み合わせ */
transform: translate(50px, 100px) rotate(45deg) scale(1.2);
```

**3D変形:**
```css
transform: perspective(1000px) rotateY(45deg);
transform: translate3d(50px, 100px, 0);
```

**関連用語:** [アニメーション](#アニメーション-animation-⭐⭐), [3D](#3d-⭐)

### イージング (Easing) ⭐⭐
アニメーションの速度曲線。

**種類:**
```css
/* 基本 */
transition: all 0.3s linear;       /* 一定速度 */
transition: all 0.3s ease;         /* 開始と終了が緩やか */
transition: all 0.3s ease-in;      /* 開始が緩やか */
transition: all 0.3s ease-out;     /* 終了が緩やか */
transition: all 0.3s ease-in-out;  /* 両端が緩やか */

/* カスタム（ベジェ曲線） */
transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
```

**一般的なイージング:**
```css
/* Material Design の easing */
--ease-standard: cubic-bezier(0.4, 0, 0.2, 1);
--ease-decelerate: cubic-bezier(0, 0, 0.2, 1);
--ease-accelerate: cubic-bezier(0.4, 0, 1, 1);
```

**関連用語:** [トランジション](#トランジション-transition-⭐⭐), [アニメーション](#アニメーション-animation-⭐⭐)

---

## パフォーマンス

### パフォーマンス (Performance) ⭐⭐⭐
WEBサイトの速度や効率性。

**重要な指標:**
- 読み込み時間
- 応答速度
- 描画速度
- インタラクティブになるまでの時間

**最適化方法:**
- 画像の圧縮
- CSSとJavaScriptの最小化
- 遅延読み込み
- キャッシュの活用

**関連用語:** [最適化](#最適化-optimization-⭐⭐), [Core Web Vitals](#core-web-vitals-⭐⭐)

### Core Web Vitals ⭐⭐
Googleが定めるWEBページのUX指標。

**3つの指標:**
1. **LCP (Largest Contentful Paint)**
   - 最大コンテンツの描画時間
   - 目標: 2.5秒以内

2. **FID (First Input Delay)**
   - 最初の入力への応答時間
   - 目標: 100ミリ秒以内

3. **CLS (Cumulative Layout Shift)**
   - レイアウトのずれ
   - 目標: 0.1以下

**関連用語:** [パフォーマンス](#パフォーマンス-performance-⭐⭐⭐), [最適化](#最適化-optimization-⭐⭐)

### 遅延読み込み (Lazy Loading) ⭐⭐
必要になるまで読み込みを遅らせる技術。

**画像の遅延読み込み:**
```html
<!-- ネイティブ対応 -->
<img src="image.jpg" loading="lazy" alt="画像">

<!-- Intersection Observer API -->
<img data-src="image.jpg" class="lazy" alt="画像">

<script>
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const img = entry.target;
      img.src = img.dataset.src;
      observer.unobserve(img);
    }
  });
});

document.querySelectorAll('.lazy').forEach(img => {
  observer.observe(img);
});
</script>
```

**メリット:**
- 初期読み込みの高速化
- データ使用量の削減
- パフォーマンスの向上

**関連用語:** [パフォーマンス](#パフォーマンス-performance-⭐⭐⭐), [画像最適化](#画像最適化-⭐⭐)

### ミニファイ (Minify) ⭐⭐
コードから不要な文字を削除してファイルサイズを削減。

**例（CSS）:**
```css
/* オリジナル */
.button {
  background-color: blue;
  padding: 10px 20px;
  border-radius: 4px;
}

/* ミニファイ後 */
.button{background-color:blue;padding:10px 20px;border-radius:4px}
```

**削除されるもの:**
- 空白
- 改行
- コメント
- 不要なコード

**ツール:**
- UglifyJS (JavaScript)
- cssnano (CSS)
- HTMLMinifier (HTML)

**関連用語:** [最適化](#最適化-optimization-⭐⭐), [バンドル](#バンドル-⭐⭐)

### キャッシュ (Cache) ⭐⭐⭐
データを一時的に保存して再利用する仕組み。

**種類:**
- ブラウザキャッシュ
- CDNキャッシュ
- サーバーサイドキャッシュ

**設定（HTTPヘッダー）:**
```
Cache-Control: max-age=31536000, public
```

**HTML:**
```html
<link rel="preload" href="style.css" as="style">
<link rel="prefetch" href="next-page.html">
```

**メリット:**
- 読み込み速度の向上
- サーバー負荷の軽減
- データ使用量の削減

**関連用語:** [パフォーマンス](#パフォーマンス-performance-⭐⭐⭐), [CDN](#cdn-⭐⭐)

---

## 画像・メディア

### レスポンシブ画像 (Responsive Images) ⭐⭐
画面サイズに応じて最適な画像を表示。

**srcset属性:**
```html
<img
  src="image-400.jpg"
  srcset="
    image-400.jpg 400w,
    image-800.jpg 800w,
    image-1200.jpg 1200w
  "
  sizes="(max-width: 600px) 400px, 800px"
  alt="レスポンシブ画像"
>
```

**picture要素:**
```html
<picture>
  <source
    media="(min-width: 800px)"
    srcset="large.jpg"
  >
  <source
    media="(min-width: 400px)"
    srcset="medium.jpg"
  >
  <img src="small.jpg" alt="画像">
</picture>
```

**関連用語:** [レスポンシブデザイン](#レスポンシブデザイン-⭐⭐⭐), [画像最適化](#画像最適化-⭐⭐)

### WebP ⭐⭐
Googleが開発した次世代画像フォーマット。JPEGやPNGより高圧縮。

**使用:**
```html
<picture>
  <source srcset="image.webp" type="image/webp">
  <source srcset="image.jpg" type="image/jpeg">
  <img src="image.jpg" alt="画像">
</picture>
```

**メリット:**
- 高圧縮率
- 透過対応
- アニメーション対応

**関連用語:** [画像フォーマット](#画像フォーマット-⭐⭐), [最適化](#最適化-optimization-⭐⭐)

### SVG (Scalable Vector Graphics) ⭐⭐
拡大縮小しても劣化しないベクター画像。

**使用方法:**
```html
<!-- インライン -->
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" fill="blue" />
</svg>

<!-- img タグ -->
<img src="icon.svg" alt="アイコン">

<!-- CSS -->
.icon {
  background-image: url('icon.svg');
}
```

**メリット:**
- 拡大しても鮮明
- ファイルサイズが小さい
- CSSで色を変更可能
- アニメーション可能

**用途:**
- ロゴ
- アイコン
- イラスト
- グラフ

**関連用語:** [ベクター](#ベクター-⭐⭐), [アイコン](#アイコン-⭐⭐⭐)

### 画像最適化 (Image Optimization) ⭐⭐
画像のファイルサイズを削減してパフォーマンスを向上。

**手法:**
- 適切なフォーマット選択
- 圧縮
- リサイズ
- 遅延読み込み
- レスポンシブ画像

**フォーマット選択:**
- 写真: JPEG / WebP
- 透過: PNG / WebP
- アイコン: SVG
- アニメーション: GIF / WebP

**ツール:**
- ImageOptim
- TinyPNG
- Squoosh

**関連用語:** [パフォーマンス](#パフォーマンス-performance-⭐⭐⭐), [WebP](#webp-⭐⭐)

### アスペクト比 (Aspect Ratio) ⭐⭐
画像や要素の縦横比。

**CSS実装:**
```css
/* 16:9 の比率 */
.video-container {
  aspect-ratio: 16 / 9;
}

/* 1:1 (正方形) */
.square {
  aspect-ratio: 1 / 1;
}

/* 旧ブラウザ対応 */
.video-container-legacy {
  position: relative;
  padding-bottom: 56.25%; /* 9/16 * 100% */
}

.video-container-legacy iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```

**関連用語:** [レスポンシブ](#レスポンシブデザイン-⭐⭐⭐), [比率](#比率-⭐⭐)

---

## フレームワーク・ツール

### フレームワーク (Framework) ⭐⭐⭐
開発を効率化するための基盤となるツール。

**CSSフレームワーク:**
- Bootstrap
- Tailwind CSS
- Bulma
- Foundation

**JavaScriptフレームワーク:**
- React
- Vue.js
- Angular

**メリット:**
- 開発速度の向上
- 一貫性のあるデザイン
- ベストプラクティスの適用
- コミュニティのサポート

**関連用語:** [ライブラリ](#ライブラリ-⭐⭐), [Bootstrap](#bootstrap-⭐⭐)

### Bootstrap ⭐⭐
最も人気のあるCSSフレームワーク。

**使用:**
```html
<link href="bootstrap.min.css" rel="stylesheet">

<div class="container">
  <div class="row">
    <div class="col-md-6">左カラム</div>
    <div class="col-md-6">右カラム</div>
  </div>
</div>

<button class="btn btn-primary">ボタン</button>
```

**特徴:**
- 12カラムグリッド
- 豊富なコンポーネント
- レスポンシブ対応
- カスタマイズ可能

**関連用語:** [フレームワーク](#フレームワーク-framework-⭐⭐⭐), [グリッド](#グリッド-⭐⭐⭐)

### Tailwind CSS ⭐⭐
ユーティリティファーストのCSSフレームワーク。

**使用:**
```html
<div class="flex items-center justify-center h-screen bg-gray-100">
  <div class="bg-white p-8 rounded-lg shadow-md">
    <h1 class="text-2xl font-bold text-gray-800 mb-4">
      タイトル
    </h1>
    <p class="text-gray-600">
      説明文
    </p>
    <button class="mt-4 px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
      ボタン
    </button>
  </div>
</div>
```

**特徴:**
- HTMLにスタイルを直接記述
- 高速な開発
- カスタマイズ性が高い
- 未使用のCSSを削除可能

**関連用語:** [ユーティリティファースト](#ユーティリティファースト-⭐), [フレームワーク](#フレームワーク-framework-⭐⭐⭐)

### Sass/SCSS ⭐⭐
CSSを拡張したメタ言語。変数、ネスト、関数などが使えます。

**例:**
```scss
// 変数
$primary-color: #007bff;
$spacing: 16px;

// ネスト
.card {
  padding: $spacing;
  background: white;

  &__title {
    color: $primary-color;
    font-size: 24px;
  }

  &:hover {
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  }
}

// ミックスイン
@mixin flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  @include flex-center;
}
```

**メリット:**
- DRY原則の実現
- 保守性の向上
- 計算機能
- 再利用可能なコード

**関連用語:** [プリプロセッサ](#プリプロセッサ-⭐⭐), [CSS](#css-⭐⭐⭐)

### プリプロセッサ (Preprocessor) ⭐⭐
CSSやJavaScriptを拡張する言語。コンパイルして標準のコードに変換します。

**CSS プリプロセッサ:**
- Sass/SCSS
- Less
- Stylus

**JavaScript プリプロセッサ:**
- TypeScript
- CoffeeScript

**メリット:**
- 高度な機能
- 効率的な記述
- エラーの検出

**関連用語:** [Sass](#sassscss-⭐⭐), [TypeScript](#typescript-⭐⭐)

---

## モダンCSS

### CSS Grid ⭐⭐⭐
2次元レイアウトを作成するCSSモジュール。

**基本:**
```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
}
```

**詳細な例:**
```css
.layout {
  display: grid;
  grid-template-columns: 200px 1fr 200px;
  grid-template-rows: auto 1fr auto;
  grid-template-areas:
    "header header header"
    "sidebar main aside"
    "footer footer footer";
  gap: 20px;
  height: 100vh;
}

.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.aside { grid-area: aside; }
.footer { grid-area: footer; }
```

**関連用語:** [Flexbox](#flexbox-⭐⭐⭐), [グリッド](#グリッド-⭐⭐⭐)

### Flexbox ⭐⭐⭐
1次元レイアウトを作成するCSSモジュール。

**基本:**
```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
}
```

**詳細な例:**
```css
.flex-container {
  display: flex;
  flex-direction: row; /* row, column, row-reverse, column-reverse */
  flex-wrap: wrap; /* nowrap, wrap, wrap-reverse */
  justify-content: center; /* flex-start, flex-end, center, space-between, space-around */
  align-items: stretch; /* flex-start, flex-end, center, baseline, stretch */
  gap: 16px;
}

.flex-item {
  flex: 1; /* flex-grow, flex-shrink, flex-basis */
  flex-basis: 200px;
}
```

**関連用語:** [CSS Grid](#css-grid-⭐⭐⭐), [レイアウト](#レイアウト-⭐⭐⭐)

### クエリコンテナ (Container Queries) ⭐
親要素のサイズに基づいてスタイルを変更する新機能。

**例:**
```css
.container {
  container-type: inline-size;
}

@container (min-width: 400px) {
  .card {
    display: flex;
  }
}

@container (min-width: 600px) {
  .card {
    grid-template-columns: repeat(2, 1fr);
  }
}
```

**メディアクエリとの違い:**
- メディアクエリ: ビューポートサイズ基準
- コンテナクエリ: 親要素のサイズ基準

**メリット:**
- より柔軟なレスポンシブデザイン
- コンポーネント単位のレスポンシブ対応

**関連用語:** [メディアクエリ](#メディアクエリ-⭐⭐⭐), [レスポンシブ](#レスポンシブデザイン-⭐⭐⭐)

### has() セレクタ ⭐
特定の子要素を持つ親要素を選択する疑似クラス。

**例:**
```css
/* チェックボックスがチェックされている親 */
.form-group:has(input:checked) {
  background: lightblue;
}

/* 画像を含むカード */
.card:has(img) {
  padding: 0;
}

/* エラーを含むフォーム */
form:has(.error) {
  border: 2px solid red;
}
```

**用途:**
- 状態に応じたスタイリング
- 子要素の有無による親のスタイル変更

**関連用語:** [セレクタ](#セレクタ-⭐⭐⭐), [疑似クラス](#疑似クラス-⭐⭐)

### カスタムプロパティ (CSS Variables) ⭐⭐⭐
動的に変更可能なCSS変数。

**定義と使用:**
```css
:root {
  --primary: #007bff;
  --spacing: 16px;
}

.button {
  background: var(--primary);
  padding: var(--spacing);
}
```

**JavaScriptから変更:**
```javascript
// 値の取得
const primaryColor = getComputedStyle(document.documentElement)
  .getPropertyValue('--primary');

// 値の設定
document.documentElement.style
  .setProperty('--primary', '#ff0000');
```

**ダークモード:**
```css
:root {
  --bg-color: white;
  --text-color: black;
}

[data-theme="dark"] {
  --bg-color: black;
  --text-color: white;
}

body {
  background: var(--bg-color);
  color: var(--text-color);
}
```

**関連用語:** [CSS変数](#css変数-custom-properties-⭐⭐⭐), [テーマ](#テーマ-⭐⭐)

### clamp() ⭐⭐
最小値、推奨値、最大値を指定してレスポンシブな値を設定。

**構文:**
```css
/* clamp(最小値, 推奨値, 最大値) */
font-size: clamp(16px, 2vw, 24px);
width: clamp(300px, 50%, 800px);
padding: clamp(1rem, 2vw, 3rem);
```

**実例:**
```css
h1 {
  /* 画面幅に応じて16px〜48pxの間で変化 */
  font-size: clamp(16px, 4vw, 48px);
}

.container {
  /* 最小300px、最大1200px、基本は90% */
  width: clamp(300px, 90%, 1200px);
}
```

**メリット:**
- メディアクエリ不要
- 滑らかなレスポンシブ対応
- シンプルな記述

**関連用語:** [min()](#min-⭐), [max()](#max-⭐), [calc()](#calc-⭐⭐)

---

## より詳しく学ぶ

これで全6カテゴリの用語集が完成しました！

次のステップ:
- [基礎用語](./01-basics.md) - 基本に戻って復習
- [デザイン原則](./02-design-principles.md) - デザイン理論を深める
- 実際にコードを書いて実践してみましょう

[用語集トップに戻る](./README.md)
