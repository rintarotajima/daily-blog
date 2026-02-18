---
title: "TailwindCSSで覚えておきたいユーティリティ"
date: 2026-02-17
summary: "よく使うTailwindCSSのユーティリティクラスと実践的なパターンの備忘録。"
---

## レスポンシブデザイン

TailwindCSSのレスポンシブはモバイルファーストで設計されている。ブレークポイントのプレフィックスを付けることで、画面サイズに応じたスタイルを適用できる。

```html
<div class="text-sm md:text-base lg:text-lg">
  画面サイズに応じてフォントサイズが変わる
</div>
```

主なブレークポイント：

- `sm` — 640px以上
- `md` — 768px以上
- `lg` — 1024px以上
- `xl` — 1280px以上

## Flexboxレイアウト

カードを横並びにする典型的なパターン：

```html
<div class="flex flex-col md:flex-row gap-4">
  <div class="flex-1 p-4 bg-white rounded-lg shadow">カード1</div>
  <div class="flex-1 p-4 bg-white rounded-lg shadow">カード2</div>
  <div class="flex-1 p-4 bg-white rounded-lg shadow">カード3</div>
</div>
```

## ホバー・トランジション

インタラクティブな要素にはホバーエフェクトとトランジションを組み合わせる。

```css
/* TailwindCSSなら以下のクラスだけでOK */
/* hover:bg-blue-600 transition-colors duration-200 */
```

```html
<button class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded transition-colors duration-200">
  クリック
</button>
```

## まとめ

- レスポンシブはモバイルファーストで考える
- `flex` + `gap` で柔軟なレイアウト
- `transition-*` でスムーズなアニメーション
