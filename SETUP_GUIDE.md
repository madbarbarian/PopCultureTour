# Setup and Configuration Guide
# セットアップ・設定ガイド

This document provides comprehensive setup instructions for the SuperClaude framework + Claude Code + 21 MCP servers development environment.
このドキュメントでは、SuperClaudeフレームワーク + Claude Code + 21個のMCPサーバー開発環境の包括的なセットアップ手順を提供します。

## 🧠 SuperClaude Framework Setup / SuperClaudeフレームワークセットアップ

### Step 1: Global Configuration / ステップ1: グローバル設定

The SuperClaude framework is already configured in your global `~/.claude/` directory with:
SuperClaudeフレームワークは、以下の内容でグローバル`~/.claude/`ディレクトリに設定済みです：

- **15 Specialized Agents** / **15個の専門エージェント**: Development, Business, Analysis, Quality domains
- **5 Behavioral Modes** / **5つの行動モード**: Brainstorm, Introspect, Task-manage, Orchestrate, Token-efficient
- **Business Expert Panel** / **ビジネス専門家パネル**: 9 thought leaders for strategic analysis
- **Advanced Commands** / **高度なコマンド**: `/sc:business-panel`, `/analyze`, `/research`, `/delegate`

### Step 2: Verify SuperClaude Integration / ステップ2: SuperClaude統合確認

Test basic SuperClaude functionality:
基本的なSuperClaude機能をテスト：

```bash
# Test business analysis panel / ビジネス分析パネルのテスト
/sc:business-panel "test strategic analysis"

# Test behavioral modes / 行動モードのテスト
claude --brainstorm "explore new features"
claude --task-manage "complex implementation"

# Test specialized agents / 専門エージェントのテスト
/delegate "analyze code quality" --agents "code-reviewer"
```

## 🔧 Prerequisites / 前提条件

Before setting up MCP servers, ensure the following environment is ready. For system-wide configuration, see **[GLOBAL_CONFIG.md](./GLOBAL_CONFIG.md)**.
MCPサーバーを設定する前に、以下の環境が整っていることを確認してください。システム全体の設定については **[GLOBAL_CONFIG.md](./GLOBAL_CONFIG.md)** を参照してください。

### Required Software / 必要なソフトウェア

1. **Claude Desktop** or **Claude Code** installed / **Claude Desktop** または **Claude Code** がインストール済み
2. **Node.js** (v16+ recommended) - For npm-based MCP servers / **Node.js** (v16以上推奨) - npm経由のMCPサーバー用
3. **Python** (3.8+) - For Python-based MCP servers / **Python** (3.8以上) - Python系MCPサーバー用
4. **uv** (Python package manager) - Required for some MCP servers / **uv** (Pythonパッケージ管理) - 一部のMCPサーバーで必要

### Install uv (Python Package Manager) / uv のインストール

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Optional Tools / オプションツール

- **Google Cloud CLI** - For Google services integration / Google サービス統合用
- **FFmpeg** - For media processing MCP servers / メディア処理MCPサーバー用
- **Docker** - For containerized development / コンテナ化開発用

## 🚀 Installation Methods / インストール方法

### Method 1: Manual Configuration (Recommended - Current Method) / 方法1: 手動設定（推奨・現在の方法）

This is the most reliable method and what this project currently uses.
これが最も信頼性の高い方法で、このプロジェクトで現在使用している方法です。

**Steps / 手順**:

1. **Add server definition to `.mcp.json`** / **`.mcp.json`にサーバー定義を追加**

2. **Add server name to `enabledMcpjsonServers` array in `.claude/settings.local.json`** / **`.claude/settings.local.json`の`enabledMcpjsonServers`配列にサーバー名を追加**

3. **Restart Claude Code** / **Claude Codeを再起動**

### Method 2: Using mcp-installer / 方法2: mcp-installerを使用

Tool for installing MCP servers through conversational interface:
会話形式でMCPサーバーをインストールできるツール：

```bash
npx mcp-installer
```

**Note / 注意**: mcp-installer may not be perfect and manual configuration might be needed.
mcp-installerは完璧ではない場合があり、手動設定が必要になることがあります。

## 🔧 Detailed Setup Steps / 詳細セットアップ手順

### 1. Adding New MCP Servers (Manual Configuration) / 新しいMCPサーバーを追加する場合（手動設定）

#### Example Setup Process / セットアップ手順例

**Step 1: Update `.mcp.json`** / **ステップ1: `.mcp.json`を更新**

```json
{
  "mcpServers": {
    "new-server": {
      "command": "npx",
      "args": ["-y", "new-mcp-server@latest"]
    }
  }
}
```

**Step 2: Update `.claude/settings.local.json`** / **ステップ2: `.claude/settings.local.json`を更新**

```json
{
  "enabledMcpjsonServers": [
    "existing-server",
    "new-server"
  ]
}
```

**Step 3: Restart Claude Code** / **ステップ3: Claude Codeを再起動**

### 2. Permission Configuration / 権限設定

Claude Code's `settings.local.json` has pre-approved the following commands:
Claude Codeの`settings.local.json`では以下のコマンドが事前承認されています:

**Auto-approved Commands / 自動承認コマンド**:
- **Claude-related / Claude関連**: `claude doctor`, `claude --version`
- **npm-related / npm関連**: `npm install`, `npm uninstall`, `npm cache clean`, etc.
- **git-related / git関連**: `git init`, `git add`, `git commit`, `git push`, `git rebase`, etc.
- **Other tools / その他**: `gh` (GitHub CLI), `WebSearch`, `find`, `afplay` (audio playback), `gcloud`, `gemini`

**Denial Settings (Security Enhancement) / 拒否設定（セキュリティ強化）**:
- Reading `.env` files and `.env.*` files / `.env`ファイルおよび`.env.*`ファイルの読み取り禁止
- Reading files in `secrets/` directory / `secrets/`ディレクトリ内ファイルの読み取り禁止
- Reading `config/credentials.json` / `config/credentials.json`の読み取り禁止
- Reading `build/` directory / `build/`ディレクトリの読み取り禁止

### 3. Environment Variables Configuration / 環境変数の設定

Most MCP servers require API keys for authentication. This project uses a `.env` file for centralized credential management.
ほとんどのMCPサーバーは認証にAPIキーが必要です。このプロジェクトでは、認証情報の一元管理に`.env`ファイルを使用します。

#### Step 1: Configure .env File / ステップ1: .envファイルの設定

The project includes a `.env` template with all required environment variables. Edit the file with your actual API keys:
プロジェクトには必要な環境変数がすべて含まれた`.env`テンプレートが含まれています。実際のAPIキーでファイルを編集してください：

```bash
# Edit the .env file with your API keys
# 実際のAPIキーで .env ファイルを編集
nano .env
```

#### Step 2: Required API Keys / ステップ2: 必要なAPIキー

```bash
# GitHub MCP Server (Required for repository operations)
GITHUB_PERSONAL_ACCESS_TOKEN=your_github_personal_access_token_here

# Slack MCP Server (Required for team communication)
SLACK_BOT_TOKEN=xoxb-your_slack_bot_token_here

# Perplexity MCP Server (Required for real-time search)
PERPLEXITY_API_KEY=your_perplexity_api_key_here

# Context7 MCP Server (Optional for higher rate limits)
CONTEXT7_API_KEY=your_context7_api_key_here

# Google/Gemini MCP Servers (Required for AI integration)
GOOGLE_API_KEY=your_google_api_key_here

# Figma MCP Server (Optional for design operations)
FIGMA_ACCESS_TOKEN=your_figma_access_token_here

# Microsoft 365 MCP Server (Optional for Office integration)
MICROSOFT_CLIENT_ID=your_client_id_here
MICROSOFT_CLIENT_SECRET=your_client_secret_here

# Notion MCP Server (Optional for knowledge management)
NOTION_API_KEY=your_notion_api_key_here

# Stripe MCP Server (Required for payment processing)
STRIPE_SECRET_KEY=your_stripe_secret_key_here

# Supabase MCP Server (Required for database operations)
SUPABASE_ACCESS_TOKEN=your_supabase_access_token_here
SUPABASE_PROJECT_REF=your_supabase_project_ref_here
```

#### Step 3: API Key Sources / ステップ3: APIキー取得先

| Service | URL to Get API Key | Required Permissions |
|---------|-------------------|---------------------|
| **GitHub** | [GitHub Settings > Developer settings > Personal access tokens](https://github.com/settings/tokens) | `repo`, `read:user` |
| **Slack** | [Slack API Apps](https://api.slack.com/apps) → Create New App → OAuth & Permissions | Bot token (`xoxb-`) |
| **Perplexity** | [Perplexity AI API](https://www.perplexity.ai/settings/api) | Paid API access |
| **Context7** | [Context7 Dashboard](https://context7.com/dashboard) | Free account |
| **Google/Gemini** | [Google AI Studio](https://aistudio.google.com/app/apikey) | Free tier available |
| **Figma** | [Figma Account Settings > Personal access tokens](https://www.figma.com/developers/api#authentication) | Read-only access |
| **Microsoft 365** | [Azure Portal > App registrations](https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) | OAuth credentials |
| **Notion** | [Notion Integrations](https://www.notion.so/my-integrations) | Internal integration |
| **Stripe** | [Stripe Dashboard > API keys](https://dashboard.stripe.com/apikeys) | Secret key | ✅ Verified |
| **Supabase** | [Supabase Dashboard > Project Settings > API](https://supabase.com/dashboard) | Access token |

#### Step 4: Environment Variable Security / ステップ4: 環境変数のセキュリティ

- **Never commit `.env` files**: The `.gitignore` file already excludes `.env*` files
- **Use minimal permissions**: Grant only necessary permissions for each API key
- **Create environment-specific files**: Use `.env.local` for local development
- **Rotate keys regularly**: Update API keys periodically for security

### 4. Hook Configuration / フック設定

Claude Code is configured with several hooks for enhanced workflow:
Claude Codeはワークフロー強化のためにいくつかのフックが設定されています：

#### Stop Hook / Stopフック

Audio notification when Claude Code terminates:
Claude Code終了時の音声通知：

```json
"hooks": {
  "Stop": [
    {
      "matcher": "",
      "hooks": [
        {
          "type": "command",
          "command": "afplay /System/Library/Sounds/Glass.aiff"
        }
      ]
    }
  ]
}
```

**Stop Hook Features / Stopフック機能**:
- Play system sound (Glass.aiff) when Claude Code stops / Claude Code終了時にシステム音（Glass.aiff）を再生
- Provide audio feedback for task completion / タスク完了の音声フィードバック提供
- Use macOS standard audio files / macOS標準音声ファイルを使用

#### PostToolUse Hook / PostToolUseフック

Automatic formatting for TypeScript files after editing:
TypeScriptファイル編集時の自動フォーマット：

```json
"PostToolUse": [
  {
    "matcher": "Edit|MultiEdit|Write",
    "hooks": [
      {
        "type": "command",
        "command": "jq -r '.tool_input.file_path' | { read file_path; if echo \"$file_path\" | grep -q '\\.ts$'; then npx prettier --write \"$file_path\"; fi; }"
      }
    ]
  }
]
```

**PostToolUse Hook Features / PostToolUseフック機能**:
- Automatically execute after Edit/MultiEdit/Write tool usage / Edit/MultiEdit/Writeツール使用後に自動実行
- Format only TypeScript (.ts) files with Prettier / TypeScript（.ts）ファイルのみPrettierでフォーマット
- Maintain code quality automatically / コード品質の自動維持

## 🔑 API Keys and Authentication / APIキー・認証設定

### Google Services (Gemini, Workspace) / Google サービス（Gemini、Workspace）

1. **Create Google Cloud Project** / **Google Cloud プロジェクト作成**
   - Visit [Google Cloud Console](https://console.cloud.google.com/)
   - Create new project or select existing one

2. **Enable APIs** / **API有効化**
   ```bash
   gcloud services enable gmail.googleapis.com
   gcloud services enable calendar-json.googleapis.com
   gcloud services enable generativelanguage.googleapis.com
   ```

3. **Create API Key** / **APIキー作成**
   - Go to APIs & Services > Credentials
   - Create API key for Gemini API

4. **Set Environment Variable** / **環境変数設定**
   ```bash
   export GOOGLE_API_KEY="your-gemini-api-key"
   ```

### Supabase Configuration / Supabase設定

1. **Get Project Reference** / **プロジェクトリファレンス取得**
   - From Supabase dashboard URL
   - Format: `https://app.supabase.com/project/[PROJECT_REF]`

2. **Generate Access Token** / **アクセストークン生成**
   - Go to Account Settings > Access Tokens
   - Create new token with appropriate permissions

3. **Update Configuration** / **設定更新**
   ```json
   "supabase": {
     "command": "npx",
     "args": ["-y", "@supabase/mcp-server-supabase", "--project-ref=YOUR_PROJECT_REF"],
     "env": {
       "SUPABASE_ACCESS_TOKEN": "YOUR_ACCESS_TOKEN"
     }
   }
   ```

### GitHub Configuration / GitHub設定

1. **Create Personal Access Token** / **個人アクセストークン作成**
   - Go to GitHub Settings > Developer settings > Personal access tokens
   - Create token with required scopes (repo, issues, etc.)

2. **Set Environment Variable** / **環境変数設定**
   ```bash
   export GITHUB_TOKEN="your-github-token"
   ```

### Slack Configuration / Slack設定

1. **Create Slack App** / **Slack アプリ作成**
   - Visit [Slack API](https://api.slack.com/apps)
   - Create new app from manifest or scratch

2. **Configure Bot Permissions** / **Bot権限設定**
   - Add necessary scopes (channels:read, chat:write, etc.)
   - Install app to workspace

3. **Get Bot Token** / **Botトークン取得**
   ```bash
   export SLACK_BOT_TOKEN="xoxb-your-slack-bot-token"
   ```

### Notion Configuration / Notion設定

1. **Create Notion Integration** / **Notion統合作成**
   - Go to [Notion Developers](https://developers.notion.com/)
   - Create new integration

2. **Get Integration Token** / **統合トークン取得**
   ```bash
   export NOTION_API_TOKEN="secret_your-notion-token"
   ```

3. **Share Pages with Integration** / **統合にページ共有**
   - Add integration to specific pages or databases

## 🛠️ Specific Server Setup / 特定サーバーセットアップ

### Python-based Servers / Python系サーバー

**Veo 3 MCP** (AI Video Generation):
```bash
pip install mcp-veo3
export GOOGLE_API_KEY="your-gemini-api-key"
# Requires Google AI Ultra subscription ($249/month)
```

**PowerPoint MCP**:
```bash
pip install powerpoint-mcp-server
```

**Excel MCP**:
```bash
pip install excel-mcp-server
```

### Node.js-based Servers / Node.js系サーバー

Most servers are automatically installed via `npx` when first accessed. No additional setup required.
ほとんどのサーバーは最初のアクセス時に`npx`経由で自動インストールされます。追加設定は不要です。

### System Requirements / システム要件

**FFmpeg MCP**:
```bash
# macOS
brew install ffmpeg

# Ubuntu/Debian
sudo apt update && sudo apt install ffmpeg

# Windows
# Download from https://ffmpeg.org/download.html
```

**Chrome DevTools MCP**:
- Chrome or Chromium browser installed
- Sufficient system memory for browser automation

## 🆘 Troubleshooting / トラブルシューティング

### Common Issues and Solutions / 一般的な問題と解決方法

#### 1. MCP Server Won't Start / MCPサーバーが起動しない

**Symptoms / 症状**:
- Server appears offline in Claude Code
- Error messages in Claude Code logs

**Solutions / 解決方法**:
1. **Restart Claude Code** / **Claude Codeを再起動**
   ```bash
   # Close Claude Code completely and reopen
   ```

2. **Check Configuration Syntax** / **設定ファイルの構文エラーを確認**
   ```bash
   # Validate JSON syntax
   cat .mcp.json | jq .
   ```

3. **Verify Prerequisites** / **前提条件を確認**
   ```bash
   node --version    # Should be v16+
   python --version  # Should be 3.8+
   npm --version
   ```

#### 2. Permission Errors / 権限エラー

**Symptoms / 症状**:
- "Permission denied" errors
- Commands not executing

**Solutions / 解決方法**:
1. **Check Permission Settings** / **権限設定を確認**
   - Verify `.claude/settings.local.json` permissions
   - Ensure commands are in the `allow` list

2. **Verify API Keys** / **APIキーを確認**
   ```bash
   echo $GOOGLE_API_KEY
   echo $GITHUB_TOKEN
   # Should return your actual keys, not empty
   ```

#### 3. Dependency Errors / 依存関係エラー

**Symptoms / 症状**:
- Module not found errors
- Import/require failures

**Solutions / 解決方法**:
1. **Check Package Installation** / **パッケージインストールを確認**
   ```bash
   npm list -g  # Check global packages
   pip list     # Check Python packages
   ```

2. **Update Node.js and Python** / **Node.jsとPythonを更新**
   ```bash
   # Update Node.js via version manager
   nvm install --lts

   # Update Python packages
   pip install --upgrade pip
   ```

3. **Install uv Tool** / **uvツールのインストール**
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

#### 4. Performance Issues / パフォーマンスの問題

**Symptoms / 症状**:
- Slow MCP server responses
- High CPU/memory usage

**Solutions / 解決方法**:
1. **Disable Unused Servers** / **不要なサーバーを無効化**
   ```json
   // Remove unused servers from enabledMcpjsonServers
   "enabledMcpjsonServers": [
     "essential-server-1",
     "essential-server-2"
   ]
   ```

2. **Monitor Resource Usage** / **リソース使用量を監視**
   ```bash
   # Check system resources
   top -p $(pgrep -f mcp)
   ```

3. **Optimize File Operations** / **ファイル操作を最適化**
   - Avoid operations on large files
   - Use specific file paths instead of directory scanning

### Server-specific Troubleshooting / サーバー別トラブルシューティング

#### Supabase MCP
- **Issue**: Access token errors / アクセストークンエラー
- **Solution**: Verify token and project ID / トークンとプロジェクトIDを確認
  ```bash
  curl -H "Authorization: Bearer $SUPABASE_ACCESS_TOKEN" \
       "https://api.supabase.com/v1/projects"
  ```

#### Perplexity MCP
- **Issue**: API key errors / APIキーエラー
- **Solution**: Check `PERPLEXITY_API_KEY` environment variable
  ```bash
  echo $PERPLEXITY_API_KEY  # Should not be empty
  ```

#### Veo 3 MCP
- **Issue**: Subscription errors / サブスクリプションエラー
- **Solution**: Verify Google AI Ultra subscription / Google AI Ultraサブスクリプションを確認

#### FFmpeg MCP
- **Issue**: FFmpeg not found / FFmpegが見つからない
- **Solution**: Install FFmpeg system-wide / システム全体にFFmpegをインストール
  ```bash
  which ffmpeg  # Should return path to ffmpeg
  ```

#### Serena MCP
- **Issue**: Language server errors / Language Serverエラー
- **Solution**: Check LSP configuration and supported languages
  ```bash
  # Verify language server installation
  which typescript-language-server
  which pylsp
  ```

#### Playwright MCP
- **Issue**: Browser automation failures / ブラウザ自動化の失敗
- **Solution**: Install browser dependencies and check permissions
  ```bash
  npx playwright install
  npx playwright install-deps
  ```

#### Notion MCP
- **Issue**: OAuth/API authentication failures / OAuth/API認証の失敗
- **Solution**: Verify API token and integration permissions
  ```bash
  curl -H "Authorization: Bearer $NOTION_API_TOKEN" \
       -H "Notion-Version: 2022-06-28" \
       "https://api.notion.com/v1/users/me"
  ```

## 🔍 Diagnostic Commands / 診断コマンド

### System Health Check / システムヘルスチェック

```bash
# Check all prerequisites
echo "Node.js: $(node --version)"
echo "Python: $(python --version)"
echo "npm: $(npm --version)"
echo "uv: $(uv --version)"

# Check environment variables
echo "Google API Key: ${GOOGLE_API_KEY:+SET}"
echo "GitHub Token: ${GITHUB_TOKEN:+SET}"
echo "Slack Token: ${SLACK_BOT_TOKEN:+SET}"
```

### MCP Configuration Validation / MCP設定検証

```bash
# Validate .mcp.json syntax
jq empty .mcp.json && echo "Valid JSON" || echo "Invalid JSON"

# Check enabled servers
jq -r '.enabledMcpjsonServers[]' .claude/settings.local.json

# Count total servers
jq '.mcpServers | length' .mcp.json
```

### Log Analysis / ログ分析

```bash
# Check Claude Code logs (macOS)
tail -f ~/Library/Logs/Claude\ Code/main.log

# Check system logs for MCP processes
ps aux | grep mcp
```

## 📚 Additional Resources / 追加リソース

### Official Documentation / 公式ドキュメント
- **[Model Context Protocol](https://modelcontextprotocol.io)** - Official MCP documentation
- **[Claude Code Documentation](https://docs.claude.com/en/docs/claude-code)** - Claude Code user guide

### Community Resources / コミュニティリソース
- **[Glama](https://glama.ai/mcp/servers)** - Open-source MCP server directory
- **[PulseMCP.com](https://www.pulsemcp.com)** - MCP server directory
- **[Awesome MCP Servers](https://github.com/wong2/awesome-mcp-servers)** - Community-maintained list

### Development Resources / 開発リソース
- **[MCP SDK](https://github.com/modelcontextprotocol)** - For building custom servers
- **[mcp-installer](https://www.npmjs.com/package/mcp-installer)** - Interactive installation tool

## 🔗 Related Documentation / 関連ドキュメント

- **[GLOBAL_CONFIG.md](./GLOBAL_CONFIG.md)** - System-wide configuration guide / システム全体設定ガイド
- **[MCP_SERVERS.md](./MCP_SERVERS.md)** - Detailed MCP server information / 詳細MCPサーバー情報
- **[CLAUDE_AGENTS.md](./CLAUDE_AGENTS.md)** - Claude Agents configuration / Claude Agents設定
- **[PROJECT_STRUCTURE.md](./PROJECT_STRUCTURE.md)** - Project architecture / プロジェクトアーキテクチャ
- **[CLAUDE.md](./CLAUDE.md)** - Claude Code instructions / Claude Code指示書
- **[GEMINI.md](./GEMINI.md)** - Google Gemini instructions / Google Gemini向け指示書
- **[README.md](./README.md)** - Project overview / プロジェクト概要

---

*This document is regularly updated. Please update this document when new setup procedures or troubleshooting solutions are discovered.*
*このドキュメントは定期的に更新されます。新しいセットアップ手順やトラブルシューティング解決策が発見された際は、この文書も更新してください。*