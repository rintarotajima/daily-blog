---
title: "Astro入門：最初の一歩"
date: 2026-02-15
summary: "Astroの基本的なコンセプトとプロジェクト構成についての学習メモ。"
---

## Astroとは

Astroは、コンテンツ駆動のWebサイトを構築するためのフレームワーク。デフォルトでJavaScriptをクライアントに送らない「ゼロJS」アーキテクチャが特徴。

## プロジェクト構成

```
src/
├── content/     # コンテンツコレクション
├── layouts/     # レイアウトコンポーネント
├── pages/       # ページルーティング
└── components/  # 再利用可能なコンポーネント
```

## コンポーネントの基本

Astroコンポーネントは `.astro` ファイルで作成する。フロントマター部分でデータを取得し、テンプレート部分でHTMLを記述する。

```astro
---
const greeting = "Hello, Astro!";
const items = ["HTML", "CSS", "JavaScript"];
---

<h1>{greeting}</h1>
<ul>
  {items.map((item) => <li>{item}</li>)}
</ul>
```

## Content Collectionsの活用

Astro 5ではContent Layer APIが導入された。`src/content.config.ts` でスキーマを定義することで、フロントマターの型安全性を確保できる。

```typescript
import { defineCollection, z } from 'astro:content';
import { glob } from 'astro/loaders';

const blog = defineCollection({
  loader: glob({ pattern: '**/*.md', base: './src/content/blog' }),
  schema: z.object({
    title: z.string(),
    date: z.coerce.date(),
    summary: z.string(),
  }),
});
```

## まとめ

- Astroはコンテンツサイトに最適
- デフォルトでゼロJSなので高速
- Content Collectionsで型安全にコンテンツを管理できる
