# MCP Servers Configuration Guide
# MCPサーバー設定ガイド

This document provides detailed information about all 19 MCP servers configured for Claude Code integration.
このドキュメントでは、Claude Code統合用に設定された19個のMCPサーバーについて詳細に説明します。

## 📋 Table of Contents / 目次

### 🚀 [MCP Servers by Category](#-mcp-servers-by-category--カテゴリ別mcpサーバー)

#### 💾 Data & Backend / データ・バックエンド
- [1. Supabase MCP](#1-supabase-mcp) - PostgreSQL Database Services
- [2. Codex MCP](#2-codex-mcp) - Advanced Code Generation

#### 📚 Documentation & Context / ドキュメント・コンテキスト
- [3. Context7 MCP](#3-context7-mcp) - Library Documentation & Knowledge Base
- [4. Serena MCP](#4-serena-mcp) - Semantic Code Operations

#### 🎨 Design & Media / デザイン・メディア
- [5. Figma MCP](#5-figma-mcp) - Design File Operations
- [6. Chrome DevTools MCP](#6-chrome-devtools-mcp) - Browser Development Tools
- [7. FFmpeg MCP](#7-ffmpeg-mcp) - Video & Audio Processing
- [8. YouTube MCP](#8-youtube-mcp) - Video Platform Analysis
- [9. Veo3 MCP](#9-veo3-mcp) - AI Video Generation

#### 🛠️ Development & Testing / 開発・テスト
- [10. GitHub MCP](#10-github-mcp) - Repository Management
- [11. Playwright MCP](#11-playwright-mcp) - Browser Automation & Testing
- [12. File-system MCP](#12-file-system-mcp) - File Operations

#### 🔍 Communication & Search / コミュニケーション・検索
- [13. Slack MCP](#13-slack-mcp) - Team Communication
- [14. Perplexity MCP](#14-perplexity-mcp) - Real-time Search
- [15. Tavily MCP](#15-tavily-mcp) - Web Research

#### 🤖 AI & Productivity / AI・生産性
- [16. MulmoCast Vision MCP](#16-mulmocast-vision-mcp) - AI Slide Generation
- [17. Gemini MCP](#17-gemini-mcp) - Google AI Integration
- [18. Notion MCP](#18-notion-mcp) - Knowledge Management

#### 💳 Commerce / 商取引
- [19. Stripe MCP](#19-stripe-mcp) - Payment Processing

## 🔧 Environment Variables / 環境変数

### Required Environment Variables / 必要な環境変数

```bash
# Supabase MCP Server
SUPABASE_ACCESS_TOKEN=your_supabase_access_token_here
SUPABASE_PROJECT_REF=your_supabase_project_ref_here

# Context7 MCP Server (optional for higher rate limits)
CONTEXT7_API_KEY=your_context7_api_key_here

# Figma MCP Server
FIGMA_API_KEY=your_figma_api_key_here

# Veo3 MCP Server
GEMINI_API_KEY=your_gemini_api_key_here

# GitHub MCP Server
GITHUB_PERSONAL_ACCESS_TOKEN=your_github_personal_access_token_here

# Slack MCP Server
SLACK_BOT_TOKEN=xoxb-your_slack_bot_token_here
SLACK_TEAM_ID=your_slack_team_id_here

# Perplexity MCP Server
PERPLEXITY_API_KEY=your_perplexity_api_key_here

# Tavily MCP Server
TAVILY_API_KEY=your_tavily_api_key_here

# Notion MCP Server
NOTION_API_KEY=your_notion_api_key_here

# Gemini MCP Server
GOOGLE_API_KEY=your_google_api_key_here

# Stripe MCP Server
STRIPE_SECRET_KEY=your_stripe_secret_key_here

# File-system MCP Server
FILESYSTEM_PATH_1=/Users/madbarbarian/Desktop
FILESYSTEM_PATH_2=/Users/madbarbarian/Downloads
```

## 🚀 MCP Servers by Category / カテゴリ別MCPサーバー

### 💾 Data & Backend / データ・バックエンド

#### 1. Supabase MCP
**Purpose**: PostgreSQL database operations, authentication, and backend services
**目的**: PostgreSQLデータベース操作、認証、バックエンドサービス

- **Command**: `npx -y @supabase/mcp-server-supabase`
- **Environment Variables**: `SUPABASE_ACCESS_TOKEN`, `SUPABASE_PROJECT_REF`
- **Capabilities**: Database queries, table management, authentication

#### 2. Codex MCP
**Purpose**: Advanced code generation and analysis
**目的**: 高度なコード生成と分析

- **Command**: `codex mcp`
- **Type**: stdio
- **Capabilities**: AI-powered code generation, code analysis, architectural suggestions

### 📚 Documentation & Context / ドキュメント・コンテキスト

#### 3. Context7 MCP
**Purpose**: Library documentation and knowledge base access
**目的**: ライブラリドキュメントとナレッジベースアクセス

- **Command**: `npx -y @upstash/context7-mcp@latest`
- **Environment Variables**: `CONTEXT7_API_KEY` (optional)
- **Capabilities**: Library documentation lookup, code examples, best practices

#### 4. Serena MCP
**Purpose**: Semantic code understanding and operations
**目的**: セマンティックコード理解と操作

- **Command**: `uvx --from git+https://github.com/oraios/serena serena start-mcp-server`
- **Capabilities**: Semantic code analysis, refactoring, pattern recognition

### 🎨 Design & Media / デザイン・メディア

#### 5. Figma MCP
**Purpose**: Design file operations and integration
**目的**: デザインファイル操作と統合

- **Command**: `npx -y figma-developer-mcp --stdio`
- **Environment Variables**: `FIGMA_API_KEY`
- **Capabilities**: Design file access, component extraction, design system integration

#### 6. Chrome DevTools MCP
**Purpose**: Browser development tools and debugging
**目的**: ブラウザ開発ツールとデバッグ

- **Command**: `npx -y chrome-devtools-mcp@latest`
- **Capabilities**: Browser automation, performance monitoring, debugging

#### 7. FFmpeg MCP
**Purpose**: Video and audio processing
**目的**: ビデオ・オーディオ処理

- **Command**: `npx -y ffmpeg-mcp@latest`
- **Capabilities**: Video conversion, audio processing, multimedia manipulation

#### 8. YouTube MCP
**Purpose**: YouTube video analysis and interaction
**目的**: YouTubeビデオ分析とインタラクション

- **Command**: `npx -y @kirbah/mcp-youtube@latest`
- **Capabilities**: Video metadata extraction, transcript analysis, content discovery

#### 9. Veo3 MCP
**Purpose**: AI-powered video generation
**目的**: AI駆動ビデオ生成

- **Command**: `python3 -m mcp_veo3 --output-dir /tmp/veo3_videos`
- **Environment Variables**: `GEMINI_API_KEY`
- **Capabilities**: AI video creation, motion generation, visual storytelling

### 🛠️ Development & Testing / 開発・テスト

#### 10. GitHub MCP
**Purpose**: Repository management and version control
**目的**: リポジトリ管理とバージョン管理

- **Command**: `npx -y @modelcontextprotocol/server-github`
- **Environment Variables**: `GITHUB_PERSONAL_ACCESS_TOKEN`
- **Capabilities**: Repository operations, pull requests, issue management

#### 11. Playwright MCP
**Purpose**: Browser automation and end-to-end testing
**目的**: ブラウザ自動化とエンドツーエンドテスト

- **Command**: `npx -y @playwright/mcp`
- **Capabilities**: Browser automation, testing, screenshot capture

#### 12. File-system MCP
**Purpose**: File system operations and management
**目的**: ファイルシステム操作と管理

- **Command**: `npx -y @modelcontextprotocol/server-filesystem`
- **Environment Variables**: `FILESYSTEM_PATH_1`, `FILESYSTEM_PATH_2`
- **Capabilities**: File operations, directory management, content analysis

### 🔍 Communication & Search / コミュニケーション・検索

#### 13. Slack MCP
**Purpose**: Team communication and collaboration
**目的**: チームコミュニケーションとコラボレーション

- **Command**: `npx -y @modelcontextprotocol/server-slack`
- **Environment Variables**: `SLACK_BOT_TOKEN`, `SLACK_TEAM_ID`
- **Capabilities**: Message posting, channel management, team collaboration

#### 14. Perplexity MCP
**Purpose**: Real-time search and information retrieval
**目的**: リアルタイム検索と情報取得

- **Command**: `npx -y perplexity-mcp@latest`
- **Environment Variables**: `PERPLEXITY_API_KEY`
- **Capabilities**: Real-time search, fact-checking, current information

#### 15. Tavily MCP
**Purpose**: Comprehensive web research and analysis
**目的**: 包括的ウェブ研究と分析

- **Command**: `npx -y @tavily/mcp-server@latest`
- **Environment Variables**: `TAVILY_API_KEY`
- **Capabilities**: Deep web research, source validation, comprehensive analysis

### 🤖 AI & Productivity / AI・生産性

#### 16. MulmoCast Vision MCP
**Purpose**: AI-powered slide and presentation generation
**目的**: AI駆動スライド・プレゼンテーション生成

- **Command**: `npx mulmocast-vision@latest`
- **Capabilities**: Slide generation, presentation design, visual content creation

#### 17. Gemini MCP
**Purpose**: Google AI integration and assistance
**目的**: Google AI統合とアシスタンス

- **Command**: `npx -y gemini-mcp-tool@latest`
- **Environment Variables**: `GOOGLE_API_KEY`
- **Capabilities**: AI assistance, content generation, analysis

#### 18. Notion MCP
**Purpose**: Knowledge management and productivity
**目的**: ナレッジ管理と生産性

- **Command**: `npx -y @notionhq/notion-mcp-server`
- **Environment Variables**: `NOTION_API_KEY`
- **Capabilities**: Knowledge base management, documentation, task tracking

### 💳 Commerce / 商取引

#### 19. Stripe MCP
**Purpose**: Payment processing and subscription management
**目的**: 決済処理とサブスクリプション管理

- **Command**: `npx -y @stripe/mcp@latest --api-key ${STRIPE_SECRET_KEY}`
- **Environment Variables**: `STRIPE_SECRET_KEY`
- **Capabilities**: Payment processing, subscription management, financial operations

## ⚙️ Configuration & Setup / 設定

### .mcp.json Configuration / .mcp.json設定

All MCP servers are defined in the `.mcp.json` file with their respective commands and environment variables. The configuration uses environment variable substitution for secure credential management.

すべてのMCPサーバーは`.mcp.json`ファイルで定義され、各コマンドと環境変数が設定されています。設定では安全な認証情報管理のために環境変数の置換を使用しています。

### .claude/settings.local.json Configuration

The Claude Code settings file controls which MCP servers are enabled and defines security permissions for tool usage.

Claude Codeの設定ファイルでは、どのMCPサーバーが有効化されるかを制御し、ツール使用のセキュリティ権限を定義しています。

## 🆘 Troubleshooting / トラブルシューティング

### Common Issues / よくある問題

1. **Environment Variables Not Found**
   - Ensure all required environment variables are set in your `.env` file
   - Check that variable names match exactly (case-sensitive)

2. **MCP Server Connection Failures**
   - Restart Claude Code after configuration changes
   - Verify API keys and tokens are valid and have appropriate permissions

3. **Permission Denied Errors**
   - Check `.claude/settings.local.json` for appropriate permissions
   - Ensure file paths and domains are properly whitelisted

### Support Resources / サポートリソース

- Claude Code Documentation: https://docs.claude.com/
- MCP Protocol Documentation: https://modelcontextprotocol.io/
- Individual MCP server repositories on GitHub