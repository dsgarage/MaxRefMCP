# MaxRefMCP

[English](README_en.md) | 日本語

**Max/MSP・Max4Live 日本語リファレンス MCP サーバー**

AI から Max/MSP のオブジェクトリファレンスを日本語で検索・参照できる [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) サーバーです。

> **MCP をサポートする AI クライアントであればどれでも利用できます。**
> Claude Code、Claude Desktop をはじめ、MCP の Streamable HTTP トランスポートに対応したクライアントであればそのまま接続可能です。

## 機能

| ツール | 説明 |
|---|---|
| `maxref.search_object` | オブジェクト名やキーワードで検索 |
| `maxref.get_object` | オブジェクトの詳細リファレンス取得 |
| `maxref.compare_objects` | 2〜5 個のオブジェクトを比較 |
| `maxref.explain_connection` | 2 オブジェクト間の接続方法を解説 |
| `maxref.rnbo_compatibility` | RNBO 互換性チェック＋代替提案 |
| `maxref.glossary` | Max/MSP 用語の日英辞書 |
| `maxref.search_pattern` | やりたいことから設計パターンを検索 |
| `maxref.search_package` | 外部パッケージ・ライブラリ検索 |
| `maxref.suggest_approach` | 実装アプローチの提案・壁打ち |
| `maxref.official_news` | Cycling '74 公式サイトの最新ニュース取得 |
| `maxref.rnbo_news` | RNBO / Move Takeover の最新情報取得 |
| `maxref.read_article` | 公式記事の詳細読み込み |
| `maxref.report_bug` | バグ報告 → GitHub Issue 自動作成 |
| `maxref.request_feature` | 機能リクエスト → GitHub Issue 自動作成 |
| `maxref.analytics` | API 利用状況サマリー取得 |

各ツールの詳細なパラメータ仕様は [Wiki — ツールリファレンス](https://github.com/dsgarage/MaxRefMCP/wiki/Tools) をご覧ください。

## クイックスタート

### Claude Code（CLI）

```bash
claude mcp add --transport http --scope project max-ref "https://maxrefmcp-production.up.railway.app/mcp"
```

### Claude Desktop

`claude_desktop_config.json` に追加:

```json
{
  "mcpServers": {
    "max-ref": {
      "type": "streamable-http",
      "url": "https://maxrefmcp-production.up.railway.app/mcp"
    }
  }
}
```

### その他の MCP 対応クライアント

以下の情報で接続できます:

| 項目 | 値 |
|---|---|
| エンドポイント URL | `https://maxrefmcp-production.up.railway.app/mcp` |
| トランスポート | Streamable HTTP |
| 認証 | 不要 |

詳しいセットアップ手順は [Wiki — セットアップガイド](https://github.com/dsgarage/MaxRefMCP/wiki/Setup) をご覧ください。

## 使い方

接続後、AI に Max/MSP について質問するだけで自動的にツールが呼び出されます。

```
「cycle~ と phasor~ の違いを教えて」
「FM 合成のパッチ設計を相談したい」
「gen~ で使えるオブジェクトを検索して」
「groove~ は RNBO で使える？」
```

活用例は [Wiki — 使い方・活用例](https://github.com/dsgarage/MaxRefMCP/wiki/Usage) をご覧ください。

## ドキュメント

| ページ | 内容 |
|---|---|
| [セットアップガイド](https://github.com/dsgarage/MaxRefMCP/wiki/Setup) | 各 AI クライアントへの導入方法 |
| [ツールリファレンス](https://github.com/dsgarage/MaxRefMCP/wiki/Tools) | 全 15 ツールのパラメータ仕様 |
| [使い方・活用例](https://github.com/dsgarage/MaxRefMCP/wiki/Usage) | 実際の使い方と質問例 |
| [FAQ](https://github.com/dsgarage/MaxRefMCP/wiki/FAQ) | よくある質問 |

## フィードバック

- **バグ報告**: [Issue を作成](https://github.com/dsgarage/MaxRefMCP/issues/new?template=bug_report.md)
- **機能リクエスト**: [Issue を作成](https://github.com/dsgarage/MaxRefMCP/issues/new?template=feature_request.md)
- MCP ツール内から `maxref.report_bug` / `maxref.request_feature` で直接報告することもできます

## リリースノート

[Releases](https://github.com/dsgarage/MaxRefMCP/releases) をご覧ください。

## 関連プロジェクト

- **[MaxMCP](https://github.com/dsgarage/MaxMCP)** — Max/MSP パッチの実操作（作成・接続・制御）を行う MCP サーバー

MaxRefMCP（調査・設計）と MaxMCP（パッチ操作）を両方接続すると、調査から実装まで一気通貫で AI と協業できます。

## 作者

**dsgarage** — [@dsgarage](https://x.com/dsgarage)

## ライセンス

MIT
