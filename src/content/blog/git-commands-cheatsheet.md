---
title: "よく使うGitコマンド備忘録"
date: 2026-02-10
summary: "日常的に使うGitコマンドをカテゴリ別にまとめた個人用チートシート。"
---

## 基本操作

```bash
# リポジトリの初期化
git init

# 変更をステージング
git add .
git add -p  # 対話的に変更を選択

# コミット
git commit -m "コミットメッセージ"
```

## ブランチ操作

```bash
# ブランチの一覧を表示
git branch

# 新しいブランチを作成して切り替え
git switch -c feature/new-feature

# ブランチをマージ
git merge feature/new-feature
```

## 履歴の確認

`git log` はオプションによって出力形式を変えられる。

```bash
# コンパクトなログ表示
git log --oneline --graph

# 特定ファイルの変更履歴
git log --follow -p -- path/to/file

# 差分の確認
git diff              # ステージング前の差分
git diff --staged     # ステージング済みの差分
```

## 便利なテクニック

### 直前のコミットを修正

```bash
git commit --amend -m "修正後のメッセージ"
```

### 一時的に変更を退避

```bash
git stash
git stash pop    # 退避した変更を復元
git stash list   # 退避リストの確認
```

### 特定のコミットを取り込む

```bash
git cherry-pick <commit-hash>
```

## まとめ

- `git add -p` で意図した変更だけをステージング
- `git log --oneline --graph` で履歴を可視化
- `git stash` で作業を一時退避
