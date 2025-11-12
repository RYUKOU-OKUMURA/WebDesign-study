# UI/UX

ユーザーインターフェースとユーザーエクスペリエンスに関する用語をまとめています。

## 目次
- [UI基礎](#ui基礎)
- [UX基礎](#ux基礎)
- [インタラクション](#インタラクション)
- [ユーザビリティ](#ユーザビリティ)
- [フィードバック](#フィードバック)
- [状態表現](#状態表現)

---

## UI基礎

### UI (User Interface) ⭐⭐⭐
ユーザーとシステムの接点。見た目や操作方法を指します。

**構成要素:**
- ボタン
- フォーム
- メニュー
- アイコン

**良いUIの条件:**
- 直感的
- 一貫性がある
- 視認性が高い
- アクセシブル

**関連用語:** [UX](#ux-user-experience-⭐⭐⭐), [GUI](#gui-⭐⭐)

### GUI (Graphical User Interface) ⭐⭐
グラフィカルなユーザーインターフェース。視覚的に操作できるUI。

**特徴:**
- アイコン
- ウィンドウ
- マウス操作
- 視覚的なフィードバック

**関連用語:** [UI](#ui-user-interface-⭐⭐⭐), [ビジュアルデザイン](#ビジュアルデザイン-⭐⭐)

### コンポーネント (Component) ⭐⭐⭐
再利用可能なUI部品。

**例:**
- ボタン
- カード
- フォーム入力
- ナビゲーション

**メリット:**
- 一貫性の確保
- 開発効率の向上
- メンテナンス性の向上

**実装例:**
```html
<!-- ボタンコンポーネント -->
<button class="btn btn-primary">
  クリック
</button>

<!-- カードコンポーネント -->
<div class="card">
  <img src="image.jpg" alt="">
  <div class="card-body">
    <h3>タイトル</h3>
    <p>説明</p>
  </div>
</div>
```

**関連用語:** [デザインシステム](#デザインシステム-⭐⭐), [パターンライブラリ](#パターンライブラリ-⭐)

### ボタン (Button) ⭐⭐⭐
ユーザーのアクションを受け付けるUI要素。

**種類:**
```html
<!-- プライマリーボタン -->
<button class="btn-primary">送信</button>

<!-- セカンダリーボタン -->
<button class="btn-secondary">キャンセル</button>

<!-- テキストボタン -->
<button class="btn-text">詳しく見る</button>

<!-- アイコンボタン -->
<button class="btn-icon">
  <span class="icon">🔍</span>
</button>
```

**デザインのポイント:**
- 十分な大きさ（最小44x44px）
- 明確なラベル
- 視覚的なフィードバック
- 無効状態の表現

**関連用語:** [CTA](#cta-⭐⭐⭐), [ホバー](#ホバー-hover-⭐⭐)

### フォーム (Form) ⭐⭐⭐
ユーザーから情報を入力してもらうUI。

**構成要素:**
```html
<form>
  <label for="name">名前</label>
  <input type="text" id="name" required>

  <label for="email">メール</label>
  <input type="email" id="email" required>

  <label for="message">メッセージ</label>
  <textarea id="message"></textarea>

  <button type="submit">送信</button>
</form>
```

**ベストプラクティス:**
- 明確なラベル
- バリデーション
- エラーメッセージ
- 送信後のフィードバック
- オートコンプリート対応

**関連用語:** [バリデーション](#バリデーション-validation-⭐⭐), [入力欄](#入力欄-input-⭐⭐⭐)

### アイコン (Icon) ⭐⭐⭐
機能や概念を表す小さな図形。

**使い方:**
```html
<!-- FontAwesome -->
<i class="fas fa-search"></i>

<!-- SVGアイコン -->
<svg width="24" height="24">
  <path d="..."/>
</svg>

<!-- テキストと併用 -->
<button>
  <span class="icon">🔍</span>
  検索
</button>
```

**ベストプラクティス:**
- 一貫性のあるスタイル
- 適切なサイズ
- alt属性の設定
- テキストラベルとの併用

**関連用語:** [アイコンフォント](#アイコンフォント-⭐⭐), [SVG](#svg-⭐⭐)

---

## UX基礎

### UX (User Experience) ⭐⭐⭐
ユーザーが製品やサービスを使う際の体験全体。

**含まれる要素:**
- 使いやすさ
- 満足度
- 効率性
- アクセシビリティ
- 感情的な反応

**良いUXの条件:**
- 目的が達成しやすい
- ストレスがない
- 楽しい・心地よい
- 信頼できる

**関連用語:** [UI](#ui-user-interface-⭐⭐⭐), [ユーザビリティ](#ユーザビリティ-usability-⭐⭐⭐)

### ユーザビリティ (Usability) ⭐⭐⭐
製品の使いやすさ。効率的・効果的に目的を達成できる度合い。

**5つの要素:**
1. **学習しやすさ**: 初めてでも使える
2. **効率性**: 素早く操作できる
3. **記憶しやすさ**: 久しぶりでも使える
4. **エラー**: エラーが少なく、回復しやすい
5. **満足度**: 使っていて快適

**測定方法:**
- ユーザーテスト
- タスク完了率
- 操作時間の計測
- エラー発生率

**関連用語:** [UX](#ux-user-experience-⭐⭐⭐), [ユーザーテスト](#ユーザーテスト-⭐⭐)

### ペルソナ (Persona) ⭐⭐
ターゲットユーザーを代表する架空の人物像。

**含まれる情報:**
- 年齢・性別
- 職業
- 趣味・関心
- 技術リテラシー
- 目標・課題

**用途:**
- デザイン判断の基準
- チーム内の共通理解
- ユーザー視点の維持

**関連用語:** [ユーザーリサーチ](#ユーザーリサーチ-⭐⭐), [ターゲット](#ターゲット-⭐⭐)

### ユーザーフロー (User Flow) ⭐⭐
ユーザーが目的を達成するまでの一連の流れ。

**例（ECサイト）:**
```
1. トップページ
2. カテゴリー選択
3. 商品一覧
4. 商品詳細
5. カート追加
6. カート確認
7. 購入手続き
8. 完了画面
```

**作成目的:**
- ユーザー体験の可視化
- 問題点の発見
- 改善施策の検討

**関連用語:** [ジャーニーマップ](#ジャーニーマップ-⭐), [ワイヤーフレーム](#ワイヤーフレーム-⭐⭐)

### アフォーダンス (Affordance) ⭐⭐
物や要素が持つ「こう使えそう」という手がかり。

**例:**
- ボタンは押せそう（立体的、色付き）
- リンクは青色で下線付き
- スライダーはドラッグできそう

**デザインへの応用:**
- ボタンに影を付ける
- クリック可能な要素の色を変える
- ドラッグ可能な要素にアイコンを付ける

**関連用語:** [シグニファイア](#シグニファイア-⭐), [直感的](#直感的-⭐⭐)

### メンタルモデル (Mental Model) ⭐⭐
ユーザーがシステムの動作について持っている期待や理解。

**重要性:**
- ユーザーの期待に沿ったデザイン
- 学習コストの削減
- エラーの防止

**例:**
- 買い物カゴのアイコン = ECサイト
- 虫眼鏡のアイコン = 検索
- ゴミ箱アイコン = 削除

**関連用語:** [直感的](#直感的-⭐⭐), [学習コスト](#学習コスト-⭐⭐)

---

## インタラクション

### インタラクション (Interaction) ⭐⭐
ユーザーとシステムの相互作用。

**種類:**
- クリック
- ホバー
- スクロール
- ドラッグ&ドロップ
- スワイプ

**デザインのポイント:**
- 予測可能
- 即座のフィードバック
- スムーズなアニメーション
- 一貫性

**関連用語:** [アニメーション](#アニメーション-animation-⭐⭐), [トランジション](#トランジション-transition-⭐⭐)

### ホバー (Hover) ⭐⭐
マウスカーソルを要素の上に置いたときの状態。

**例:**
```css
.button {
  background: blue;
  transition: background 0.3s;
}

.button:hover {
  background: darkblue;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}
```

**用途:**
- リンクの強調
- ボタンの反応表示
- 追加情報の表示

**関連用語:** [インタラクション](#インタラクション-interaction-⭐⭐), [状態](#状態-state-⭐⭐)

### クリック (Click) ⭐⭐⭐
要素をクリックしたときの動作。

**状態:**
```css
/* 通常 */
.button {
  background: blue;
}

/* ホバー */
.button:hover {
  background: darkblue;
}

/* アクティブ（押下中） */
.button:active {
  transform: scale(0.95);
}
```

**関連用語:** [タップ](#タップ-tap-⭐⭐), [インタラクション](#インタラクション-interaction-⭐⭐)

### タップ (Tap) ⭐⭐
タッチデバイスで要素をタッチすること。

**クリックとの違い:**
- ホバー状態がない
- タッチ領域が必要（最小44x44px）
- ロングタップの考慮

**CSS:**
```css
/* タッチデバイス対応 */
@media (hover: none) {
  .button:active {
    background: darkblue;
  }
}
```

**関連用語:** [タッチ](#タッチ-⭐⭐), [モバイルファースト](#モバイルファースト-⭐⭐⭐)

### スワイプ (Swipe) ⭐⭐
画面を指でなぞる操作。モバイルデバイスで使用。

**用途:**
- カルーセルのスライド
- 画像ギャラリー
- メニューの開閉
- アイテムの削除

**実装:**
```javascript
element.addEventListener('touchstart', handleTouchStart);
element.addEventListener('touchmove', handleTouchMove);
element.addEventListener('touchend', handleTouchEnd);
```

**関連用語:** [ジェスチャー](#ジェスチャー-⭐), [タッチ](#タッチ-⭐⭐)

### ドラッグ&ドロップ (Drag and Drop) ⭐⭐
要素を掴んで移動させる操作。

**用途:**
- ファイルアップロード
- リスト順序の変更
- カスタマイズ可能なレイアウト

**HTML:**
```html
<div draggable="true" ondragstart="drag(event)">
  ドラッグ可能
</div>

<div ondrop="drop(event)" ondragover="allowDrop(event)">
  ここにドロップ
</div>
```

**関連用語:** [インタラクション](#インタラクション-interaction-⭐⭐), [ジェスチャー](#ジェスチャー-⭐)

---

## ユーザビリティ

### アクセシビリティ (Accessibility) ⭐⭐⭐
障がいのある人を含むすべての人が使えるようにすること。

**対応項目:**
- **視覚**: 十分なコントラスト、alt属性
- **聴覚**: 字幕、トランスクリプト
- **運動**: キーボード操作、大きなタップ領域
- **認知**: シンプルな表現、一貫性

**実装例:**
```html
<!-- alt属性 -->
<img src="chart.jpg" alt="2024年売上推移グラフ">

<!-- ARIAラベル -->
<button aria-label="メニューを開く">
  <span class="icon">☰</span>
</button>

<!-- キーボード操作 -->
<div role="button" tabindex="0" onkeypress="handleKey(event)">
  クリック可能
</div>
```

**関連用語:** [WCAG](#wcag-⭐⭐), [ARIA](#aria-⭐⭐)

### WCAG (Web Content Accessibility Guidelines) ⭐⭐
Webコンテンツのアクセシビリティガイドライン。

**レベル:**
- **A**: 最低限の基準
- **AA**: 推奨レベル（多くのサイトが目標）
- **AAA**: 最高レベル

**4つの原則（POUR）:**
1. **知覚可能** (Perceivable)
2. **操作可能** (Operable)
3. **理解可能** (Understandable)
4. **堅牢** (Robust)

**関連用語:** [アクセシビリティ](#アクセシビリティ-accessibility-⭐⭐⭐), [ARIA](#aria-⭐⭐)

### キーボードナビゲーション (Keyboard Navigation) ⭐⭐
キーボードだけでサイトを操作できること。

**主なキー:**
- Tab: 次の要素へ
- Shift+Tab: 前の要素へ
- Enter: 選択/実行
- Space: チェックボックス/ボタン
- 矢印キー: リスト内の移動

**実装:**
```css
/* フォーカス時のスタイル */
:focus {
  outline: 2px solid blue;
  outline-offset: 2px;
}

/* フォーカス表示の改善 */
:focus-visible {
  outline: 2px solid blue;
}
```

**関連用語:** [アクセシビリティ](#アクセシビリティ-accessibility-⭐⭐⭐), [フォーカス](#フォーカス-focus-⭐⭐)

### レスポンシブ (Responsive) ⭐⭐⭐
画面サイズに応じて最適な表示に切り替わること。

**実装方法:**
```css
/* モバイル */
.container {
  padding: 16px;
}

/* タブレット */
@media (min-width: 768px) {
  .container {
    padding: 32px;
  }
}

/* デスクトップ */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
}
```

**関連用語:** [メディアクエリ](#メディアクエリ-⭐⭐⭐), [モバイルファースト](#モバイルファースト-⭐⭐⭐)

### エラーハンドリング (Error Handling) ⭐⭐
エラーの防止と、発生時の適切な対応。

**原則:**
1. **エラーの防止**: バリデーション、確認ダイアログ
2. **明確なメッセージ**: 何が問題か、どうすればいいか
3. **回復の支援**: 修正しやすいUI

**実装例:**
```html
<form>
  <input
    type="email"
    required
    pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$"
  >
  <span class="error">正しいメールアドレスを入力してください</span>
</form>
```

```css
.error {
  color: red;
  font-size: 14px;
  display: none;
}

input:invalid + .error {
  display: block;
}
```

**関連用語:** [バリデーション](#バリデーション-validation-⭐⭐), [フィードバック](#フィードバック-feedback-⭐⭐⭐)

---

## フィードバック

### フィードバック (Feedback) ⭐⭐⭐
ユーザーの操作に対するシステムの反応。

**種類:**
- 視覚的: 色の変化、アニメーション
- 聴覚的: サウンド
- 触覚的: バイブレーション

**重要性:**
- 操作の確認
- 処理中の表示
- 結果の通知

**例:**
```html
<!-- ボタンの視覚的フィードバック -->
<button class="btn" onclick="handleClick()">
  送信
</button>

<script>
function handleClick() {
  const btn = event.target;
  btn.textContent = '送信中...';
  btn.disabled = true;

  // 処理完了後
  setTimeout(() => {
    btn.textContent = '完了！';
    btn.classList.add('success');
  }, 2000);
}
</script>
```

**関連用語:** [ローディング](#ローディング-loading-⭐⭐), [トースト](#トースト-toast-⭐⭐)

### ローディング (Loading) ⭐⭐
処理中であることを示す表示。

**種類:**
```html
<!-- スピナー -->
<div class="spinner"></div>

<!-- プログレスバー -->
<div class="progress">
  <div class="progress-bar" style="width: 60%"></div>
</div>

<!-- スケルトンスクリーン -->
<div class="skeleton">
  <div class="skeleton-line"></div>
  <div class="skeleton-line"></div>
</div>

<!-- テキスト -->
<p>読み込み中...</p>
```

**ベストプラクティス:**
- 0.5秒以上かかる処理で表示
- 進捗が分かる場合はプログレスバー
- 長時間かかる場合は推定時間を表示

**関連用語:** [スピナー](#スピナー-spinner-⭐⭐), [スケルトンスクリーン](#スケルトンスクリーン-⭐)

### トースト (Toast) ⭐⭐
画面端に一時的に表示される通知メッセージ。

**例:**
```html
<div class="toast toast-success">
  <span class="icon">✓</span>
  保存しました
</div>
```

```css
.toast {
  position: fixed;
  bottom: 20px;
  right: 20px;
  padding: 16px 24px;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  animation: slideIn 0.3s ease-out;
}

@keyframes slideIn {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}
```

**用途:**
- 操作完了の通知
- エラーメッセージ
- 情報の通知

**関連用語:** [スナックバー](#スナックバー-snackbar-⭐), [通知](#通知-notification-⭐⭐)

### プレースホルダー (Placeholder) ⭐⭐
入力欄の入力例を示すテキスト。

**例:**
```html
<input
  type="text"
  placeholder="例: 山田太郎"
  aria-label="お名前"
>

<input
  type="email"
  placeholder="example@email.com"
>
```

**注意点:**
- ラベルの代わりにしない
- 短く分かりやすく
- コントラストに注意

**関連用語:** [フォーム](#フォーム-form-⭐⭐⭐), [入力欄](#入力欄-input-⭐⭐⭐)

### バリデーション (Validation) ⭐⭐
入力内容の妥当性チェック。

**タイミング:**
- リアルタイム（入力中）
- フォーカスアウト時
- 送信時

**実装例:**
```html
<input
  type="email"
  id="email"
  required
  pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$"
>

<script>
const input = document.getElementById('email');

input.addEventListener('blur', () => {
  if (!input.validity.valid) {
    showError('正しいメールアドレスを入力してください');
  }
});
</script>
```

**関連用語:** [エラーハンドリング](#エラーハンドリング-error-handling-⭐⭐), [フォーム](#フォーム-form-⭐⭐⭐)

---

## 状態表現

### 状態 (State) ⭐⭐
UI要素の現在の状況。

**主な状態:**
- デフォルト（通常）
- ホバー
- フォーカス
- アクティブ（押下中）
- 無効（disabled）
- ローディング
- エラー
- 成功

**CSS実装:**
```css
.button {
  /* デフォルト */
  background: blue;
}

.button:hover {
  /* ホバー */
  background: darkblue;
}

.button:active {
  /* アクティブ */
  transform: scale(0.95);
}

.button:disabled {
  /* 無効 */
  background: gray;
  cursor: not-allowed;
  opacity: 0.5;
}
```

**関連用語:** [インタラクション](#インタラクション-interaction-⭐⭐), [フィードバック](#フィードバック-feedback-⭐⭐⭐)

### フォーカス (Focus) ⭐⭐
キーボード操作で選択されている状態。

**スタイリング:**
```css
/* デフォルトのoutlineを改善 */
:focus {
  outline: 2px solid #007bff;
  outline-offset: 2px;
}

/* マウスクリック時は非表示 */
:focus:not(:focus-visible) {
  outline: none;
}

/* キーボード操作時のみ表示 */
:focus-visible {
  outline: 2px solid #007bff;
}
```

**重要性:**
- キーボードナビゲーション
- アクセシビリティ

**関連用語:** [キーボードナビゲーション](#キーボードナビゲーション-keyboard-navigation-⭐⭐), [アクセシビリティ](#アクセシビリティ-accessibility-⭐⭐⭐)

### 無効状態 (Disabled) ⭐⭐
操作できない状態。

**実装:**
```html
<button disabled>送信</button>
<input type="text" disabled value="編集不可">
```

```css
button:disabled {
  background: #cccccc;
  color: #666666;
  cursor: not-allowed;
  opacity: 0.6;
}
```

**使用場面:**
- 条件未達成
- 処理中
- 権限不足

**関連用語:** [状態](#状態-state-⭐⭐), [フィードバック](#フィードバック-feedback-⭐⭐⭐)

### CTA (Call To Action) ⭐⭐⭐
ユーザーに行動を促す要素。

**例:**
- 「今すぐ登録」ボタン
- 「無料で始める」ボタン
- 「詳しく見る」リンク

**デザインのポイント:**
```css
.cta-button {
  /* 目立つ色 */
  background: #ff6b6b;
  color: white;

  /* 大きなサイズ */
  padding: 16px 32px;
  font-size: 18px;

  /* 視線を引く */
  box-shadow: 0 4px 12px rgba(255,107,107,0.3);

  /* アニメーション */
  transition: transform 0.2s;
}

.cta-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(255,107,107,0.4);
}
```

**関連用語:** [コンバージョン](#コンバージョン-⭐⭐), [ボタン](#ボタン-button-⭐⭐⭐)

---

## より詳しく学ぶ

次のステップ:
- [技術・実装](./06-technical.md) - UIの実装方法を学ぶ
- [デザイン原則](./02-design-principles.md) - UXの基本原則を復習
- [レイアウト](./03-layout.md) - UIコンポーネントのレイアウトを学ぶ

[用語集トップに戻る](./README.md)
