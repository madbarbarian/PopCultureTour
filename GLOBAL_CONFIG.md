# Global Configuration Guide
# グローバル設定ガイド

**Purpose**: Comprehensive guide for system-wide configurations that apply across all projects
**目的**: 全プロジェクトに適用されるシステム全体設定の包括的ガイド

## 📋 Global Configuration Overview / グローバル設定概要

### **Global Configuration Directories / グローバル設定ディレクトリ**
| Directory / ディレクトリ | Purpose / 目的 | Configuration Type / 設定種別 |
|---------|---------|---------|
| **`~/.claude/`** | SuperClaude Framework | AI behavioral modes, business analysis |
| **`~/.codex/`** | Codex CLI Configuration | Advanced code generation settings |
| **`~/.config/`** | System Configuration | Git, GitHub CLI, various tools |
| **`~/.npm/`** | NPM Global Settings | Package management configuration |

### **Configuration Hierarchy / 設定階層**
```
Global (System-wide) / グローバル（システム全体）
├── ~/.claude/          # SuperClaude Framework
├── ~/.codex/           # Codex CLI
├── ~/.config/git/      # Git configuration
├── ~/.config/gh/       # GitHub CLI
└── ~/.npm/             # NPM global settings
```

## 🧠 **SuperClaude Framework (`~/.claude/`)**

### SuperClaude Global Configuration / SuperClaudeグローバル設定

**Location**: `~/.claude/`
**Purpose**: AI-enhanced development with behavioral modes and business analysis capabilities

#### **Core Framework Files / コアフレームワークファイル**
| File / ファイル | Purpose / 目的 | Content Type / 内容種別 |
|---------|---------|---------|
| **CLAUDE.md** | SuperClaude entry point | Framework integration point |
| **AGENTS.md** | Advanced AI agents | 15 specialized agents configuration |
| **COMMANDS.md** | Advanced slash commands | Command definitions and usage |
| **MODES.md** | Behavioral modes | 7 behavioral mode configurations |
| **RESEARCH_CONFIG.md** | Deep research settings | Multi-hop research configuration |

#### **Business Analysis Framework / ビジネス分析フレームワーク**
| File / ファイル | Expert / 専門家 | Framework / フレームワーク |
|---------|---------|---------|
| **BUSINESS_PANEL_EXAMPLES.md** | All Experts | Usage examples and patterns |
| **BUSINESS_SYMBOLS.md** | All Experts | Symbol system for efficiency |
| **BUSINESS_*.md** | Specific Experts | Individual framework definitions |

#### **Behavioral Modes Configuration / 行動モード設定**
| Mode File / モードファイル | Trigger / トリガー | Purpose / 目的 |
|---------|---------|---------|
| **MODE_Brainstorming.md** | Vague requests | Collaborative discovery |
| **MODE_Business_Panel.md** | Business analysis | Multi-expert strategic analysis |
| **MODE_DeepResearch.md** | Research commands | Systematic investigation |
| **MODE_Introspection.md** | Error recovery | Meta-cognitive analysis |
| **MODE_Orchestration.md** | Multi-tool operations | Intelligent tool selection |
| **MODE_Task_Management.md** | Complex tasks | Hierarchical organization |
| **MODE_Token_Efficiency.md** | Resource constraints | Symbol-enhanced communication |

## 🛠️ **Codex CLI Configuration (`~/.codex/`)**

### Codex CLI Advanced Code Generation / Codex CLI高度コード生成

**Location**: `~/.codex/`
**Purpose**: Advanced AI-powered code generation and analysis with session management

#### **Core Configuration Files / コア設定ファイル**
| File / ファイル | Purpose / 目的 | Content / 内容 |
|---------|---------|---------|
| **config.toml** | Main configuration | Model selection, security settings |
| **auth.json** | Authentication | API keys and tokens (secured) |
| **sessions/** | Session history | Previous coding sessions |
| **log/** | Operation logs | Debug and audit information |

#### **Model Configuration / モデル設定**
```toml
# ~/.codex/config.toml
[model]
# Default model for Codex sessions
default = "gpt-5-codex"  # or "claude-3-5-sonnet-20241022", "o3", "o4-mini"
provider = "openai"      # or "anthropic", "oss"

[sandbox]
# Security sandbox mode
mode = "workspace-write"  # read-only | workspace-write | danger-full-access
timeout = 300            # Session timeout in seconds

[approval]
# Command approval policy
policy = "on-request"    # untrusted | on-failure | on-request | never
```

#### **Available Models / 利用可能モデル**
| Provider / プロバイダ | Models / モデル | Use Case / 使用例 |
|---------|---------|---------|
| **OpenAI** | `gpt-4`, `gpt-5-codex`, `o3`, `o4-mini` | General coding, complex algorithms |
| **Anthropic** | `claude-3-5-sonnet-20241022`, `claude-3-opus` | Code review, architecture design |
| **Local/OSS** | Ollama models | Privacy-sensitive development |

#### **Security Modes / セキュリティモード**
| Mode / モード | Access Level / アクセスレベル | Use Case / 使用例 |
|---------|---------|---------|
| **read-only** | File reading only | Code analysis, review |
| **workspace-write** | Project directory only | Safe development |
| **danger-full-access** | Full system access | System administration |

## ⚙️ **System Configuration (`~/.config/`)**

### Development Tools Configuration / 開発ツール設定

**Location**: `~/.config/`
**Purpose**: System-wide development tool configurations

#### **Git Global Configuration / Git グローバル設定**
**Location**: `~/.config/git/config`

```ini
[user]
    name = Your Name
    email = your.email@example.com

[core]
    editor = code --wait
    autocrlf = input

[push]
    default = simple
    autoSetupRemote = true

[pull]
    rebase = true

[init]
    defaultBranch = main
```

#### **GitHub CLI Configuration / GitHub CLI設定**
**Location**: `~/.config/gh/config.yml`

```yaml
# GitHub CLI configuration
version: 1
git_protocol: ssh
editor: code --wait
prompt: enabled
pager: less

aliases:
    co: pr checkout
    pv: pr view
    pc: pr create

hosts:
    github.com:
        user: your-username
        oauth_token: your-token
        git_protocol: ssh
```

#### **NPM Global Configuration / NPM グローバル設定**
**Location**: `~/.npmrc`

```ini
# NPM global configuration
registry=https://registry.npmjs.org/
init-author-name=Your Name
init-author-email=your.email@example.com
init-license=MIT
save-exact=true
progress=true
```

## 🔐 **Environment Variables / 環境変数**

### Global Environment Configuration / グローバル環境設定

#### **Shell Configuration / シェル設定**
**Location**: `~/.zshrc` or `~/.bashrc`

```bash
# AI Development Environment Variables
export OPENAI_API_KEY="your-openai-key"
export ANTHROPIC_API_KEY="your-anthropic-key"
export GITHUB_TOKEN="your-github-token"

# Development Tools
export EDITOR="code --wait"
export NODE_ENV="development"

# Claude Code Integration
export CLAUDE_CONFIG_PATH="$HOME/.claude"
export CODEX_CONFIG_PATH="$HOME/.codex"

# Path additions
export PATH="$HOME/.codex/bin:$PATH"
export PATH="/usr/local/bin:$PATH"
```

#### **API Keys Management / APIキー管理**
| Service / サービス | Environment Variable / 環境変数 | Usage / 用途 |
|---------|---------|---------|
| **OpenAI** | `OPENAI_API_KEY` | Codex CLI, various MCP servers |
| **Anthropic** | `ANTHROPIC_API_KEY` | Claude integrations |
| **GitHub** | `GITHUB_TOKEN` | GitHub MCP server, gh CLI |
| **Google** | `GOOGLE_API_KEY` | Gemini MCP server |
| **Perplexity** | `PERPLEXITY_API_KEY` | Perplexity MCP server |

## 🌐 **Cloud Platform Configurations / クラウドプラットフォーム設定**

### Deployment and Infrastructure / デプロイとインフラ

#### **Vercel Configuration / Vercel設定**
**Location**: `~/.vercel/` (if exists)
**Purpose**: Deployment platform integration

#### **Cloudflare Wrangler / Cloudflare Wrangler**
**Location**: `~/.wrangler/` (if exists)
**Purpose**: Cloudflare Workers deployment

#### **AWS Configuration / AWS設定**
**Location**: `~/.aws/` (if exists)
**Purpose**: AWS service integration

## 🔄 **Configuration Synchronization / 設定同期**

### Cross-Machine Configuration Sync / マシン間設定同期

#### **Version Control for Configs / 設定のバージョン管理**
```bash
# Recommended approach for config sync
git init ~/.claude
git add ~/.claude/*.md
git commit -m "Initial SuperClaude configuration"

# Create private repository for sensitive configs
# (Exclude auth.json and API keys)
```

#### **Configuration Backup Strategy / 設定バックアップ戦略**
```bash
# Automated backup script
#!/bin/bash
BACKUP_DIR="$HOME/config-backup-$(date +%Y%m%d)"
mkdir -p "$BACKUP_DIR"

# Backup configurations (excluding sensitive files)
cp -r ~/.claude/*.md "$BACKUP_DIR/claude/"
cp ~/.codex/config.toml "$BACKUP_DIR/codex/"
cp ~/.config/git/config "$BACKUP_DIR/git/"
cp ~/.config/gh/config.yml "$BACKUP_DIR/gh/"

echo "Configuration backed up to $BACKUP_DIR"
```

## 📊 **Performance Optimization / パフォーマンス最適化**

### Global Performance Settings / グローバルパフォーマンス設定

#### **Memory and CPU Optimization / メモリとCPU最適化**
```toml
# ~/.codex/config.toml
[performance]
max_memory_mb = 4096
max_cpu_cores = 4
cache_enabled = true
cache_size_mb = 1024

[timeouts]
default_timeout = 300
long_running_timeout = 1800
```

#### **Cache Configuration / キャッシュ設定**
```bash
# Environment variables for caching
export CLAUDE_CACHE_SIZE="1GB"
export CODEX_CACHE_TTL="3600"  # 1 hour
export MCP_CACHE_ENABLED="true"
```

## 🛡️ **Security Configuration / セキュリティ設定**

### Global Security Standards / グローバルセキュリティ標準

#### **Credential Management / 認証情報管理**
- **API Keys**: Store in environment variables, never in config files
- **Authentication**: Use secure authentication methods (OAuth, SSH keys)
- **Access Control**: Implement least privilege principle
- **Audit Logging**: Enable logging for security monitoring

#### **File Permissions / ファイル権限**
```bash
# Secure configuration file permissions
chmod 600 ~/.codex/auth.json    # Codex authentication
chmod 600 ~/.ssh/id_*           # SSH keys
chmod 700 ~/.gnupg              # GPG keys
```

## 🔧 **Troubleshooting / トラブルシューティング**

### Common Configuration Issues / よくある設定問題

#### **Permission Issues / 権限問題**
```bash
# Fix common permission issues
chmod -R 755 ~/.claude/
chmod -R 755 ~/.codex/
chmod 600 ~/.codex/auth.json
```

#### **Environment Variable Issues / 環境変数問題**
```bash
# Verify environment variables
echo $OPENAI_API_KEY
echo $CLAUDE_CONFIG_PATH
echo $PATH | tr ':' '\n' | grep -E "(claude|codex)"
```

#### **Configuration Validation / 設定検証**
```bash
# Validate configurations
codex config validate
claude doctor
git config --list --global
```

---

**🎯 Configuration Philosophy / 設定哲学**: Global configurations should provide consistent, secure, and optimized environments across all projects while maintaining flexibility for project-specific needs.

**グローバル設定は、プロジェクト固有のニーズに対する柔軟性を維持しながら、全プロジェクトにわたって一貫性があり、安全で最適化された環境を提供すべきです。**

```toml
# Sandbox mode for command execution
sandbox = "workspace-write"  # "read-only", "workspace-write", "danger-full-access"

# Approval policy for shell commands
approval_policy = "untrusted"  # "untrusted", "on-failure", "on-request", "never"

# Sandbox permissions
sandbox_permissions = [
    "disk-read-access",
    "disk-write-access"
]
```

**Security Levels / セキュリティレベル**:
- **`read-only`**: Safe for exploration / 探索に安全
- **`workspace-write`**: Balanced for development / 開発に最適
- **`danger-full-access`**: Full system access (use with caution) / フルシステムアクセス（注意して使用）

#### Session Management / セッション管理

```toml
[session]
save_history = true         # Save session history
max_history = 50           # Maximum sessions to keep
auto_resume = false        # Auto-resume last session
```

### Configuration Profiles / 設定プロファイル

Codex supports multiple profiles for different use cases:

Codexは異なる用途に応じた複数のプロファイルをサポートします：

```toml
# Development profile - Full capabilities
[profiles.development]
model = "claude-3-5-sonnet-20241022"
sandbox = "workspace-write"
approval_policy = "untrusted"
web_search = true

# Production profile - Conservative settings
[profiles.production]
model = "gpt-4"
sandbox = "read-only"
approval_policy = "on-request"
web_search = false

# Research profile - Read-only exploration
[profiles.research]
model = "claude-3-5-sonnet-20241022"
sandbox = "read-only"
approval_policy = "never"
web_search = true
```

**Profile Usage / プロファイル使用**:
```bash
# Use specific profile
codex --profile development

# Override model for session
codex --model gpt-5-codex
```

### API Key Configuration / APIキー設定

```toml
# OpenAI settings
[models.openai]
api_key_source = "env"  # Use environment variable
# api_key_file = "~/.openai/api_key"  # Alternative: file-based

# Anthropic settings
[models.anthropic]
api_key_source = "env"
# api_key_file = "~/.anthropic/api_key"

# Local OSS (Ollama) settings
[models.oss]
host = "localhost"
port = 11434
```

**Environment Variables Required / 必要な環境変数**:
```bash
export OPENAI_API_KEY="your-openai-key"
export ANTHROPIC_API_KEY="your-anthropic-key"
```

### Tools and Features / ツール・機能

```toml
[tools]
# Enable web search capability
web_search = true

# Working directory (optional)
# working_directory = "/path/to/default/workspace"
```

### Shell Environment Policy / シェル環境ポリシー

```toml
[shell_environment_policy]
# Environment variable inheritance
inherit = "core"  # "all", "filtered", "none"
```

**Inheritance Levels / 継承レベル**:
- **`all`**: Inherit all environment variables / 全環境変数を継承
- **`filtered`**: Only safe variables / 安全な変数のみ
- **`core`**: Essential variables only / 必須変数のみ
- **`none`**: No inheritance / 継承なし

### Logging Configuration / ログ設定

```toml
[logging]
level = "info"                    # "debug", "info", "warn", "error"
file = "~/.codex/log/codex.log"   # Log file location
max_size = "10MB"                 # Maximum log file size
max_files = 5                     # Number of log files to retain
```

### MCP Integration / MCP統合

```toml
[mcp]
enabled = true       # Enable MCP server functionality
timeout = 30         # Default timeout for MCP operations (seconds)

[mcp.servers]
# MCP server configurations (typically managed through .mcp.json)
```

## 🎯 Claude Code Global Settings (`~/.claude/settings.json`)

### Location and Purpose / 配置と目的

```bash
# Configuration file location
~/.claude/settings.json
```

This file controls Claude Code's global behavior across all projects and sessions.

このファイルは、全プロジェクト・セッションでのClaude Codeのグローバル動作を制御します。

### Configuration Structure / 設定構造

```json
{
  "model": "opusplan"
}
```

**Available Models / 利用可能モデル**:
- **`opusplan`**: Planning-focused Opus model / プランニング重視のOpusモデル
- **`claude-3-5-sonnet`**: Balanced performance / バランス型性能
- **`claude-3-opus`**: Maximum capability / 最大機能
- **`claude-3-haiku`**: Fast responses / 高速応答

### Model Selection Guidelines / モデル選択ガイドライン

| Model | Use Case | Strengths | 使用ケース | 強み |
|-------|----------|-----------|------------|------|
| `opusplan` | Planning & Architecture | Strategic thinking | プランニング・アーキテクチャ | 戦略的思考 |
| `claude-3-5-sonnet` | General Development | Code quality | 一般開発 | コード品質 |
| `claude-3-opus` | Complex Projects | Deep analysis | 複雑プロジェクト | 深い分析 |
| `claude-3-haiku` | Quick Tasks | Speed | 素早いタスク | 速度 |

## 🔧 Setting Up Global Configuration / グローバル設定のセットアップ

### Initial Setup Steps / 初期セットアップ手順

1. **Create Configuration Directories / 設定ディレクトリ作成**
   ```bash
   mkdir -p ~/.codex/log
   mkdir -p ~/.claude
   ```

2. **Initialize Codex Configuration / Codex設定初期化**
   ```bash
   # Copy the reference configuration
   cp /path/to/reference/config.toml ~/.codex/config.toml

   # Edit configuration
   nano ~/.codex/config.toml
   ```

3. **Set Claude Code Global Model / Claude Codeグローバルモデル設定**
   ```bash
   echo '{"model": "opusplan"}' > ~/.claude/settings.json
   ```

4. **Configure Environment Variables / 環境変数設定**
   ```bash
   # Add to ~/.zshrc or ~/.bashrc
   export OPENAI_API_KEY="your-openai-key"
   export ANTHROPIC_API_KEY="your-anthropic-key"
   export GOOGLE_API_KEY="your-google-key"
   ```

### Verification / 確認

```bash
# Test Codex configuration
codex --version
codex --help

# Verify environment variables
echo $OPENAI_API_KEY
echo $ANTHROPIC_API_KEY

# Check Claude Code settings
cat ~/.claude/settings.json
```

## 🚀 Advanced Configuration / 高度な設定

### Custom Profile Creation / カスタムプロファイル作成

Create specialized profiles for different development scenarios:

異なる開発シナリオ用の専門プロファイルを作成：

```toml
# AI Research Profile
[profiles.ai-research]
model = "claude-3-opus"
sandbox = "read-only"
approval_policy = "never"
web_search = true

# Security Audit Profile
[profiles.security]
model = "gpt-4"
sandbox = "read-only"
approval_policy = "on-request"
web_search = false

# Rapid Prototyping Profile
[profiles.prototype]
model = "claude-3-haiku"
sandbox = "workspace-write"
approval_policy = "untrusted"
web_search = true
```

### Environment-specific Settings / 環境別設定

```toml
# Development environment
[profiles.dev]
model = "claude-3-5-sonnet-20241022"
sandbox = "workspace-write"
approval_policy = "untrusted"

# Staging environment
[profiles.staging]
model = "gpt-4"
sandbox = "read-only"
approval_policy = "on-request"

# Production environment
[profiles.prod]
model = "gpt-4"
sandbox = "read-only"
approval_policy = "on-request"
web_search = false
```

### Integration with Development Tools / 開発ツールとの統合

```toml
# IDE integration settings
[ide]
auto_complete = true
inline_suggestions = true
code_review = true

# Version control integration
[vcs]
auto_commit_messages = true
branch_suggestions = true
merge_conflict_resolution = true
```

## 📊 Performance Optimization / パフォーマンス最適化

### Resource Management / リソース管理

```toml
# Performance settings
[performance]
max_concurrent_sessions = 3
session_timeout = 1800  # 30 minutes
memory_limit = "2GB"
cpu_limit = 80  # Percentage
```

### Caching Configuration / キャッシュ設定

```toml
# Cache settings
[cache]
enabled = true
max_size = "1GB"
ttl = 3600  # 1 hour
compression = true
```

## 🔒 Security Best Practices / セキュリティベストプラクティス

### API Key Security / APIキーセキュリティ

1. **Use Environment Variables / 環境変数を使用**
   ```bash
   # Never store keys in configuration files
   # 設定ファイルにキーを保存しない
   export OPENAI_API_KEY="sk-..."
   ```

2. **Secure File Permissions / ファイル権限の保護**
   ```bash
   chmod 600 ~/.codex/config.toml
   chmod 600 ~/.claude/settings.json
   ```

3. **Regular Key Rotation / 定期的なキー更新**
   - Rotate API keys monthly / 月次でAPIキーを更新
   - Monitor usage patterns / 使用パターンを監視
   - Set up alerts for unusual activity / 異常なアクティビティのアラート設定

### Sandbox Security / サンドボックスセキュリティ

```toml
# Recommended security settings
sandbox = "workspace-write"  # Never use "danger-full-access" in production
approval_policy = "untrusted"  # Always require approval for untrusted commands

# Restrict file access
[security]
allowed_paths = [
    "~/workspace",
    "~/projects"
]
denied_paths = [
    "~/.ssh",
    "~/.aws",
    "/etc",
    "/usr"
]
```

## 🆘 Troubleshooting Global Configuration / グローバル設定のトラブルシューティング

### Common Issues / 一般的な問題

#### 1. Configuration File Not Found / 設定ファイルが見つからない

**Problem / 問題**: `~/.codex/config.toml` or `~/.claude/settings.json` missing

**Solution / 解決策**:
```bash
# Create missing directories
mkdir -p ~/.codex ~/.claude

# Initialize with default configuration
codex --init
```

#### 2. API Key Errors / APIキーエラー

**Problem / 問題**: Authentication failures

**Solution / 解決策**:
```bash
# Check environment variables
env | grep -E "(OPENAI|ANTHROPIC|GOOGLE)_API_KEY"

# Test API connectivity
curl -H "Authorization: Bearer $OPENAI_API_KEY" \
     "https://api.openai.com/v1/models"
```

#### 3. Permission Errors / 権限エラー

**Problem / 問題**: Commands not executing due to sandbox restrictions

**Solution / 解決策**:
```bash
# Check current configuration
codex --show-config

# Temporarily use less restrictive profile
codex --profile development
```

#### 4. Profile Not Loading / プロファイルが読み込まれない

**Problem / 問題**: Custom profiles not recognized

**Solution / 解決策**:
```bash
# Validate TOML syntax
codex --validate-config

# List available profiles
codex --list-profiles
```

### Diagnostic Commands / 診断コマンド

```bash
# System health check
codex --doctor

# Show current configuration
codex --show-config

# Test all API connections
codex --test-apis

# Validate configuration syntax
codex --validate-config
```

## 📚 Configuration Templates / 設定テンプレート

### Minimal Configuration / 最小構成

```toml
# Basic Codex configuration
model = "claude-3-5-sonnet-20241022"
model_provider = "anthropic"
sandbox = "workspace-write"
approval_policy = "untrusted"

[tools]
web_search = true

[models.anthropic]
api_key_source = "env"
```

### Full-featured Configuration / フル機能構成

```toml
# Complete Codex configuration with all features
model = "claude-3-5-sonnet-20241022"
model_provider = "anthropic"
sandbox = "workspace-write"
approval_policy = "untrusted"

[tools]
web_search = true

[session]
save_history = true
max_history = 100
auto_resume = false

[shell_environment_policy]
inherit = "core"

[logging]
level = "info"
file = "~/.codex/log/codex.log"
max_size = "10MB"
max_files = 5

[models.anthropic]
api_key_source = "env"

[models.openai]
api_key_source = "env"

[mcp]
enabled = true
timeout = 30

# Multiple profiles for different scenarios
[profiles.development]
model = "claude-3-5-sonnet-20241022"
sandbox = "workspace-write"
approval_policy = "untrusted"
web_search = true

[profiles.production]
model = "gpt-4"
sandbox = "read-only"
approval_policy = "on-request"
web_search = false

[profiles.research]
model = "claude-3-opus"
sandbox = "read-only"
approval_policy = "never"
web_search = true
```

## 🔗 Related Documentation / 関連ドキュメント

- **[README.md](./README.md)** - Project overview / プロジェクト概要
- **[SETUP_GUIDE.md](./SETUP_GUIDE.md)** - Project-specific setup / プロジェクト固有セットアップ
- **[MCP_SERVERS.md](./MCP_SERVERS.md)** - MCP server configurations / MCPサーバー設定
- **[CLAUDE_AGENTS.md](./CLAUDE_AGENTS.md)** - Claude agents setup / Claude エージェント設定
- **[PROJECT_STRUCTURE.md](./PROJECT_STRUCTURE.md)** - Project architecture / プロジェクトアーキテクチャ

---

**📝 Note**: This document covers system-wide configuration that affects all projects. For project-specific settings, refer to the individual project documentation.

**📝 注意**: この文書はすべてのプロジェクトに影響するシステム全体の設定を対象としています。プロジェクト固有の設定については、個別のプロジェクト文書を参照してください。