# Project Structure and File Documentation
# プロジェクト構造とファイル説明書

This document provides detailed explanations of the role, functionality, and usage of each directory and file within the project, organized by functional purpose.
このドキュメントでは、プロジェクト内の各ディレクトリとファイルの役割、機能、使用方法について機能別に詳しく説明します。

## 📁 Overall Project Structure / プロジェクト全体構造

```
(ref)dev_base/
├── .claude/                    # Claude Code Configuration / Claude Code設定
│   └── settings.local.json    # Permissions & MCP enablement / 権限・MCP有効化
├── .cursor/                    # Cursor IDE Settings & Development Rules / Cursor IDE設定・開発ルール
│   └── rules/                 # Development rules (6 specialized rules) / 開発ルール（6個の専門ルール）
├── .git/                      # Git History Management / Git履歴管理
├── docs/                      # Project Documentation / プロジェクトドキュメント
├── .env                       # Environment Variables (gitignored) / 環境変数（Git管理外）
├── .gitignore                 # Git ignore patterns / Git除外パターン
├── .mcp.json                  # MCP Server Definitions (21 servers) / MCPサーバー定義（21個）
├── (ref)dev_base.code-workspace # VS Code Workspace / VS Code ワークスペース
│
├── README.md                  # Project overview / プロジェクト概要
├── PROJECT_STRUCTURE.md       # This file / このファイル
│
├── CLAUDE.md                  # Claude Code instructions / Claude Code向け指示書
├── GEMINI.md                  # Google Gemini instructions / Google Gemini向け指示書
│
├── MCP_SERVERS.md             # MCP server configurations / MCPサーバー設定
├── CLAUDE_AGENTS.md           # AI agents setup / AIエージェント設定
├── SETUP_GUIDE.md             # Setup & troubleshooting / セットアップ・トラブルシューティング
└── GLOBAL_CONFIG.md           # Global configuration / グローバル設定
```

## 🤖 Claude Code Configuration (.claude) / Claude Code 設定 (.claude)

### `.claude/settings.local.json`
**Role / 役割**: Claude Code permission settings and MCP server enablement
Claude Codeの権限設定とMCPサーバー有効化

**Features / 機能**:
- Bash command execution permission settings / Bashコマンドの実行許可設定
- MCP server enablement / MCPサーバーの有効化
- Security control / セキュリティ制御

**Auto-approved Commands / 自動承認コマンド**:
- **Git Operations**: `git add`, `git commit`, `git push`, `git rebase`
- **NPM Operations**: `npm install`, `npm uninstall`, `npm cache clean`
- **Development Tools**: `gh` (GitHub CLI), `WebSearch`, `find`
- **System Tools**: `claude doctor`, `open`, `afplay`

**Security Constraints / セキュリティ制約**:
- **FileSystem Access**: Limited to Desktop, Downloads folders only
- **Web Fetch**: Restricted to github.com, zenn.dev domains
- **Sensitive Files**: .env*, secrets/, config/credentials.json read prohibited

**What you can do / 何ができるか**:
- ✅ Git operation automation / Git操作の自動化
- ✅ npm package management / npm パッケージ管理
- ✅ GitHub CLI operations / GitHub CLI操作
- ✅ Web search functionality / Web検索機能
- ✅ File search functionality / ファイル検索機能
- ✅ All 21 MCP server functions / 全21個のMCPサーバー機能


## 📖 Documentation Files / ドキュメントファイル

### Function-Based Documentation Organization / 機能軸ドキュメント構成

#### **Core Configuration / コア設定**
- **`MCP_SERVERS.md`**: Detailed MCP server configurations (21 servers) / 詳細MCPサーバー設定（21個）
- **`CLAUDE_AGENTS.md`**: AI agents setup and usage / AIエージェント設定・使用方法
- **`SETUP_GUIDE.md`**: Complete setup and troubleshooting guide / 完全セットアップ・トラブルシューティングガイド
- **`GLOBAL_CONFIG.md`**: System-wide configuration / システム全体設定

#### **AI Assistant Instructions / AIアシスタント向け指示書**
- **`CLAUDE.md`**: Claude Code project instructions (Primary) / Claude Code向けプロジェクト指示書（主要）
- **`GEMINI.md`**: Google Gemini project instructions (Secondary) / Google Gemini向けプロジェクト指示書（補助）

#### **Project Architecture / プロジェクト構造**
- **`README.md`**: Project overview and quick start / プロジェクト概要・クイックスタート
- **`PROJECT_STRUCTURE.md`**: This file - detailed structure documentation / このファイル - 詳細構造ドキュメント

### Function-Based Capabilities / 機能別能力

#### **Development Automation / 開発自動化**
- **Full-stack Development**: Supabase + GitHub + Context7 integration
- **AI Agents**: Code review, quality testing, task delegation
- **Code Tools**: Semantic analysis (Serena), advanced code generation (Codex)
- **Web Automation**: Chrome DevTools + Playwright for testing

#### **Content & Media Creation / コンテンツ・メディア作成**
- **Design Integration**: Figma for design workflows
- **Video Processing**: YouTube analysis + Veo3 AI generation + FFmpeg conversion
- **Document Generation**: PowerPoint + Excel + Microsoft 365 + Notion + MulmoCast Vision
- **Research & Information**: Perplexity real-time search + Context7 documentation

#### **Framework Extensions / フレームワーク拡張**
- **Behavioral Modes**: Brainstorm, Task-manage, Orchestrate modes
- **Business Analysis**: 9-expert business panel for strategic analysis
- **Advanced Commands**: `/sc:business-panel`, `/analyze`, `/research`, `/delegate`

## 🛠️ Configuration Files / 設定ファイル

### `.mcp.json` - MCP Server Definitions / MCPサーバー定義
**Role / 役割**: Model Context Protocol server configurations (21 servers)
**Details / 詳細**: See [MCP_SERVERS.md](./MCP_SERVERS.md) for complete configuration guide

**Server Categories / サーバーカテゴリ**:
- **Data & Development**: Supabase, Codex, Context7, GitHub
- **Web & Automation**: Chrome DevTools, Playwright, Filesystem
- **Media & Video**: YouTube, Veo3, FFmpeg
- **Office & Documents**: PowerPoint, Excel, Microsoft365, Notion
- **Design & UI**: Figma, MulmoCast Vision
- **Communication**: Slack, Perplexity
- **Code Analysis**: Serena
- **AI Integration**: Gemini, Gemini CLI

### Environment Variables / 環境変数
**File / ファイル**: `.env` (gitignored)
**Purpose / 目的**: API keys and sensitive configuration
**Required Keys / 必要キー**: SUPABASE_ACCESS_TOKEN, PERPLEXITY_API_KEY, GOOGLE_API_KEY, etc.

### `(ref)dev_base.code-workspace` - VSCode Workspace / VSCodeワークスペース
**Role / 役割**: VSCode project settings and editor configuration
**Function / 機能**: Unified editor settings across development environment

## 🚀 Development Workflow / 開発ワークフロー

### Function-Based Development Flow / 機能軸開発フロー

#### 1. **AI-Enhanced Development / AI拡張開発**
1. **CLAUDE.md** - Claude Code project context / Claude Codeプロジェクトコンテキスト
2. **MCP Servers** - Specialized tools activation / 専門ツール有効化
3. **AI Agents** - Code review and quality testing / コードレビュー・品質テスト
4. **Development Rules** - Quality assurance / 品質保証

#### 2. **Content Creation Workflow / コンテンツ作成ワークフロー**
1. **Research Phase** - Perplexity + Context7 for information gathering
2. **Design Phase** - Figma integration for design workflows
3. **Media Processing** - YouTube analysis → Veo3 generation → FFmpeg conversion
4. **Documentation** - PowerPoint + Excel + Microsoft 365 + Notion

#### 3. **Quality Assurance Process / 品質保証プロセス**
1. **Development Rules** - Cursor rules compliance / Cursor ルール遵守
2. **AI Agents** - Automated code review and testing / 自動コードレビュー・テスト
3. **Framework Extensions** - Advanced validation and analysis / 高度な検証・分析
4. **Security Standards** - Permission and access control / 権限・アクセス制御

## 🔐 セキュリティ・注意事項

### ファイル管理
- **機密情報**: `.env`ファイルで管理（`.gitignore`済み）
- **API キー**: Supabase, Clerk等のトークン適切管理
- **権限設定**: Claude Code権限の最小限化

### 開発ルール遵守
- **UI変更**: 既存UIの無許可変更禁止
- **コード標準**: 全ルールファイルの厳格遵守
- **タスク管理**: TODO更新の継続的実行

## 💡 Usage Optimization / 活用最適化

### Function-Based Integration Patterns / 機能軸統合パターン

#### **Development Automation Pipeline / 開発自動化パイプライン**
```
Basic workflow: Development → Supabase (DB) → GitHub (Version Control) → Chrome DevTools (Testing) → Notion (Docs)
AI Enhancement: AI Agents (code-reviewer, app-quality-tester) + Framework Extensions
```

#### **Content Creation Pipeline / コンテンツ作成パイプライン**
```
Media workflow: YouTube Analysis → Veo3 Generation → FFmpeg Processing → PowerPoint Presentation
Business Analysis: Framework Extensions (business panel) → Content Creation → Documentation
```

#### **Quality Assurance Workflow / 品質保証ワークフロー**
```
Code quality: Serena (semantic analysis) → code-reviewer (quality check) → GitHub (PR) → Slack (notification)
Enhanced: Task Management modes + Expert consultation + Quality validation
```

### Performance Optimization / パフォーマンス最適化

#### **MCP Server Coordination / MCPサーバー連携**
- **Parallel Operations**: Multiple MCP servers working simultaneously
- **Intelligent Routing**: Function-specific server selection
- **Resource Management**: Efficient memory and processing usage

#### **Framework Extensions / フレームワーク拡張**
- **Behavioral Modes**: Adaptive behavior based on task complexity
- **Business Expert Panel**: Strategic analysis for complex decisions
- **Advanced Commands**: Streamlined workflow automation

### Project Extension Guidelines / プロジェクト拡張ガイドライン

#### **Adding New Capabilities / 新機能追加**
1. **MCP Servers**: Update `.mcp.json` and `MCP_SERVERS.md`
2. **AI Agents**: Document in `CLAUDE_AGENTS.md`
3. **Development Rules**: Add to `.cursor/rules/` directory
4. **Configuration**: Update `SETUP_GUIDE.md` and `GLOBAL_CONFIG.md`

#### **Documentation Maintenance / ドキュメント保守**
- **Function-axis Organization**: Maintain capability-focused structure
- **Integration Documentation**: Update workflow examples
- **Setup Instructions**: Keep troubleshooting guides current
- **Version Tracking**: Document capability evolution

---

**🎯 Project Philosophy / プロジェクト哲学**: AI駆動開発環境により生産性を最大化し、品質保証とワークフロー自動化を実現する統合開発プラットフォームの提供

*This document evolves with project capabilities. When new functions or integrations are added, ensure documentation follows function-based organization principles.*

*このドキュメントはプロジェクト機能の進化と共に更新されます。新しい機能や統合が追加された際は、機能軸組織原則に従って文書化してください。*