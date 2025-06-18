---
title: Obsidian Web Clipper × AI でWebページを自動要約＆ストックしてみた | DevelopersIO
source: https://dev.classmethod.jp/articles/try-obsidian-web-clipper-ai-summary/
author:
  - "[[toyoshima-masaya]]"
created: 2025-06-18
description: 
tags:
  - clippings
  - obsidian
  - AI
---
# Obsidian Web Clipper × AI でWebページを自動要約＆ストックしてみた

## 概要
- Obsidianのブラウザ拡張機能「Obsidian Web Clipper」を使い、Webページを自動で要約・保存する方法の紹介。
- 特にObsidianユーザーや、後で読みたい記事が溜まっている人におすすめ。

## インタープリターの設定方法
1. 拡張機能の設定画面で「インタープリター」を選択。
2. プロバイダーをGoogle GeminiやDeepSeek、OpenAIなどから選択しAPIキーを入力。
3. モデルを選択（例：Gemini 2.0 Flash）。
4. 詳細設定で`{{fullHtml}}`を指定。

## テンプレートの設定方法
- 「テンプレート」から保存先ディレクトリを指定。
- ノートの内容に要約プロンプトを設定。例：
  ```
  内容を簡潔に要約してください。また要点ごとにマークダウン形式で簡潔にまとめてください。その際、箇条書きや見出しを活用し重要なポイントが一目で分かるようにしてください。
  ```

## Webページの要約を試す
- 実際に記事を対象に拡張機能を使い、自動要約を試す。
- 要約は約2.5秒で完了し、簡潔で分かりやすい内容に。
- 元記事へのリンクもノートに含まれるため、詳細を確認可能。

## 最後に
- 気になる記事はこの方法で保存し、時間のあるときにObsidian内で整理するのが便利。
- 本記事がObsidianユーザーの参考になれば幸い。