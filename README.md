# MaxRefMCP

**Max/MSP・Max4Live 日本語リファレンス MCP サーバー**

Claude Code や Claude Desktop から Max/MSP のオブジェクトリファレンスを日本語で検索・参照できる MCP (Model Context Protocol) サーバーです。

## 機能

| ツール | 説明 |
|---|---|
| `maxref_search_object` | オブジェクト名やキーワードで検索 |
| `maxref_get_object` | オブジェクトの詳細リファレンス取得 |
| `maxref_compare_objects` | 2〜5 個のオブジェクトを比較 |
| `maxref_explain_connection` | 2 オブジェクト間の接続方法を解説 |
| `maxref_rnbo_compatibility` | RNBO 互換性チェック＋代替提案 |
| `maxref_glossary` | Max/MSP 用語の日英辞書 |
| `maxref_search_pattern` | やりたいことから設計パターンを検索 |
| `maxref_search_package` | 外部パッケージ・ライブラリ検索 |
| `maxref_suggest_approach` | 実装アプローチの提案・壁打ち |
| `maxref_report_bug` | バグ報告 → GitHub Issue 自動作成 |
| `maxref_request_feature` | 機能リクエスト → GitHub Issue 自動作成 |
| `maxref_analytics` | API 利用状況サマリー取得 |

## セットアップ

### Claude Code

プロジェクトディレクトリで以下を実行:

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

### .mcp.json（プロジェクト設定）

リポジトリ直下に `.mcp.json` を作成:

```json
{
  "mcpServers": {
    "max-ref": {
      "type": "http",
      "url": "https://maxrefmcp-production.up.railway.app/mcp"
    }
  }
}
```

## 使い方

接続後、Claude に Max/MSP について質問するだけで自動的にツールが呼び出されます。

```
「cycle~ と phasor~ の違いを教えて」
「FM 合成のパッチ設計を相談したい」
「gen~ で使えるオブジェクトを検索して」
```

## フィードバック

- **バグ報告**: [Issue を作成](https://github.com/dsgarage/MaxRefMCP/issues/new?template=bug_report.md)
- **機能リクエスト**: [Issue を作成](https://github.com/dsgarage/MaxRefMCP/issues/new?template=feature_request.md)
- MCP ツール内から `maxref_report_bug` / `maxref_request_feature` で直接報告することもできます

## リリースノート

[Releases](https://github.com/dsgarage/MaxRefMCP/releases) をご覧ください。

## 関連プロジェクト

- **[MaxMCP](https://github.com/dsgarage/MaxMCP)** — Max/MSP パッチの実操作（作成・接続・制御）を行う MCP サーバー

## ライセンス

MIT
