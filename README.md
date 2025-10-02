# Claude Code AI-Enhanced Development Environment
# Claude Code AI拡張開発環境

**Comprehensive AI-Powered Development Platform** - Claude Code + 22 MCP Servers + AI Agents + Framework Extensions
**包括的AI駆動開発プラットフォーム** - Claude Code + 22個のMCPサーバー + AIエージェント + フレームワーク拡張

## 🚀 Overview / 概要

This project provides a comprehensive AI-enhanced development environment with 22 MCP (Model Context Protocol) servers and specialized AI agents for Claude Code. It enables full-stack development, automation, and quality assurance through integrated AI-powered tools. Additionally, the SuperClaude framework provides advanced behavioral modes and business analysis capabilities.

このプロジェクトは、Claude Code用の22個のMCP（Model Context Protocol）サーバーと専門AIエージェントによる包括的なAI拡張開発環境を提供します。統合されたAI駆動ツールにより、フルスタック開発、自動化、品質保証を実現します。さらに、SuperClaudeフレームワークが高度な行動モードとビジネス分析機能を提供します。

### ⚡ Key Features / 主要機能

#### 🛠️ Development Automation / 開発自動化
- **🗄️ Full-stack Development / フルスタック開発**: Supabase + GitHub + Context7
- **🤖 AI Agents / AIエージェント**: Code review, quality testing, task delegation
- **🔧 Code Tools / コードツール**: Semantic analysis (Serena), advanced code generation (Codex)
- **🌐 Web Automation / Web自動化**: Chrome DevTools + Playwright for testing and automation

#### 📊 Content & Media Creation / コンテンツ・メディア作成
- **🎨 Design Integration / デザイン統合**: Figma for design workflows
- **📹 Video Processing / 動画処理**: YouTube analysis + Veo3 AI generation + FFmpeg conversion
- **📋 Document Generation / 文書生成**: PowerPoint + Excel + Microsoft 365 + Notion + MulmoCast Vision
- **🔍 Research & Information / 研究・情報収集**: Perplexity real-time search + Context7 documentation

#### 🧠 AI Integration / AI統合
- **🤖 Google AI / Google AI**: Gemini API + Gemini CLI for advanced AI capabilities
- **💬 Communication / コミュニケーション**: Slack integration for team workflows
- **📂 File Management / ファイル管理**: Filesystem access for local development

#### ✨ Framework Extensions / フレームワーク拡張
- **🎯 Behavioral Modes / 行動モード**: SuperClaude's Brainstorm, Task-manage, Orchestrate modes
- **💼 Business Analysis / ビジネス分析**: 9-expert business panel for strategic analysis
- **📋 Advanced Commands / 高度なコマンド**: `/sc:business-panel`, `/analyze`, `/research`, `/delegate`

## 💡 Usage Examples / 使用例

### Development Workflows / 開発ワークフロー
```bash
# Full-stack development with AI assistance / AI支援フルスタック開発
claude "implement user authentication"  # Triggers code-reviewer and app-quality-tester
supabase operations → github integration → chrome devtools testing

# Code quality improvement / コード品質改善
claude "review this codebase for performance issues"
# Uses Serena for semantic analysis → code-reviewer for suggestions
```

### Content Creation Workflows / コンテンツ作成ワークフロー
```bash
# Video content pipeline / 動画コンテンツパイプライン
youtube analysis → veo3 generation → ffmpeg processing → powerpoint presentation

# Document automation / 文書自動化
"Create presentation from data analysis results"
# Uses Excel/data → MulmoCast Vision → PowerPoint integration
```

### Research & Analysis / 研究・分析
```bash
# Real-time research / リアルタイム研究
perplexity search → context7 documentation → notion documentation

# Technical documentation / 技術文書作成
"Find latest React patterns and create implementation guide"
# Uses Context7 → AI analysis → Notion/document generation
```

### AI-Enhanced Features / AI拡張機能
```bash
# Business analysis (SuperClaude framework) / ビジネス分析（SuperClaude拡張）
/sc:business-panel @business_plan.pdf --mode discussion

# Advanced development modes / 高度な開発モード
claude --brainstorm "improve app architecture"  # SuperClaude brainstorm mode
claude --task-manage "implement complex feature"  # SuperClaude task management

# Expert consultation / 専門家コンサルテーション
/delegate "strategic analysis" --agents "porter-analyst,christensen-advisor"

# UI/UX Design Analysis / UI/UXデザイン分析
/uiux_comprehensive_audit  # Comprehensive UI/UX audit using Playwright

# Structured App Development / 構造化アプリ開発
/serena "implement user dashboard" -s -t  # Structured development with todos
/serena "debug performance issue" -q      # Quick debugging analysis
/serena "design auth system" -d -r        # Deep design with research
```

### Gemini Integration / Gemini統合
```bash
# Direct AI assistance / 直接AI支援
"Gemini APIでコード生成して"  # Direct API integration
"この画像を解析してください"  # Multi-modal analysis

# Advanced AI workflows / 高度なAIワークフロー
"プロジェクト全体を分析してバグを修正"  # Gemini CLI with MCP integration
```

## 📋 Quick Start / クイックスタート

### Prerequisites / 前提条件

```bash
# Required Environment / 必要な環境
- Claude Code or Claude Desktop
- Node.js (v16+) - Only if you plan to develop Node.js applications / Node.jsアプリケーション開発時のみ
- Python (3.8+)
- uv (Python package manager)
- volta (Node.js version manager) - Recommended for Node.js projects / Node.jsプロジェクト推奨
```

### Setup / セットアップ

1. **Clone Repository / リポジトリクローン**
   ```bash
   git clone <repository-url>
   cd (ref)dev_base
   ```

2. **Environment Variables Configuration / 環境変数設定**
   - Copy and customize `.env` file with your API keys / `.env`ファイルをコピーして、APIキーを設定
   - See [Environment Variables Section](#-environment-variables--環境変数) for details / 詳細は環境変数セクションを参照
   ```bash
   # Copy template and fill in your API keys
   cp .env .env.local  # Optional: create local copy
   # Edit .env with your actual API keys
   ```

3. **Check Claude Code Configuration / Claude Code設定確認**
   - Verify enabled MCP servers in `.claude/settings.local.json`
   - Configure environment variables as needed
   - `.claude/settings.local.json` で有効化されたMCPサーバーを確認
   - 必要に応じて環境変数設定

4. **Node.js Development Setup (Optional) / Node.js開発セットアップ（オプション）**
   ```bash
   # Only if planning Node.js development / Node.js開発を行う場合のみ
   # Volta is already configured for Node.js v22.20.0
   # voltaはNode.js v22.20.0用に設定済み
   volta list  # Check current configuration / 現在の設定確認
   ```

5. **Start Claude Code with Environment Variables / 環境変数付きでClaude Code起動**
   ```bash
   # Ensure .env file is loaded / .envファイルを確実に読み込み
   env $(grep -v '^#' .env | grep -v '^$' | xargs) claude
   ```

   **Alternative: Regular startup / 代替: 通常起動**
   - Restart Claude Code normally to apply configuration changes
   - 設定変更を反映させるため通常通りClaude Codeを再起動

## 🤖 AI Agents / AIエージェント

### Core Claude Agents / コアClaude Agents
**Built-in specialized agents for development workflows / 開発ワークフロー向け組み込み専門エージェント**

| Agent / エージェント | Function / 機能 | Usage / 使用場面 |
|---------|---------|------|
| **code-reviewer** | Code quality review and improvement suggestions / コード品質レビュー・改善提案 | After implementation, before PR |
| **app-quality-tester** | Comprehensive application testing / アプリケーション総合テスト | Feature completion, deployment prep |
| **uiux-designer** | UI/UX design analysis and improvement using Playwright / Playwright活用UI/UXデザイン分析・改善 | Design review, UX optimization |
| **serena-expert** | Token-efficient app development using Serena MCP / Serena MCP活用トークン効率的アプリ開発 | Component creation, API development, system architecture |

### Framework Extensions (SuperClaude) / フレームワーク拡張（SuperClaude）
**Additional specialized agents for complex workflows / 複雑ワークフロー向け追加専門エージェント**

| Domain / ドメイン | Agents / エージェント | Specialization / 専門分野 |
|---------|---------|------|
| **Development / 開発** | general-purpose | Multi-step tasks, orchestration |
| **Business / ビジネス** | porter-analyst, christensen-advisor, drucker-consultant, godin-marketer, collins-strategist | Strategic frameworks, innovation, management |
| **Analysis / 分析** | deep-researcher, synthesis-engine, pattern-detector | Research, integration, pattern recognition |
| **Quality / 品質** | quality-validator, memory-manager | Quality assurance, session management |

#### 💼 Business Expert Panel / ビジネス専門家パネル
Available through SuperClaude framework for strategic analysis:
SuperClaudeフレームワーク経由で戦略分析に利用可能：

- **Porter**: Competitive strategy / 競争戦略
- **Drucker**: Management fundamentals / 経営学基礎
- **Christensen**: Disruptive innovation / 破壊的イノベーション
- **Godin**: Marketing strategy / マーケティング戦略
- **Kim/Mauborgne**: Blue Ocean Strategy / ブルーオーシャン戦略
- **Collins**: Organizational excellence / 組織卓越性
- **Taleb**: Risk management / リスク管理
- **Meadows**: Systems thinking / システム思考
- **Doumont**: Clear communication / 明確なコミュニケーション

## 🔑 Environment Variables / 環境変数

### API Keys Configuration / APIキー設定

Most MCP servers require API keys for authentication. Configure them in the `.env` file:
ほとんどのMCPサーバーは認証にAPIキーが必要です。`.env`ファイルで設定してください：

```bash
# GitHub MCP Server
GITHUB_PERSONAL_ACCESS_TOKEN=your_github_personal_access_token_here

# Slack MCP Server (Required for Slack integration)
SLACK_BOT_TOKEN=xoxb-your_slack_bot_token_here

# Perplexity MCP Server
PERPLEXITY_API_KEY=your_perplexity_api_key_here

# Context7 MCP Server (optional for higher rate limits)
CONTEXT7_API_KEY=your_context7_api_key_here

# Google/Gemini MCP Servers
GOOGLE_API_KEY=your_google_api_key_here

# Figma MCP Server
FIGMA_ACCESS_TOKEN=your_figma_access_token_here

# Microsoft 365 MCP Server
MICROSOFT_CLIENT_ID=your_client_id_here
MICROSOFT_CLIENT_SECRET=your_client_secret_here

# Notion MCP Server
NOTION_API_KEY=your_notion_api_key_here

# Stripe MCP Server
STRIPE_SECRET_KEY=your_stripe_secret_key_here

# Supabase MCP Server
SUPABASE_ACCESS_TOKEN=your_supabase_access_token_here
SUPABASE_PROJECT_REF=your_supabase_project_ref_here
```

### How to Get API Keys / APIキーの取得方法

| Service | Where to Get API Key | Notes |
|---------|---------------------|--------|
| **GitHub** | [Settings > Developer settings > Personal access tokens](https://github.com/settings/tokens) | Requires repo, read:user permissions |
| **Slack** | [Slack API](https://api.slack.com/apps) → Create New App → OAuth & Permissions | Bot token starting with `xoxb-` (Required for team integration) |
| **Perplexity** | [Perplexity AI](https://www.perplexity.ai/settings/api) | Paid API access required for real-time search |
| **Context7** | [Context7 Dashboard](https://context7.com/dashboard) | Optional, provides higher rate limits |
| **Google/Gemini** | [Google AI Studio](https://aistudio.google.com/app/apikey) | Free tier available |
| **Figma** | [Figma Account Settings](https://www.figma.com/developers/api#authentication) | Personal access token |
| **Microsoft 365** | [Azure App Registration](https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) | OAuth app credentials |
| **Notion** | [Notion Integrations](https://www.notion.so/my-integrations) | Internal integration token |
| **Stripe** | [Stripe Dashboard](https://dashboard.stripe.com/apikeys) | Secret key for server-side ✅ Verified |
| **Supabase** | [Supabase Dashboard](https://supabase.com/dashboard) → Project Settings → API | Access token and project ref |

### Security Notes / セキュリティに関する注意

- **Never commit `.env` file to version control** / `.env`ファイルをバージョン管理にコミットしないでください
- **Use environment-specific files** / 環境固有のファイルを使用してください: `.env.local`, `.env.production`
- **Rotate API keys regularly** / APIキーを定期的にローテーションしてください
- **Grant minimal necessary permissions** / 必要最小限の権限のみを付与してください
- **Test MCP connections** / MCP接続をテストしてください: Check Claude Code status for connection issues

## 🛠️ MCP Servers (22) / MCPサーバー (22個)

**Specialized Model Context Protocol servers for enhanced Claude Code capabilities**
**Claude Code機能拡張のための専門化されたModel Context Protocolサーバー**

| Category / カテゴリ | Servers / サーバー | Features / 機能 |
|---------|---------|------|
| **Data & Development / データ・開発** | Supabase, Codex, Context7, GitHub | DB operations, code generation, documentation, repository management |
| **Web & Automation / Web・自動化** | Chrome DevTools, Playwright, Filesystem | Browser operations, web automation, file management |
| **Media & Video / メディア・動画** | YouTube, Veo3, FFmpeg | Video analysis, AI video generation, conversion processing |
| **Office & Documents / オフィス・文書** | PowerPoint, Excel, Microsoft365, Notion | Presentations, data analysis, document management |
| **Design & UI / デザイン・UI** | Figma, MulmoCast Vision, Playwright (via uiux-designer) | Design operations, AI slide generation, UI/UX analysis |
| **Communication / コミュニケーション** | Slack, Perplexity | Team collaboration, real-time search |
| **Payment & E-commerce / 決済・Eコマース** | Stripe | Payment processing, subscription management, financial data |
| **Code Analysis / コード分析** | Serena | Semantic code understanding, LSP integration |
| **AI Integration / AI統合** | Gemini, Gemini CLI | Google AI integration, multi-modal AI, terminal assistance |

## 📋 Commands / コマンド

**Comprehensive command framework for enhanced productivity and workflow automation**
**生産性向上とワークフロー自動化のための包括的なコマンドフレームワーク**

### SuperClaude Framework Commands / SuperClaudeフレームワークコマンド
- **Business Analysis**: `/sc:business-panel` - Multi-expert strategic analysis with 9 business frameworks
- **Deep Research**: `/research` - Multi-hop research with adaptive strategies and source validation
- **Advanced Analysis**: `/analyze --think-hard` - Comprehensive technical and strategic analysis
- **Task Delegation**: `/delegate` - Intelligent sub-agent coordination for complex workflows

### Project-Specific Commands / プロジェクト固有コマンド
- **Development**: `/test`, `/lint`, `/build` - Quality assurance and build automation
- **Git Integration**: `/commit` - Intelligent commit with automated analysis
- **MCP Server Management**: `/mcp` - Check MCP server status and connection health
- **UI Generation**: `/ui`, `/21` - Modern UI component generation from 21st.dev patterns
- **Logo Integration**: `/logo [company]` - Brand logo search and implementation
- **UI/UX Design**: `/uiux_comprehensive_audit` - Comprehensive UI/UX analysis and improvement using Playwright
- **App Development**: `/serena [task] [options]` - Token-efficient structured development using Serena MCP

## 📖 Documentation / ドキュメント

### **Core Documentation / コアドキュメント**
| File / ファイル | Purpose / 目的 | Description / 説明 |
|---------|---------|---------|
| **[README.md](./README.md)** | Project Overview | Main project guide and quick start |
| **[PROJECT_STRUCTURE.md](./PROJECT_STRUCTURE.md)** | Architecture Details | Detailed project structure and configuration |
| **[SETUP_GUIDE.md](./SETUP_GUIDE.md)** | Setup & Troubleshooting | Complete installation and troubleshooting guide |

### **Configuration Documentation / 設定ドキュメント**
| File / ファイル | Purpose / 目的 | Description / 説明 |
|---------|---------|---------|
| **[MCP_SERVERS.md](./MCP_SERVERS.md)** | MCP Server Config | 21 MCP servers configuration and usage |
| **[CLAUDE_AGENTS.md](./CLAUDE_AGENTS.md)** | AI Agents Setup | AI agents configuration and workflows |
| **[CLAUDE_COMMANDS.md](./CLAUDE_COMMANDS.md)** | Command Reference | SuperClaude commands and custom commands |
| **[DEVELOPMENT_RULES.md](./DEVELOPMENT_RULES.md)** | Development Standards | Coding standards and development rules |
| **[GLOBAL_CONFIG.md](./GLOBAL_CONFIG.md)** | Global Settings | System-wide configuration (~/.*) |

### **AI Assistant Instructions / AIアシスタント向け指示書**
| File / ファイル | Purpose / 目的 | Description / 説明 |
|---------|---------|---------|
| **[CLAUDE.md](./CLAUDE.md)** | Claude Instructions | Claude Code project instructions (Primary) |
| **[GEMINI.md](./GEMINI.md)** | Gemini Instructions | Google Gemini project instructions (Secondary) |

### **Framework Extensions / フレームワーク拡張**
**SuperClaude framework documentation in global configuration:**
**SuperClaudeフレームワークドキュメントはグローバル設定内に配置：**
- **Global Directory / グローバルディレクトリ**: `~/.claude/` directory with behavioral modes and expert knowledge
- **Advanced Features / 高度な機能**: Behavioral modes, business expert panel, specialized workflow agents

## 🔐 セキュリティ・権限

### 自動承認コマンド
```bash
# Git操作
git add, commit, push, rebase

# npm操作
npm install, uninstall, cache clean

# Node.js関連 (voltaが導入済み)
volta list, volta pin, volta install

# その他
gh (GitHub CLI), WebSearch, find
```

### アクセス制限
- **FileSystem MCP**: Desktop, Downloads フォルダのみ
- **Web Fetch**: github.com, zenn.dev ドメインのみ
- **機密ファイル**: .env*, secrets/, config/credentials.json 読み取り禁止

## 🚀 使用例

### Advanced Workflow Examples / 高度なワークフロー例

#### Full-stack Development Pipeline / フルスタック開発パイプライン
```bash
# Basic workflow / 基本ワークフロー
Development → Supabase (DB) → GitHub (Version Control) → Chrome DevTools (Testing) → Notion (Docs)

# With AI enhancement / AI拡張ワークフロー
AI Agents (serena-expert, code-reviewer, app-quality-tester, uiux-designer) + Gemini API + SuperClaude framework
```

#### Content Creation Pipeline / コンテンツ作成パイプライン
```bash
# Media workflow / メディアワークフロー
YouTube Analysis → Veo3 Generation → FFmpeg Processing → PowerPoint Presentation

# With business analysis / ビジネス分析付き
SuperClaude Business Panel (strategic analysis) → Content Creation → Documentation
```

#### Quality Assurance Workflow / 品質保証ワークフロー
```bash
# Code quality / コード品質
Serena (semantic analysis) → code-reviewer (quality check) → GitHub (PR) → Slack (notification)

# Enhanced with SuperClaude / SuperClaude拡張
Task Management modes + Expert consultation + Quality validation
```

## 💡 拡張・カスタマイズ

### 新MCPサーバー追加

1. `.mcp.json` にサーバー定義追加
2. `.claude/settings.local.json` で有効化
3. Claude Code再起動
4. `MCP_SERVERS.md` 更新

### Node.js開発環境準備

このプロジェクトは設定ファイルのみですが、Node.jsアプリケーション開発時は以下が利用可能：

1. **Volta Node.js バージョン管理**
   ```bash
   volta list              # 設定確認
   volta pin node@22.20.0  # バージョン固定 (設定済み)
   volta install yarn      # パッケージマネージャー追加
   ```

2. **プロジェクト初期化** (必要時)
   ```bash
   npm init -y             # package.json作成 (作成済み)
   npm install express     # 依存関係追加例
   ```

3. **設定の利点**
   - チーム全員で同じNode.jsバージョン使用
   - プロジェクト固有のバージョン管理
   - 自動バージョン切り替え

### 開発ルール追加

1. `.cursor/rules/` に新ルールファイル作成
2. `DEVELOPMENT_RULES.md` 更新

## 🆘 トラブルシューティング

### よくある問題

1. **MCPサーバー起動失敗**
   - Claude Code再起動
   - `.mcp.json` 構文チェック

2. **権限エラー**
   - `.claude/settings.local.json` 確認
   - 環境変数設定確認

3. **API認証エラー**
   - 各種APIキー設定確認
   - トークン有効性確認

4. **Slack MCPサーバー未接続**
   - `SLACK_BOT_TOKEN`環境変数の設定確認
   - [Slack API](https://api.slack.com/apps)でBot Token取得
   - `xoxb-`で始まるBot Tokenが必要
   - 設定後はClaude Code再起動

詳細は [SETUP_GUIDE.md](./SETUP_GUIDE.md#トラブルシューティング) を参照

## 📈 Update History / 更新履歴

- **2025年10月**: MCP Server Verification & Configuration Updates / MCPサーバー検証・設定更新
  - **Stripe MCP Integration**: Complete payment processing verification and testing / Stripe MCP統合：決済処理の完全検証・テスト
  - **Claude Code Agent Enhancement**: Added serena-expert and uiux-designer specialized agents / Claude Codeエージェント強化：serena-expert・uiux-designerエージェント追加
  - **Configuration Optimization**: Updated .mcp.json, permissions, and environment setup / 設定最適化：.mcp.json・権限・環境設定更新
  - **Documentation Updates**: Verified status markers and comprehensive testing results / ドキュメント更新：検証済みステータス・包括的テスト結果

- **2025年9月**: Framework Extensions & Documentation Restructure / フレームワーク拡張・ドキュメント再構築
  - **Framework Extensions**: SuperClaude framework integration with behavioral modes and business analysis / フレームワーク拡張：SuperClaudeフレームワーク統合（行動モード・ビジネス分析）
  - **Advanced AI Capabilities**: 15 specialized agents for complex workflows / 高度なAI機能：複雑ワークフロー向け15個の専門エージェント
  - **Documentation Optimization**: Function-based organization and role clarification / ドキュメント最適化：機能軸整理・役割明確化

- **2025年1月**: Complete MCP Ecosystem / 完全MCPエコシステム
  - **21 MCP Servers**: Complete integration including Gemini, Veo3, Office suite / 21個MCPサーバー：Gemini、Veo3、Officeスイート含む完全統合
  - **AI Agent Framework**: code-reviewer, app-quality-tester for development workflows / AIエージェントフレームワーク：開発ワークフロー向けエージェント
  - **Documentation System**: Comprehensive guides and technical references / ドキュメントシステム：包括的ガイド・技術リファレンス

- **2024年9月**: Foundation Development Environment / 基盤開発環境
  - **Core MCP Servers**: 19 servers for full-stack development / コアMCPサーバー：フルスタック開発向け19個サーバー
  - **Essential Integrations**: Database, version control, testing, office productivity / 必須統合：データベース、バージョン管理、テスト、オフィス生産性
  - **Development Rules**: Cursor IDE integration with specialized rules / 開発ルール：Cursor IDE統合・専門ルール

---

**🎯 このプロジェクトの目標**: AI駆動開発環境により生産性を最大化し、品質保証とワークフロー自動化を実現する統合開発プラットフォームの提供