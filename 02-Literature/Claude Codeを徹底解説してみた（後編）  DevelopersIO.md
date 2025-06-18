---
title: Claude Codeを徹底解説してみた（後編） | DevelopersIO
source: https://dev.classmethod.jp/articles/get-started-claude-code-2nd/
author:
  - "[[nokomoro3]]"
created: 2025-06-18
description: 
tags:
  - clippings
  - claude-code
---
# Claude Code 徹底解説（後編）要約
## 本記事について
- Claude Codeのセットアップから応用的な使用方法まで幅広く解説
- 前編ではセットアップ・基礎を説明し、本編は応用編を中心に記載

## MCPサーバーの追加
- MCPサーバーは`claude mcp add`コマンドで追加
- 追加後は`.mcp.json`に設定が保存される
- 起動時にサーバー利用の許可を求められる
- `/mcp`コマンドで接続状態やツール一覧を確認可能

## Permission（権限）について
- ツールごとにAllow（許可）とDeny（拒否）のルール設定が可能
- 一部ツールは明示的な許可が必要（Bash, Edit, WebFetchなど）
- 権限設定はスラッシュコマンド`/permission`か起動時オプションで行う
- 設定はローカルやプロジェクト単位で保存可能

## 消費トークン削減
- `/compact`コマンドで会話履歴を要約しトークン消費を削減
- 自動要約機能もあり設定変更可能
- `/clear`で履歴完全削除も可能

## memory(CLAUDE.md)の分割
- `@path/to/import`で複数ファイルのメモリを管理できる
- 最大5階層の再帰的インポートが可能
- `/memory`コマンドで読み込み状況を確認できる

## 拡張思考(Extended thinking)
- 複雑な思考が必要なタスクで有効
- キーワード（例：「もっと考えて」）で思考強化を促せる

## カスタムスラッシュコマンド
- Markdownファイルで独自コマンドを作成可能
- `$ARGUMENTS`で引数を渡せる

## Git worktreeの利用
- 複数タスクを並行処理するためにgit worktreeを活用
- ブランチ別に作業環境を分離しながら同時作業が可能

## GitHub Actions連携 (Claude Code Action)
- PRやIssueに`@claude`メンションで自動コードレビューや修正が可能
- GitHub CLIのセットアップが必要
- `/install-github-app`コマンドでセットアップ可能
- APIキーが必要で従量課金に注意
- 日本語化はワークフローYAMLのプロンプトを編集

## 参考情報
- Bedrock環境での利用方法もあり（環境変数設定で利用可能）
- トークン使用量と料金を可視化する非公式ツール`ccusage`の紹介

## スラッシュコマンド一覧（一部紹介）
- `/bug`: フィードバック送信
- `/clear`: 会話履歴削除
- `/compact`: 会話履歴要約
- `/config`: 設定パネル表示
- `/mcp`: MCPサーバー管理
- `/permission`: 権限管理
- `/review`: PRレビュー
- `/status`: 状態表示

## CLIコマンド例
- `claude`: 対話型REPL起動
- `claude \"query\"`: クエリ指定で起動
- `claude -p \"query\"`: 1回限りのクエリ
- `cat file | claude -p \"query\"`: パイプ入力処理

## 公式情報
- npmパッケージやドキュメントは随時更新中
- 最新情報は`--help`コマンドで確認推奨
- 公式ドキュメントやベストプラクティスリンク多数掲載

---

本記事はClaude Codeの高度な利用方法と連携機能を詳しく解説しており、実践的な設定や活用例が豊富に紹介されています。