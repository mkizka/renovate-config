# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

このリポジトリは、Renovateの共有設定を提供するライブラリです。他のプロジェクトから`extends`で参照して利用します。

## 設定ファイル

- `default.json`: ベースとなるRenovate設定
- `js-app.json`: JavaScriptアプリケーション用の設定
- `js-lib.json`: JavaScriptライブラリ用の設定

## 開発コマンド

```bash
# コードフォーマット
pnpm format

# Husky（Git hooks）のセットアップ
pnpm prepare
```

## アーキテクチャ

このリポジトリは、Renovateの設定プリセットを提供するシンプルな構成です：

1. **default.json**:
   - `config:best-practices`を拡張
   - 自動マージを有効化
   - minor/patchアップデートをグループ化
   - 毎週土曜日の朝4時（JST）に実行

2. **js-app.json/js-lib.json**:
   - default.jsonとそれぞれの設定を継承

## Git hooks

pre-commitフックでlint-stagedが実行され、Prettierによる自動フォーマットが適用されます。
