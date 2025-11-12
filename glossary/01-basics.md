# 基礎用語

WEB開発の基本となる用語をまとめています。初心者の方はまずここから学習することをおすすめします。

## 目次
- [WEBの基本](#webの基本)
- [マークアップ言語](#マークアップ言語)
- [スタイリング](#スタイリング)
- [プログラミング](#プログラミング)
- [開発環境](#開発環境)
- [その他基本用語](#その他基本用語)

---

## WEBの基本

### HTML (HyperText Markup Language) ⭐⭐⭐
WEBページの構造を記述するためのマークアップ言語。文書の見出し、段落、リンク、画像などを定義します。

**使用例:**
```html
<h1>見出し</h1>
<p>段落のテキスト</p>
```

**関連用語:** [セマンティックHTML](#セマンティックhtml-⭐⭐), [タグ](#タグ-⭐⭐⭐)

### CSS (Cascading Style Sheets) ⭐⭐⭐
HTMLで記述された文書の見た目やレイアウトを指定するスタイルシート言語。色、フォント、配置などを制御します。

**使用例:**
```css
h1 {
  color: blue;
  font-size: 24px;
}
```

**関連用語:** [セレクタ](#セレクタ-⭐⭐⭐), [プロパティ](#プロパティ-⭐⭐⭐)

### JavaScript ⭐⭐⭐
WEBページに動的な機能を追加するためのプログラミング言語。ユーザーの操作に応じた処理や、ページの内容を動的に変更できます。

**使用例:**
```javascript
document.getElementById('button').addEventListener('click', function() {
  alert('クリックされました！');
});
```

**関連用語:** [DOM](#dom-⭐⭐), [イベント](#イベント-⭐⭐)

### ブラウザ (Web Browser) ⭐⭐⭐
WEBページを表示するためのソフトウェア。Chrome、Firefox、Safari、Edgeなどがあります。

**特徴:**
- HTMLを解釈してページを表示
- JavaScriptを実行
- CSSを適用してスタイリング

**関連用語:** [レンダリング](#レンダリング-⭐⭐), [クロスブラウザ](#クロスブラウザ-⭐⭐)

### サーバー (Server) ⭐⭐⭐
WEBページやデータを配信するコンピュータ。ユーザーのリクエストに応じて情報を返します。

**関連用語:** [クライアント](#クライアント-⭐⭐⭐), [HTTP](#http-⭐⭐⭐)

### クライアント (Client) ⭐⭐⭐
サーバーにリクエストを送り、情報を受け取る側。通常はユーザーのブラウザを指します。

**関連用語:** [サーバー](#サーバー-server-⭐⭐⭐), [クライアントサイド](#クライアントサイド-⭐⭐)

### HTTP/HTTPS (HyperText Transfer Protocol) ⭐⭐⭐
WEB上でデータをやり取りするための通信プロトコル。HTTPSはセキュアな暗号化通信版。

**違い:**
- HTTP: 非暗号化通信
- HTTPS: SSL/TLSで暗号化された安全な通信

**関連用語:** [プロトコル](#プロトコル-⭐⭐), [SSL](#ssl-⭐⭐)

---

## マークアップ言語

### タグ (Tag) ⭐⭐⭐
HTMLで要素を定義するためのマーク。`<tagname>`で開始し、`</tagname>`で終了します。

**例:**
```html
<p>これは段落です</p>
<div>これはdiv要素です</div>
```

**関連用語:** [要素](#要素-element-⭐⭐⭐), [属性](#属性-attribute-⭐⭐⭐)

### 要素 (Element) ⭐⭐⭐
開始タグ、コンテンツ、終了タグで構成されるHTMLの構成単位。

**例:**
```html
<p>テキスト</p>
<!-- <p>が開始タグ、「テキスト」がコンテンツ、</p>が終了タグ -->
```

**関連用語:** [タグ](#タグ-tag-⭐⭐⭐), [ネスト](#ネスト-⭐⭐)

### 属性 (Attribute) ⭐⭐⭐
タグに追加情報を与えるためのもの。`属性名="値"`の形式で記述します。

**例:**
```html
<a href="https://example.com" target="_blank">リンク</a>
<img src="image.jpg" alt="画像の説明">
```

**関連用語:** [タグ](#タグ-tag-⭐⭐⭐), [値](#値-⭐⭐⭐)

### セマンティックHTML (Semantic HTML) ⭐⭐
意味のあるタグを使ってHTMLを記述する手法。`<header>`, `<nav>`, `<article>`など。

**メリット:**
- SEOに有利
- アクセシビリティの向上
- コードの可読性向上

**例:**
```html
<article>
  <header>
    <h1>記事のタイトル</h1>
  </header>
  <p>記事の内容</p>
</article>
```

**関連用語:** [SEO](#seo-⭐⭐⭐), [アクセシビリティ](#アクセシビリティ-⭐⭐⭐)

### インライン要素 (Inline Element) ⭐⭐
文章の中に配置される要素。改行されず、横に並びます。`<span>`, `<a>`, `<strong>`など。

**例:**
```html
<p>これは<strong>インライン</strong>要素です</p>
```

**関連用語:** [ブロック要素](#ブロック要素-block-element-⭐⭐), [display](#display-⭐⭐⭐)

### ブロック要素 (Block Element) ⭐⭐
独立したブロックを形成する要素。前後に改行が入ります。`<div>`, `<p>`, `<h1>`など。

**例:**
```html
<div>これはブロック要素です</div>
<p>これも別のブロックです</p>
```

**関連用語:** [インライン要素](#インライン要素-inline-element-⭐⭐), [display](#display-⭐⭐⭐)

### ネスト (Nest) ⭐⭐
要素の中に別の要素を入れ子にすること。HTMLの階層構造を作ります。

**例:**
```html
<div>
  <p>
    <span>入れ子構造</span>
  </p>
</div>
```

**関連用語:** [要素](#要素-element-⭐⭐⭐), [階層構造](#階層構造-⭐⭐)

---

## スタイリング

### セレクタ (Selector) ⭐⭐⭐
CSSでスタイルを適用する対象を指定するもの。要素、クラス、IDなどで指定します。

**例:**
```css
/* 要素セレクタ */
p { color: black; }

/* クラスセレクタ */
.class-name { color: blue; }

/* IDセレクタ */
#id-name { color: red; }
```

**関連用語:** [クラス](#クラス-class-⭐⭐⭐), [ID](#id-⭐⭐⭐)

### プロパティ (Property) ⭐⭐⭐
CSSでスタイルの種類を指定するもの。`color`, `font-size`, `margin`など。

**例:**
```css
p {
  color: blue;        /* プロパティ: color */
  font-size: 16px;    /* プロパティ: font-size */
}
```

**関連用語:** [値](#値-⭐⭐⭐), [セレクタ](#セレクタ-selector-⭐⭐⭐)

### クラス (Class) ⭐⭐⭐
複数の要素に同じスタイルを適用するための識別子。`.`で始まります。

**HTML:**
```html
<p class="highlight">強調されたテキスト</p>
```

**CSS:**
```css
.highlight {
  background-color: yellow;
}
```

**関連用語:** [ID](#id-⭐⭐⭐), [セレクタ](#セレクタ-selector-⭐⭐⭐)

### ID ⭐⭐⭐
ページ内で一意の要素を識別するための識別子。`#`で始まります。

**HTML:**
```html
<div id="header">ヘッダー</div>
```

**CSS:**
```css
#header {
  background-color: navy;
}
```

**関連用語:** [クラス](#クラス-class-⭐⭐⭐), [セレクタ](#セレクタ-selector-⭐⭐⭐)

### ボックスモデル (Box Model) ⭐⭐⭐
HTML要素を囲む矩形領域のモデル。content、padding、border、marginで構成されます。

**構成:**
```
┌─────────── margin ───────────┐
│ ┌───────── border ─────────┐ │
│ │ ┌─────── padding ───────┐│ │
│ │ │                       ││ │
│ │ │      content          ││ │
│ │ │                       ││ │
│ │ └───────────────────────┘│ │
│ └─────────────────────────┘ │
└─────────────────────────────┘
```

**関連用語:** [margin](#margin-⭐⭐⭐), [padding](#padding-⭐⭐⭐), [border](#border-⭐⭐⭐)

### margin ⭐⭐⭐
要素の外側の余白。他の要素との間隔を制御します。

**例:**
```css
div {
  margin: 10px;              /* 全方向 */
  margin: 10px 20px;         /* 上下 左右 */
  margin: 10px 20px 30px 40px; /* 上 右 下 左 */
}
```

**関連用語:** [padding](#padding-⭐⭐⭐), [ボックスモデル](#ボックスモデル-box-model-⭐⭐⭐)

### padding ⭐⭐⭐
要素の内側の余白。コンテンツとボーダーの間の空間です。

**例:**
```css
div {
  padding: 10px;
  padding: 10px 20px;
}
```

**関連用語:** [margin](#margin-⭐⭐⭐), [ボックスモデル](#ボックスモデル-box-model-⭐⭐⭐)

### border ⭐⭐⭐
要素の境界線。太さ、スタイル、色を指定できます。

**例:**
```css
div {
  border: 1px solid black;
  border-radius: 5px; /* 角を丸める */
}
```

**関連用語:** [ボックスモデル](#ボックスモデル-box-model-⭐⭐⭐)

### display ⭐⭐⭐
要素の表示方法を指定するプロパティ。`block`, `inline`, `flex`, `grid`など。

**例:**
```css
.block { display: block; }
.inline { display: inline; }
.flex { display: flex; }
.none { display: none; } /* 非表示 */
```

**関連用語:** [ブロック要素](#ブロック要素-block-element-⭐⭐), [インライン要素](#インライン要素-inline-element-⭐⭐)

---

## プログラミング

### DOM (Document Object Model) ⭐⭐
HTMLやXML文書をプログラムから操作するためのAPI。JavaScriptから要素の取得や変更ができます。

**例:**
```javascript
// 要素の取得
const element = document.getElementById('myId');

// 内容の変更
element.textContent = '新しいテキスト';

// スタイルの変更
element.style.color = 'blue';
```

**関連用語:** [JavaScript](#javascript-⭐⭐⭐), [要素](#要素-element-⭐⭐⭐)

### イベント (Event) ⭐⭐
ユーザーの操作やブラウザの動作によって発生する出来事。クリック、スクロール、読み込み完了など。

**例:**
```javascript
// クリックイベント
button.addEventListener('click', function() {
  console.log('クリックされました');
});

// フォーム送信イベント
form.addEventListener('submit', function(e) {
  e.preventDefault();
});
```

**関連用語:** [イベントリスナー](#イベントリスナー-⭐⭐), [コールバック](#コールバック-⭐)

### イベントリスナー (Event Listener) ⭐⭐
特定のイベントを監視し、発生時に処理を実行する仕組み。

**例:**
```javascript
element.addEventListener('click', function() {
  // クリック時の処理
});
```

**関連用語:** [イベント](#イベント-event-⭐⭐), [コールバック](#コールバック-⭐)

### 変数 (Variable) ⭐⭐⭐
データを格納するための入れ物。JavaScriptでは`let`, `const`, `var`で宣言します。

**例:**
```javascript
let name = '太郎';
const age = 25;
var isStudent = true;
```

**関連用語:** [データ型](#データ型-⭐⭐), [スコープ](#スコープ-⭐)

### 関数 (Function) ⭐⭐⭐
処理をまとめて名前を付けたもの。再利用可能なコードブロックです。

**例:**
```javascript
function greet(name) {
  return `こんにちは、${name}さん！`;
}

// アロー関数
const greet = (name) => {
  return `こんにちは、${name}さん！`;
};
```

**関連用語:** [引数](#引数-⭐⭐), [戻り値](#戻り値-⭐⭐)

---

## 開発環境

### エディタ (Editor) ⭐⭐⭐
コードを書くためのソフトウェア。VS Code、Sublime Text、Atomなどがあります。

**主な機能:**
- シンタックスハイライト
- コード補完
- デバッグ機能

**関連用語:** [IDE](#ide-⭐⭐), [VSCode](#vscode-⭐⭐⭐)

### VSCode (Visual Studio Code) ⭐⭐⭐
Microsoftが開発した人気の無料コードエディタ。拡張機能が豊富です。

**特徴:**
- 軽量で高速
- 豊富な拡張機能
- Git統合
- デバッグ機能

**関連用語:** [エディタ](#エディタ-editor-⭐⭐⭐), [拡張機能](#拡張機能-⭐⭐)

### パス (Path) ⭐⭐⭐
ファイルやディレクトリの場所を示す文字列。絶対パスと相対パスがあります。

**例:**
```html
<!-- 相対パス -->
<img src="./images/photo.jpg">

<!-- 絶対パス -->
<img src="/assets/images/photo.jpg">
```

**関連用語:** [相対パス](#相対パス-⭐⭐), [絶対パス](#絶対パス-⭐⭐)

### 相対パス (Relative Path) ⭐⭐
現在のファイルを基準としたファイルの場所。

**例:**
```
./image.jpg      # 同じディレクトリ
../image.jpg     # 1つ上のディレクトリ
./img/photo.jpg  # imgディレクトリ内
```

**関連用語:** [絶対パス](#絶対パス-absolute-path-⭐⭐), [パス](#パス-path-⭐⭐⭐)

### 絶対パス (Absolute Path) ⭐⭐
ルートディレクトリを基準としたファイルの場所。

**例:**
```
/home/user/project/index.html
/assets/css/style.css
```

**関連用語:** [相対パス](#相対パス-relative-path-⭐⭐), [パス](#パス-path-⭐⭐⭐)

### Git ⭐⭐⭐
バージョン管理システム。コードの変更履歴を管理し、チーム開発を支援します。

**基本コマンド:**
```bash
git init          # リポジトリの初期化
git add .         # 変更をステージング
git commit -m ""  # コミット
git push          # リモートへプッシュ
```

**関連用語:** [GitHub](#github-⭐⭐⭐), [バージョン管理](#バージョン管理-⭐⭐)

### GitHub ⭐⭐⭐
Gitリポジトリをホスティングするサービス。コードの共有やコラボレーションに使われます。

**主な機能:**
- リポジトリホスティング
- Issue管理
- Pull Request
- プロジェクト管理

**関連用語:** [Git](#git-⭐⭐⭐), [リポジトリ](#リポジトリ-⭐⭐)

---

## その他基本用語

### レンダリング (Rendering) ⭐⭐
ブラウザがHTMLやCSSを解釈して、画面に表示する処理。

**関連用語:** [ブラウザ](#ブラウザ-web-browser-⭐⭐⭐), [DOM](#dom-⭐⭐)

### クロスブラウザ (Cross Browser) ⭐⭐
異なるブラウザでも同じように表示・動作すること。またはその対応。

**対応すべきブラウザ:**
- Chrome
- Firefox
- Safari
- Edge

**関連用語:** [ブラウザ](#ブラウザ-web-browser-⭐⭐⭐), [ベンダープレフィックス](#ベンダープレフィックス-⭐)

### デバッグ (Debug) ⭐⭐⭐
プログラムのバグ（誤り）を見つけて修正すること。

**ツール:**
- ブラウザの開発者ツール
- console.log()
- ブレークポイント

**関連用語:** [開発者ツール](#開発者ツール-⭐⭐⭐), [コンソール](#コンソール-⭐⭐)

### 開発者ツール (Developer Tools) ⭐⭐⭐
ブラウザに組み込まれた開発支援ツール。F12キーで開きます。

**主な機能:**
- 要素の検証
- CSSの編集
- JavaScriptのデバッグ
- ネットワークの監視

**関連用語:** [デバッグ](#デバッグ-debug-⭐⭐⭐), [コンソール](#コンソール-⭐⭐)

### コンソール (Console) ⭐⭐
開発者ツールの一部。JavaScriptのログ出力やエラー確認ができます。

**例:**
```javascript
console.log('ログ出力');
console.error('エラーメッセージ');
console.warn('警告');
```

**関連用語:** [開発者ツール](#開発者ツール-developer-tools-⭐⭐⭐), [デバッグ](#デバッグ-debug-⭐⭐⭐)

### SEO (Search Engine Optimization) ⭐⭐⭐
検索エンジン最適化。検索結果で上位に表示されるための施策。

**基本的な施策:**
- セマンティックなHTML
- メタタグの設定
- ページ速度の最適化
- モバイル対応

**関連用語:** [セマンティックHTML](#セマンティックhtml-semantic-html-⭐⭐), [メタタグ](#メタタグ-⭐⭐)

### アクセシビリティ (Accessibility) ⭐⭐⭐
障がいのある人を含む、すべての人が使いやすいWEBサイトを作ること。

**基本的な対応:**
- 適切なalt属性
- キーボード操作対応
- 十分なコントラスト
- セマンティックなHTML

**関連用語:** [alt属性](#alt属性-⭐⭐), [ARIA](#aria-⭐)

### 値 (Value) ⭐⭐⭐
HTMLの属性やCSSのプロパティに設定するデータ。

**例:**
```html
<img src="image.jpg" alt="画像">
<!-- "image.jpg"と"画像"が値 -->
```

```css
p {
  color: blue; /* "blue"が値 */
}
```

**関連用語:** [属性](#属性-attribute-⭐⭐⭐), [プロパティ](#プロパティ-property-⭐⭐⭐)

---

## より詳しく学ぶ

次のステップ:
- [デザイン原則・理論](./02-design-principles.md) - デザインの基本原則を学ぶ
- [レイアウト・構造](./03-layout.md) - ページレイアウトについて学ぶ
- [技術・実装](./06-technical.md) - より実践的な技術を学ぶ

[用語集トップに戻る](./README.md)
