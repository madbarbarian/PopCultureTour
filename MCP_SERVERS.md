# MCP Servers Configuration Guide
# MCPサーバー設定ガイド

This document provides detailed information about all 21 MCP servers configured for SuperClaude + Claude Code integration.
このドキュメントでは、SuperClaude + Claude Code統合用に設定された21個のMCPサーバーについて詳細に説明します。

## 📋 Table of Contents / 目次

### 🧠 [SuperClaude Framework Integration](#-superclaudeフレームワーク統合)
### 🚀 [MCP Servers by Category](#-mcp-servers-by-category--カテゴリ別mcpサーバー)

#### 💾 Data & Development / データ・開発
- [1. Supabase MCP](#1-supabase-mcp) - Database & Backend Services
- [2. Codex MCP](#2-codex-mcp) - Advanced Code Generation
- [3. Sequential Thinking MCP](#3-sequential-thinking-mcp) - Advanced Reasoning
- [4. Context7 MCP](#4-context7-mcp) - Documentation & Knowledge Base
- [5. Magic MCP](#5-magic-mcp) - UI Component Generation

#### 🌐 Web & Automation / Web・自動化
- [6. Chrome DevTools MCP](#6-chrome-devtools-mcp) - Browser Operations
- [7. Playwright MCP](#7-playwright-mcp) - Web Automation & Testing
- [8. Filesystem MCP](#8-filesystem-mcp) - File Operations

#### 📊 Office & Productivity / オフィス・生産性
- [9. PowerPoint MCP](#9-powerpoint-mcp) - Presentation Creation
- [10. Excel MCP](#10-excel-mcp) - Spreadsheet Operations
- [11. Microsoft 365 MCP](#11-microsoft-365-mcp) - Office Suite Integration
- [12. Notion MCP](#12-notion-mcp) - Knowledge Management

#### 🎨 Design & Media / デザイン・メディア
- [13. Figma MCP](#13-figma-mcp) - Design File Operations
- [14. MulmoCast Vision MCP](#14-mulmocast-vision-mcp) - AI Slide Generation
- [15. FFmpeg MCP](#15-ffmpeg-mcp) - Video & Audio Processing
- [16. YouTube MCP](#16-youtube-mcp) - Video Analysis
- [17. Veo3 MCP](#17-veo3-mcp) - AI Video Generation

#### 🔍 Research & Communication / 研究・コミュニケーション
- [18. Perplexity MCP](#18-perplexity-mcp) - Real-time Search
- [19. Tavily MCP](#19-tavily-mcp) - Web Research
- [20. GitHub MCP](#20-github-mcp) - Repository Management
- [21. Slack MCP](#21-slack-mcp) - Team Communication

#### 🤖 AI & Code Analysis / AI・コード分析
- [22. Morphllm MCP](#22-morphllm-mcp) - Pattern-based Code Editing
- [23. Serena MCP](#23-serena-mcp) - Semantic Code Understanding
- [24. Gemini MCP](#24-gemini-mcp) - Google AI Integration
- [25. Gemini CLI MCP](#25-gemini-cli-mcp) - Advanced AI Terminal

### ⚙️ [Configuration & Setup](#-configuration--setup--設定)
### 🔧 [Environment Variables](#-environment-variables--環境変数)
### 🆘 [Troubleshooting](#-troubleshooting--トラブルシューティング)

## 🧠 SuperClaude Framework Integration / SuperClaudeフレームワーク統合

The MCP servers listed below work seamlessly with the SuperClaude framework, providing enhanced capabilities:
以下のMCPサーバーは、SuperClaudeフレームワークとシームレスに連携し、拡張機能を提供します：

- **Sequential Thinking**: Advanced reasoning and analysis / 高度な推論・分析
- **Context7**: Documentation and knowledge base integration / ドキュメント・知識ベース統合
- **Magic**: UI component generation with 21st.dev patterns / 21st.devパターンによるUIコンポーネント生成
- **Morphllm**: Pattern-based code transformations / パターンベースのコード変換
- **Tavily**: Real-time web search and research / リアルタイムWeb検索・研究
- **Playwright**: Browser automation and testing / ブラウザ自動化・テスト

### SuperClaude Mode Coordination / SuperClaudeモード連携
- **Brainstorm Mode** → Context7 (documentation), Tavily (research)
- **Task Management Mode** → Sequential (planning), Magic (UI implementation)
- **Business Panel Mode** → All MCP servers for comprehensive analysis

## 🚀 Available MCP Servers / 利用可能MCPサーバー

### 1. Supabase MCP
**Features / 機能**: Supabase database operations, migration management, Edge Functions
Supabaseデータベース操作、マイグレーション管理、Edge Functions
```json
"supabase": {
  "command": "npx",
  "args": ["-y", "@supabase/mcp-server-supabase", "--project-ref=mzcltskhvnvmenjmbmjp"],
  "env": {
    "SUPABASE_ACCESS_TOKEN": "sbp_ae5018a9c5959fe5e508b1d313b717faf40c2d05"
  }
}
```

**Use Cases / 使用例**:
- List database tables / データベーステーブルの一覧表示
- Execute SQL queries / SQLクエリの実行
- Apply migrations / マイグレーションの適用
- Deploy Edge Functions / Edge Functionsのデプロイ

### 2. Codex MCP
**Features / 機能**: Advanced code generation and analysis / 高度なコード生成と分析
```json
"codex": {
  "type": "stdio",
  "command": "codex",
  "args": ["mcp"]
}
```

**Use Cases / 使用例**:
- Complex programming task execution / 複雑なプログラミングタスクの実行
- Code optimization and improvement / コードの最適化と改善
- Project-wide analysis / プロジェクト全体の分析

### 3. Context7 MCP
**Features / 機能**: Latest library documentation retrieval / 最新ライブラリドキュメントの取得
```json
"context7": {
  "command": "npx",
  "args": ["-y", "@upstash/context7-mcp@latest"]
}
```

**Use Cases / 使用例**:
- Retrieve latest library documentation / ライブラリの最新ドキュメント取得
- Check API references / APIリファレンスの確認
- Get code examples / コード例の取得

### 4. Chrome DevTools MCP
**Features / 機能**: Browser automation and debugging / ブラウザ自動化とデバッグ
```json
"chrome-devtools": {
  "command": "npx",
  "args": ["-y", "chrome-devtools-mcp@latest"]
}
```

**Use Cases / 使用例**:
- Take webpage screenshots / Webページのスクリーンショット撮影
- Performance analysis / パフォーマンス分析
- Network request monitoring / ネットワークリクエストの監視
- User interaction simulation / ユーザー操作のシミュレーション

**Security Note / セキュリティ注意**: Avoid using on pages with sensitive or personal information.
機密情報や個人情報を含むページでの使用は避けてください。

### 5. Filesystem MCP
**Features / 機能**: Local filesystem access / ローカルファイルシステムへのアクセス
```json
"filesystem": {
  "command": "npx",
  "args": [
    "-y",
    "@modelcontextprotocol/server-filesystem",
    "/Users/madbarbarian/Desktop",
    "/Users/madbarbarian/Downloads"
  ]
}
```

**Accessible Folders / アクセス可能フォルダ**:
- Desktop / デスクトップ
- Downloads folder / ダウンロードフォルダ

**Use Cases / 使用例**:
- File read/write operations / ファイルの読み書き
- Check folder structure / フォルダ構造の確認
- File move/copy operations / ファイルの移動・コピー

### 6. YouTube MCP
**Features / 機能**: YouTube video subtitle extraction and summarization / YouTube動画の字幕取得と要約
```json
"youtube": {
  "command": "npx",
  "args": ["-y", "mcp-youtube@latest"]
}
```

**Use Cases / 使用例**:
- Generate YouTube video summaries / YouTube動画の要約生成
- Extract and analyze subtitles / 字幕の取得と分析
- Understand video content / 動画内容の理解

**Usage Example / 使用方法**:
```
このYouTube動画を要約して: https://youtube.com/watch?v=VIDEO_ID
```

### 7. Veo 3 MCP (AI Video Generation)
**Features / 機能**: Video generation using Google Veo 3 / Google Veo 3を使った動画生成
```json
"veo3": {
  "command": "python",
  "args": ["-m", "mcp_veo3"]
}
```

**Prerequisites / 使用前の準備**:
1. Install Python package / Pythonパッケージのインストール:
   ```bash
   pip install mcp-veo3
   ```
2. Set up Google Gemini API key / Google Gemini APIキーの設定
3. Subscribe to Google AI Ultra package (月額$249) / Google AI Ultraパッケージの契約

**Features / 機能**:
- Text-to-video generation / テキストから動画生成
- Image-to-video generation (animation) / 画像から動画生成（アニメーション化）
- Video with audio generation / 音声付き動画生成
- Multiple model support (Veo 3, Veo 3 Fast, Veo 2) / 複数モデル対応
- Various aspect ratio support / 様々なアスペクト比対応

**Use Cases / 使用例**:
- "Generate a video of a cat playing in the park" / "猫が公園で遊んでいる動画を生成して"
- "Animate this image" / "この画像をアニメーション化して"
- "Create a relaxing video of sunset by the sea" / "夕日の海辺でのリラックスした動画を作成"

**Important Notes / 注意事項**:
- Paid service (Google AI Ultra required) / 有料サービス（Google AI Ultra必須）
- High-quality video generation may take time / 高品質動画生成には時間がかかる場合があります

### 8. PowerPoint MCP
**Features / 機能**: PowerPoint presentation creation and editing / PowerPointプレゼンテーションの作成・編集
```json
"powerpoint": {
  "command": "python",
  "args": ["-m", "powerpoint_mcp_server"]
}
```

**Prerequisites / 使用前の準備**:
```bash
pip install powerpoint-mcp-server
```

**Use Cases / 使用例**:
- Automatic presentation generation / プレゼンテーションの自動生成
- Bulk slide editing / スライドの一括編集
- Template application / テンプレートの適用

### 9. Excel MCP
**Features / 機能**: Excel file creation, editing, and analysis / Excelファイルの作成・編集・分析
```json
"excel": {
  "command": "python",
  "args": ["-m", "excel_mcp_server"]
}
```

**Prerequisites / 使用前の準備**:
```bash
pip install excel-mcp-server
```

**Use Cases / 使用例**:
- Data analysis and chart creation / データ分析とグラフ作成
- Spreadsheet automation / スプレッドシートの自動化
- Report generation / レポート生成

### 10. Microsoft 365 MCP
**Features / 機能**: Microsoft 365 services integration / Microsoft 365サービスとの統合
```json
"microsoft365": {
  "command": "npx",
  "args": ["-y", "ms-365-mcp-server@latest"]
}
```

**Use Cases / 使用例**:
- OneDrive file access / OneDriveファイルアクセス
- Teams integration / Teams連携
- Outlook email operations / Outlookメール操作
- SharePoint integration / SharePointとの連携

### 11. Figma MCP
**Features / 機能**: Figma design file operations / Figmaデザインファイルの操作
```json
"figma": {
  "command": "npx",
  "args": ["-y", "@figma/mcp-server@latest"]
}
```

**Use Cases / 使用例**:
- Retrieve design files / デザインファイルの取得
- Extract component information / コンポーネント情報の抽出
- Analyze design elements / デザイン要素の分析

### 12. FFmpeg MCP
**Features / 機能**: Video and audio file conversion and editing / 動画・音声ファイルの変換・編集
```json
"ffmpeg": {
  "command": "npx",
  "args": ["-y", "ffmpeg-mcp@latest"]
}
```

**Prerequisites / 前提条件**: FFmpeg must be installed on the system / システムにFFmpegがインストールされている必要があります

**Use Cases / 使用例**:
- Video format conversion / 動画フォーマット変換
- Audio extraction / 音声抽出
- Video trimming and merging / 動画のトリミング・結合
- Resolution change / 解像度変更

### 13. MulmoCast Vision MCP
**Features / 機能**: AI-driven presentation slide generation / AI駆動のプレゼンテーションスライド生成
```json
"mulmocast-vision": {
  "command": "npx",
  "args": ["mulmocast-vision@latest"]
}
```

**Features / 機能**:
- 80+ business templates / 80以上のビジネステンプレート
- Natural language slide generation / 自然言語での指示でスライド生成
- HTML format with customization options / HTML形式でカスタマイズ可能
- Auto-save to `~/Documents/mulmocast-vision/` / `~/Documents/mulmocast-vision/`に自動保存

**Use Cases / 使用例**:
- "Create 20 business proposal slides" / "20枚のビジネス提案スライドを作成"
- "Generate presentation materials for data analysis results" / "データ分析結果のプレゼン資料生成"

### 14. GitHub MCP
**Features / 機能**: GitHub repository, Issues, and PR operations / GitHubリポジトリ・Issues・PRの操作
```json
"github": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-github"]
}
```

**Use Cases / 使用例**:
- Retrieve repository information / リポジトリ情報の取得
- Create and manage Issues and PRs / Issues・PRの作成・管理
- Code reviews / コードレビュー
- GitHub API integration / GitHub APIとの連携

### 15. Slack MCP
**Features / 機能**: Slack workspace integration / Slackワークスペースとの連携
```json
"slack": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-slack"]
}
```

**Use Cases / 使用例**:
- Send and receive messages / メッセージの送信・受信
- Channel management / チャンネル管理
- User information retrieval / ユーザー情報取得
- Notification settings / 通知設定

### 16. Perplexity MCP
**Features / 機能**: Real-time search using Perplexity Sonar API / Perplexity Sonar APIを使用したリアルタイム検索
```json
"perplexity": {
  "command": "npx",
  "args": ["-y", "perplexity-mcp@latest"]
}
```

**Prerequisites / 使用前の準備**: Set `PERPLEXITY_API_KEY` environment variable / `PERPLEXITY_API_KEY`環境変数の設定が必要

**Use Cases / 使用例**:
- Real-time information search / 最新情報のリアルタイム検索
- Web information summarization and analysis / Web情報の要約・分析
- Research and investigation support / 研究・調査支援

### 17. Serena MCP
**Features / 機能**: Semantic code understanding and analysis (coding agent toolkit) / セマンティックコード理解・分析（コーディングエージェントツールキット）
```json
"serena": {
  "command": "npx",
  "args": ["-y", "serena@latest"]
}
```

**Technical Features / 技術特徴**:
- Language Server Protocol (LSP) integration / Language Server Protocol (LSP) 統合
- Symbol-level code analysis / シンボルレベルでのコード分析
- IDE-level code operation capabilities / IDE レベルのコード操作機能
- Large codebase specialization / 大規模コードベースに特化

**Use Cases / 使用例**:
- Semantic code search and analysis / セマンティックコード検索・分析
- Automatic extraction of function/class definitions / 関数・クラス定義の自動抽出
- Code refactoring support / コードリファクタリング支援
- Dependency visualization / 依存関係の可視化

**Supported Languages / 対応言語**:
- Direct support / 直接サポート: TypeScript, JavaScript, Python, etc.
- Indirect support / 間接サポート: Ruby, Go, C#, etc.

### 18. Playwright MCP
**Features / 機能**: Browser automation and web operations (Microsoft official) / ブラウザ自動化・Web操作（Microsoft公式）
```json
"playwright": {
  "command": "npx",
  "args": ["-y", "@playwright/mcp"]
}
```

**Technical Features / 技術特徴**:
- Structured web operations without screenshots / 構造化データベースのWeb操作（スクリーンショット不要）
- Lightweight, high-speed processing using accessibility tree / アクセシビリティツリーを活用した軽量・高速処理
- LLM-friendly deterministic operations / LLMフレンドリーな決定論的操作
- Structured approach (not pixel-based) / ピクセルベースでない構造化アプローチ

**Use Cases / 使用例**:
- Web navigation and form input / Web Navigation・フォーム入力
- Data extraction from structured content / 構造化コンテンツからのデータ抽出
- LLM-driven automated test generation / LLM駆動の自動テスト生成
- JavaScript execution and screenshot capture / JavaScript実行・スクリーンショット撮影

**Features / 機能**:
- Page loading, element waiting, click operations / ページ読み込み・要素待機・クリック操作
- JavaScript evaluation and execution / JavaScript評価・実行
- Real browser environment operations / リアルブラウザ環境での操作

### 19. Notion API MCP
**Features / 機能**: Notion workspace integration (Notion official) / Notionワークスペース連携（Notion公式）
```json
"notion": {
  "command": "npx",
  "args": ["-y", "@notionhq/notion-mcp-server"]
}
```

**Technical Features / 技術特徴**:
- Secure workspace access via OAuth authentication / OAuth認証による安全なワークスペースアクセス
- AI-optimized Markdown format / AI最適化されたMarkdown形式
- Efficient data format / 効率的なデータフォーマット
- Full workspace read/write permissions / フルワークスペース読み書き権限

**Prerequisites / 使用前の準備**: Notion API token or OAuth configuration required / Notion APIトークンまたはOAuth設定が必要

**Use Cases / 使用例**:
- Automatic generation of documents, PRDs, technical specifications / ドキュメント・PRD・技術仕様書の自動生成
- Page and database read/write operations / ページ・データベースの読み書き操作
- Document creation from project data / プロジェクトデータからの資料作成
- User management and content structure management / ユーザー管理・コンテンツ構造管理

**Supported Operations / 対応操作**:
- Page creation, editing, deletion / ページ作成・編集・削除
- Database operations / データベース操作
- Comment management / コメント管理
- Content search and retrieval / コンテンツ検索・取得

### 20. Gemini MCP
**Features / 機能**: Google Gemini AI integration / Google Gemini AI統合
```json
"gemini": {
  "command": "npx",
  "args": ["-y", "mcp-gemini-server@latest"]
}
```

**Technical Features / 技術特徴**:
- Google Gemini 2.5 Pro model access / Google Gemini 2.5 Proモデルアクセス
- Multi-modal AI capabilities (text, image, code) / マルチモーダルAI機能（テキスト、画像、コード）
- Google Workspace API integration / Google Workspace API統合
- Natural language processing / 自然言語処理

**Use Cases / 使用例**:
- Advanced code generation and analysis / 高度なコード生成・分析
- Multi-modal content processing / マルチモーダルコンテンツ処理
- Google Workspace automation / Google Workspace自動化
- Natural language to API translation / 自然言語からAPI操作への変換

**Prerequisites / 前提条件**:
```bash
# Install Google AI SDK
npm install @google/generative-ai

# Set up API key
export GOOGLE_API_KEY="your-gemini-api-key"
```

**Integration Examples / 統合例**:
```
"Gemini APIでコード生成して"
"この画像を解析して"
"Gmail API呼び出しコードを作成"
```

### 21. Gemini CLI MCP
**Features / 機能**: Google Gemini CLI integration / Google Gemini CLI統合
```json
"gemini-cli": {
  "command": "npx",
  "args": ["-y", "@google/gemini-cli@latest"]
}
```

**Technical Features / 技術特徴**:
- Open-source AI agent terminal access / オープンソースAIエージェントターミナルアクセス
- ReAct (Reason and Act) loop with built-in tools / 組み込みツールとのReActループ
- FastMCP integration / FastMCP統合
- Local and remote MCP server support / ローカル・リモートMCPサーバーサポート

**Use Cases / 使用例**:
- Terminal-based AI assistance / ターミナルベースAIアシスタンス
- Complex use cases: bug fixing, feature creation / 複雑なユースケース：バグ修正、機能作成
- Test coverage improvement / テストカバレッジ改善
- Google Cloud integration / Google Cloud統合

**Installation / インストール**:
```bash
# Install Gemini CLI globally
npm install -g @google/gemini-cli@latest

# Install FastMCP for enhanced MCP support
pip install fastmcp>=2.12.3
```

**Advanced Usage / 高度な使用例**:
```
"プロジェクト全体を分析してバグを修正"
"テストカバレッジを改善"
"複雑なワークフローを自動実行"
```

## 🔗 Related Documentation / 関連ドキュメント

- **[CLAUDE_AGENTS.md](./CLAUDE_AGENTS.md)** - Claude Agents configuration / Claude Agents設定
- **[SETUP_GUIDE.md](./SETUP_GUIDE.md)** - Setup and troubleshooting / セットアップとトラブルシューティング
- **[PROJECT_STRUCTURE.md](./PROJECT_STRUCTURE.md)** - Project architecture / プロジェクトアーキテクチャ
- **[CLAUDE.md](./CLAUDE.md)** - Claude Code instructions / Claude Code指示書
- **[GEMINI.md](./GEMINI.md)** - Google Gemini instructions / Google Gemini向け指示書
- **[README.md](./README.md)** - Project overview / プロジェクト概要

---

*This document is regularly updated. Please update this document when new MCP servers are added.*
*このドキュメントは定期的に更新されます。新しいMCPサーバーが追加された際は、この文書も更新してください。*