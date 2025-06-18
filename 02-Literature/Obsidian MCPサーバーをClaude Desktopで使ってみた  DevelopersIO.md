---
title: Obsidian MCPサーバーをClaude Desktopで使ってみた | DevelopersIO
source: https://dev.classmethod.jp/articles/obsidian-mcp-claude-desktop-integration-hands-on/
author:
  - "[[とーち]]"
created: 2025-06-19
description: Obsidian MCPサーバーをClaude Desktopで使ってみた
tags:
  - clippings
  - obsidian
  - claude-desktop
---
# Obsidian MCPサーバーをClaude Desktopで使ってみた 要約

## 概要
- MCP（Model Context Protocol）サーバーの一つである「obsidian-mcp」をClaude Desktopで試した。
- Obsidianのノートを自然な会話で検索・参照できるようになる。

## インストール方法
- Claude DesktopをMCPクライアントとして使用。
- Node.jsがインストールされていれば使えるnpxコマンドを利用。
- インストールコマンド: `npx @smithery/cli install mcp-obsidian --client claude`
- インストール後、Claude Desktopの設定ファイル（claude_desktop_config.json）に設定が追加される。
- npxの絶対パスに修正が必要な場合あり。
- 設定完了後、Claude Desktopを再起動し、ハンマーアイコンをクリックすると新しいツールが追加されていることを確認。

## 実際に使ってみた
- Claude DesktopからObsidianノートに関する質問が可能。
- search_notesで関連ノート検索、read_notesでノート内容を読み込み回答を生成。
- ブログ下書きレビューなど多様な使い方が可能。
- 無料プランの制限があり、他のMCPクライアントも検討推奨。

## まとめ
- Obsidianノートの検索・参照が会話形式でできるため非常に便利。
- MCPサーバーによりAIアシスタントの能力拡張が期待できる。
- 安全なMCPサーバー選びが重要で、悪用事例もあるため注意が必要。

## 参考リンク
- MCP公式 Example Servers: https://modelcontextprotocol.io/examples
- Obsidian MCP GitHub: https://github.com/calclavia/mcp-obsidian
- Smithery MCP Registry: https://smithery.ai/
