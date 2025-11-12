# 色・タイポグラフィ

色彩とフォントに関する用語をまとめています。

## 目次
- [色彩理論](#色彩理論)
- [カラースキーム](#カラースキーム)
- [色の指定方法](#色の指定方法)
- [タイポグラフィ基礎](#タイポグラフィ基礎)
- [フォントの種類](#フォントの種類)
- [テキストスタイリング](#テキストスタイリング)

---

## 色彩理論

### 色相 (Hue) ⭐⭐⭐
色の種類。赤、青、黄色など、色相環上の位置で表されます。

**HSL表記:**
```css
/* 0度: 赤, 120度: 緑, 240度: 青 */
color: hsl(0, 100%, 50%);    /* 赤 */
color: hsl(120, 100%, 50%);  /* 緑 */
color: hsl(240, 100%, 50%);  /* 青 */
```

**関連用語:** [彩度](#彩度-saturation-⭐⭐⭐), [明度](#明度-lightness-⭐⭐⭐)

### 彩度 (Saturation) ⭐⭐⭐
色の鮮やかさ。彩度が高いほど鮮やか、低いほどくすんだ色になります。

**例:**
```css
/* 彩度100%（鮮やか） */
color: hsl(0, 100%, 50%);

/* 彩度50%（中間） */
color: hsl(0, 50%, 50%);

/* 彩度0%（グレー） */
color: hsl(0, 0%, 50%);
```

**関連用語:** [色相](#色相-hue-⭐⭐⭐), [明度](#明度-lightness-⭐⭐⭐)

### 明度 (Lightness/Brightness) ⭐⭐⭐
色の明るさ。0%が黒、100%が白、50%が純色です。

**例:**
```css
/* 明度25%（暗い） */
color: hsl(0, 100%, 25%);

/* 明度50%（通常） */
color: hsl(0, 100%, 50%);

/* 明度75%（明るい） */
color: hsl(0, 100%, 75%);
```

**関連用語:** [色相](#色相-hue-⭐⭐⭐), [彩度](#彩度-saturation-⭐⭐⭐)

### 色相環 (Color Wheel) ⭐⭐
色相を環状に配置したもの。色の関係性を視覚化します。

**構成:**
- 原色（赤、青、黄）
- 二次色（オレンジ、緑、紫）
- 三次色

**用途:**
- 調和する色の選択
- カラースキームの作成
- 補色の確認

**関連用語:** [補色](#補色-complementary-color-⭐⭐), [類似色](#類似色-⭐⭐)

### 補色 (Complementary Color) ⭐⭐
色相環で正反対に位置する色。組み合わせると強いコントラストを生みます。

**例:**
- 赤 ⟷ 緑
- 青 ⟷ オレンジ
- 黄 ⟷ 紫

**用途:**
- 強調したい要素
- アクセントカラー
- ビビッドなデザイン

**関連用語:** [コントラスト](#コントラスト-⭐⭐⭐), [色相環](#色相環-color-wheel-⭐⭐)

### コントラスト (Contrast) ⭐⭐⭐
色の対比。明度や色相の差によって生まれます。

**コントラスト比:**
```
最小推奨:
- 本文テキスト: 4.5:1
- 大きなテキスト: 3:1
- UIコンポーネント: 3:1
```

**重要性:**
- 可読性の向上
- アクセシビリティ
- 視覚階層の形成

**関連用語:** [アクセシビリティ](#アクセシビリティ-⭐⭐⭐), [WCAG](#wcag-⭐⭐)

---

## カラースキーム

### カラーパレット (Color Palette) ⭐⭐⭐
デザインで使用する色のセット。

**構成例:**
```css
/* プライマリーカラー */
--primary: #007bff;

/* セカンダリーカラー */
--secondary: #6c757d;

/* アクセントカラー */
--accent: #ff6b6b;

/* ニュートラルカラー */
--gray-100: #f8f9fa;
--gray-900: #212529;
```

**関連用語:** [プライマリーカラー](#プライマリーカラー-primary-color-⭐⭐⭐), [ブランドカラー](#ブランドカラー-⭐⭐⭐)

### プライマリーカラー (Primary Color) ⭐⭐⭐
ブランドを代表する主要な色。最も頻繁に使用されます。

**用途:**
- ロゴ
- メインボタン
- リンク
- ブランド要素

**例:**
```css
.btn-primary {
  background-color: var(--primary);
  color: white;
}
```

**関連用語:** [セカンダリーカラー](#セカンダリーカラー-secondary-color-⭐⭐), [ブランドカラー](#ブランドカラー-⭐⭐⭐)

### セカンダリーカラー (Secondary Color) ⭐⭐
プライマリーカラーを補助する色。

**用途:**
- サブボタン
- 背景
- 装飾要素

**関連用語:** [プライマリーカラー](#プライマリーカラー-primary-color-⭐⭐⭐), [アクセントカラー](#アクセントカラー-accent-color-⭐⭐)

### アクセントカラー (Accent Color) ⭐⭐
注意を引くための強調色。

**用途:**
- CTAボタン
- 重要な通知
- ハイライト
- ホバー効果

**例:**
```css
.btn-cta {
  background-color: var(--accent);
  animation: pulse 2s infinite;
}
```

**関連用語:** [CTA](#cta-⭐⭐⭐), [強調](#強調-⭐⭐)

### ニュートラルカラー (Neutral Color) ⭐⭐⭐
グレー、ベージュなど、主張の少ない色。

**用途:**
- 背景
- テキスト
- ボーダー
- シャドウ

**例:**
```css
:root {
  --gray-50: #f9fafb;
  --gray-100: #f3f4f6;
  --gray-200: #e5e7eb;
  --gray-900: #111827;
}
```

**関連用語:** [グレースケール](#グレースケール-⭐⭐), [背景色](#背景色-⭐⭐⭐)

### 類似色 (Analogous Colors) ⭐⭐
色相環で隣り合う色。調和的な配色を作ります。

**例:**
- 青、青緑、緑
- 赤、オレンジ、黄

**効果:**
- 穏やかな印象
- 統一感
- 自然な調和

**関連用語:** [色相環](#色相環-color-wheel-⭐⭐), [補色](#補色-complementary-color-⭐⭐)

### モノクロマティック (Monochromatic) ⭐⭐
1つの色相の明度や彩度を変えた配色。

**例:**
```css
/* 青系のモノクロマティック */
--blue-900: #1e3a8a;
--blue-700: #1d4ed8;
--blue-500: #3b82f6;
--blue-300: #93c5fd;
--blue-100: #dbeafe;
```

**効果:**
- シンプルで洗練
- 統一感が強い
- ブランド認識の向上

**関連用語:** [グラデーション](#グラデーション-gradient-⭐⭐), [色相](#色相-hue-⭐⭐⭐)

---

## 色の指定方法

### HEX (16進数) ⭐⭐⭐
`#RRGGBB`形式で色を指定。最も一般的です。

**例:**
```css
color: #ff0000;  /* 赤 */
color: #00ff00;  /* 緑 */
color: #0000ff;  /* 青 */
color: #fff;     /* 白（省略形） */
```

**関連用語:** [RGB](#rgb-⭐⭐⭐), [カラーコード](#カラーコード-⭐⭐⭐)

### RGB ⭐⭐⭐
Red、Green、Blueの値で色を指定。0-255の範囲。

**例:**
```css
color: rgb(255, 0, 0);     /* 赤 */
color: rgb(0, 255, 0);     /* 緑 */
color: rgb(0, 0, 255);     /* 青 */
```

**関連用語:** [RGBA](#rgba-⭐⭐⭐), [HEX](#hex-16進数-⭐⭐⭐)

### RGBA ⭐⭐⭐
RGBに透明度（Alpha）を追加。0-1の範囲。

**例:**
```css
background: rgba(0, 0, 0, 0.5);  /* 半透明の黒 */
background: rgba(255, 0, 0, 0.3);  /* 半透明の赤 */
```

**用途:**
- オーバーレイ
- シャドウ
- 重なり合う要素

**関連用語:** [透明度](#透明度-opacity-⭐⭐⭐), [RGB](#rgb-⭐⭐⭐)

### HSL ⭐⭐
Hue（色相）、Saturation（彩度）、Lightness（明度）で指定。

**例:**
```css
color: hsl(0, 100%, 50%);    /* 赤 */
color: hsl(120, 100%, 50%);  /* 緑 */
color: hsl(240, 100%, 50%);  /* 青 */
```

**メリット:**
- 直感的な色の調整
- 同系色の作成が容易
- 明度の統一が簡単

**関連用語:** [HSLA](#hsla-⭐⭐), [色相](#色相-hue-⭐⭐⭐)

### HSLA ⭐⭐
HSLに透明度を追加。

**例:**
```css
background: hsla(0, 100%, 50%, 0.5);  /* 半透明の赤 */
```

**関連用語:** [HSL](#hsl-⭐⭐), [透明度](#透明度-opacity-⭐⭐⭐)

### 透明度 (Opacity) ⭐⭐⭐
要素全体の透明度を指定。0（完全に透明）から1（不透明）。

**例:**
```css
.overlay {
  background: black;
  opacity: 0.5;  /* 半透明 */
}
```

**注意:**
- 子要素にも影響する
- 背景だけを透明にしたい場合はRGBAを使用

**関連用語:** [RGBA](#rgba-⭐⭐⭐), [透過](#透過-⭐⭐)

---

## タイポグラフィ基礎

### タイポグラフィ (Typography) ⭐⭐⭐
文字のデザインと配置に関する技術。可読性と美しさを両立させます。

**要素:**
- フォントの選択
- サイズ
- 行間
- 字間
- 配置

**重要性:**
- 情報の伝達
- ブランドイメージ
- ユーザーエクスペリエンス

**関連用語:** [フォント](#フォント-font-⭐⭐⭐), [可読性](#可読性-readability-⭐⭐⭐)

### フォント (Font) ⭐⭐⭐
文字の書体デザイン。

**指定方法:**
```css
font-family: 'Helvetica', 'Arial', sans-serif;
```

**種類:**
- セリフ
- サンセリフ
- モノスペース
- 筆記体

**関連用語:** [フォントファミリー](#フォントファミリー-font-family-⭐⭐⭐), [書体](#書体-⭐⭐⭐)

### フォントファミリー (Font Family) ⭐⭐⭐
フォントの種類を指定するプロパティ。フォールバックを設定します。

**例:**
```css
body {
  font-family:
    'Hiragino Sans',
    'Noto Sans JP',
    sans-serif;
}
```

**ベストプラクティス:**
- 複数のフォントを指定
- 必ずジェネリックファミリーを最後に
- Web フォントを先頭に

**関連用語:** [フォント](#フォント-font-⭐⭐⭐), [Webフォント](#webフォント-⭐⭐)

### フォントサイズ (Font Size) ⭐⭐⭐
文字の大きさ。

**単位:**
```css
/* 絶対単位 */
font-size: 16px;

/* 相対単位 */
font-size: 1rem;   /* ルート要素基準 */
font-size: 1.2em;  /* 親要素基準 */

/* パーセンテージ */
font-size: 120%;
```

**推奨サイズ:**
- 本文: 16px（1rem）
- 見出し: 24px-48px
- 小さいテキスト: 14px

**関連用語:** [rem](#rem-⭐⭐⭐), [em](#em-⭐⭐)

### 行間 (Line Height) ⭐⭐⭐
行と行の間隔。可読性に大きく影響します。

**例:**
```css
p {
  line-height: 1.6;  /* フォントサイズの1.6倍 */
}

h1 {
  line-height: 1.2;  /* 見出しは狭めに */
}
```

**推奨値:**
- 本文: 1.5-1.8
- 見出し: 1.2-1.4

**関連用語:** [レディビリティ](#レディビリティ-⭐⭐), [余白](#余白-⭐⭐⭐)

### 字間 (Letter Spacing / Tracking) ⭐⭐
文字と文字の間隔。

**例:**
```css
h1 {
  letter-spacing: 0.05em;  /* 広めに */
}

.tight {
  letter-spacing: -0.02em;  /* 狭めに */
}
```

**用途:**
- 見出しの強調
- 高級感の演出
- 可読性の調整

**関連用語:** [カーニング](#カーニング-kerning-⭐), [タイポグラフィ](#タイポグラフィ-typography-⭐⭐⭐)

### ウェイト (Font Weight) ⭐⭐⭐
フォントの太さ。

**値:**
```css
font-weight: 100;  /* Thin */
font-weight: 300;  /* Light */
font-weight: 400;  /* Regular/Normal */
font-weight: 500;  /* Medium */
font-weight: 700;  /* Bold */
font-weight: 900;  /* Black */
```

**キーワード:**
```css
font-weight: normal;  /* 400 */
font-weight: bold;    /* 700 */
```

**関連用語:** [太字](#太字-bold-⭐⭐⭐), [フォント](#フォント-font-⭐⭐⭐)

---

## フォントの種類

### セリフ体 (Serif) ⭐⭐⭐
文字の端に飾り（セリフ）がある書体。伝統的で格式高い印象。

**例:**
- Times New Roman
- Georgia
- 游明朝

**用途:**
- 印刷物
- 長文
- フォーマルなサイト

**CSS:**
```css
font-family: Georgia, 'Times New Roman', serif;
```

**関連用語:** [サンセリフ](#サンセリフ体-sans-serif-⭐⭐⭐), [書体](#書体-⭐⭐⭐)

### サンセリフ体 (Sans-serif) ⭐⭐⭐
セリフのないシンプルな書体。モダンで読みやすい。

**例:**
- Helvetica
- Arial
- 游ゴシック

**用途:**
- WEBサイト
- UI
- 見出し

**CSS:**
```css
font-family: 'Helvetica Neue', Arial, sans-serif;
```

**関連用語:** [セリフ体](#セリフ体-serif-⭐⭐⭐), [書体](#書体-⭐⭐⭐)

### モノスペース (Monospace) ⭐⭐
すべての文字が同じ幅の書体。コード表示に使用。

**例:**
- Courier
- Consolas
- Monaco

**用途:**
- コードブロック
- ターミナル表示
- 表

**CSS:**
```css
code {
  font-family: 'Courier New', Consolas, monospace;
}
```

**関連用語:** [コードブロック](#コードブロック-⭐⭐), [プロポーショナル](#プロポーショナル-⭐)

### Webフォント (Web Font) ⭐⭐
WEB上から読み込むフォント。デザインの自由度が高まります。

**読み込み方法:**
```css
/* Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

/* または */
@font-face {
  font-family: 'CustomFont';
  src: url('font.woff2') format('woff2');
}
```

**メリット:**
- 豊富な書体
- クロスブラウザ対応
- ブランディング

**デメリット:**
- 読み込み時間
- 表示の遅延

**関連用語:** [Google Fonts](#google-fonts-⭐⭐), [FOIT](#foit-⭐)

### Google Fonts ⭐⭐
Googleが提供する無料のWebフォントサービス。

**使用方法:**
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```

```css
body {
  font-family: 'Roboto', sans-serif;
}
```

**メリット:**
- 無料
- 使いやすい
- 豊富な種類

**関連用語:** [Webフォント](#webフォント-web-font-⭐⭐), [フォント](#フォント-font-⭐⭐⭐)

---

## テキストスタイリング

### テキストアライン (Text Align) ⭐⭐⭐
テキストの配置方向。

**値:**
```css
text-align: left;     /* 左揃え */
text-align: center;   /* 中央揃え */
text-align: right;    /* 右揃え */
text-align: justify;  /* 両端揃え */
```

**使い分け:**
- 本文: left（日本語）
- 見出し: center（場合による）
- 価格など: right

**関連用語:** [整列](#整列-⭐⭐⭐), [レイアウト](#レイアウト-⭐⭐⭐)

### テキストデコレーション (Text Decoration) ⭐⭐
テキストの装飾。

**例:**
```css
text-decoration: underline;      /* 下線 */
text-decoration: line-through;   /* 取り消し線 */
text-decoration: overline;       /* 上線 */
text-decoration: none;           /* なし */

/* 詳細な指定 */
text-decoration: underline wavy red;
```

**用途:**
- リンク
- 強調
- 削除された内容の表示

**関連用語:** [リンク](#リンク-⭐⭐⭐), [下線](#下線-⭐⭐)

### テキストシャドウ (Text Shadow) ⭐⭐
テキストに影を付ける効果。

**例:**
```css
/* 基本 */
text-shadow: 2px 2px 4px rgba(0,0,0,0.3);

/* 複数の影 */
text-shadow:
  2px 2px 4px rgba(0,0,0,0.3),
  -2px -2px 4px rgba(255,255,255,0.8);

/* グロー効果 */
text-shadow: 0 0 10px rgba(255,255,255,0.8);
```

**用途:**
- 立体感
- 可読性の向上
- デザインアクセント

**関連用語:** [シャドウ](#シャドウ-⭐⭐), [エフェクト](#エフェクト-⭐⭐)

### テキスト変換 (Text Transform) ⭐⭐
テキストの大文字/小文字変換。

**例:**
```css
text-transform: uppercase;   /* すべて大文字 */
text-transform: lowercase;   /* すべて小文字 */
text-transform: capitalize;  /* 各単語の先頭を大文字 */
text-transform: none;        /* 変換なし */
```

**用途:**
- 見出しの統一
- ブランディング
- スタイルの統一

**関連用語:** [タイポグラフィ](#タイポグラフィ-typography-⭐⭐⭐)

### 行端揃え (Text Justify) ⭐
両端揃えの詳細設定。

**例:**
```css
text-align: justify;
text-justify: inter-word;  /* 単語間で調整 */
```

**注意:**
- 日本語では使いにくい
- 不自然な空白が生じる場合がある

**関連用語:** [テキストアライン](#テキストアライン-text-align-⭐⭐⭐)

### 縦書き (Vertical Writing) ⭐
テキストを縦に表示。

**例:**
```css
.vertical {
  writing-mode: vertical-rl;  /* 右から左 */
  writing-mode: vertical-lr;  /* 左から右 */
}
```

**用途:**
- 日本語の縦書き
- デザインアクセント
- 伝統的な表現

**関連用語:** [writing-mode](#writing-mode-⭐), [日本語組版](#日本語組版-⭐)

### 省略記号 (Text Overflow) ⭐⭐
長いテキストを省略して表示。

**1行省略:**
```css
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

**複数行省略:**
```css
.line-clamp {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
```

**用途:**
- カードタイトル
- 説明文
- モバイル表示

**関連用語:** [overflow](#overflow-⭐⭐), [white-space](#white-space-⭐⭐)

---

## より詳しく学ぶ

次のステップ:
- [UI/UX](./05-ui-ux.md) - ユーザーエクスペリエンスを学ぶ
- [デザイン原則](./02-design-principles.md) - 色の使い方の原則を復習
- [技術・実装](./06-technical.md) - CSSの実装テクニックを学ぶ

[用語集トップに戻る](./README.md)
