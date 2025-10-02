# Claude Commands Reference
# Claude コマンドリファレンス

**Purpose**: Comprehensive command reference for SuperClaude framework and custom commands
**目的**: SuperClaudeフレームワークとカスタムコマンドの包括的コマンドリファレンス

## 📋 Command Categories / コマンドカテゴリ

### **Global Commands (SuperClaude Framework) / グローバルコマンド（SuperClaudeフレームワーク）**
| Command / コマンド | Purpose / 目的 | Configuration / 設定 |
|---------|---------|---------|
| `/sc:business-panel` | Multi-expert business analysis | ~/.claude/BUSINESS_*.md |
| `/sc:research` | Deep research with multi-hop analysis | ~/.claude/RESEARCH_CONFIG.md |
| `/sc:load` | Restore project context and session state | ~/.claude/AGENTS.md |
| `/sc:save` | Persist project state and learning patterns | ~/.claude/AGENTS.md |
| `/analyze` | Technical and strategic analysis | ~/.claude/COMMANDS.md |
| `/improve` | Iterative enhancement with validation cycles | ~/.claude/COMMANDS.md |
| `/design` | Solution design with expert guidance | ~/.claude/COMMANDS.md |
| `/delegate` | Sub-agent task delegation | ~/.claude/AGENTS.md |
| `/workflow` | Execute predefined or custom workflows | ~/.claude/COMMANDS.md |

### **Project Commands (Local Configuration) / プロジェクトコマンド（ローカル設定）**
| Command / コマンド | Purpose / 目的 | Configuration / 設定 |
|---------|---------|---------|
| `/ui` or `/21` | UI component generation | MCP Magic server |
| `/logo [company]` | Logo search and integration | MCP Magic server |
| `/commit` | Intelligent git commit with analysis | .claude/settings.local.json |
| `/test` | Run project-specific test suites | CLAUDE.md project instructions |
| `/lint` | Code quality and style checking | DEVELOPMENT_RULES.md |
| `/deploy` | Project deployment workflows | .mcp.json configurations |

## 🧠 **Business Analysis Commands / ビジネス分析コマンド**

### `/sc:business-panel`
**Purpose**: Multi-expert business analysis using 9 strategic frameworks
**Global Configuration**: `~/.claude/BUSINESS_*.md`

**Syntax**:
```bash
/sc:business-panel [@document] [query] [--options]
```

**Options**:
- `--experts "list"`: Select specific experts (porter,drucker,christensen,godin,kim_mauborgne,collins,taleb,meadows,doumont)
- `--mode [discussion|debate|socratic]`: Analysis interaction style
- `--focus [strategy|innovation|risk|communication]`: Domain focus
- `--synthesis-only`: Skip individual analysis, show only synthesis
- `--structured`: Executive summary format
- `--quick`: Time-constrained analysis (max 3 experts)

**Examples**:
```bash
# Comprehensive strategy analysis
/sc:business-panel @business_plan.pdf --mode discussion

# Innovation focus with specific experts
/sc:business-panel "AI product development" --experts "christensen,drucker,godin" --focus innovation

# Blue ocean strategy exploration
/sc:business-panel "new market entry" --experts "kim_mauborgne,porter" --synthesis-only
```

**Expert Profiles**:
- **Porter**: Competitive strategy, Five Forces analysis
- **Drucker**: Management fundamentals, systematic innovation
- **Christensen**: Disruptive innovation, jobs-to-be-done
- **Godin**: Remarkable marketing, tribe building
- **Kim/Mauborgne**: Blue Ocean Strategy, value innovation
- **Collins**: Good to Great principles, disciplined execution
- **Taleb**: Antifragility, risk management
- **Meadows**: Systems thinking, leverage points
- **Doumont**: Clear communication, cognitive load optimization

## 🔍 **Analysis Commands / 分析コマンド**

### `/analyze`
**Purpose**: Technical and strategic analysis with optional business panel integration
**Global Configuration**: `~/.claude/COMMANDS.md`

**Syntax**:
```bash
/analyze [@target] [--options]
```

**Options**:
- `--think`: Standard analysis depth
- `--think-hard`: Deep architectural analysis
- `--ultrathink`: Comprehensive system analysis
- `--business-panel`: Include business expert analysis
- `--focus [performance|security|architecture|scalability]`: Technical focus
- `--scope [file|module|project|system]`: Analysis boundary

**Examples**:
```bash
# Technical architecture analysis
/analyze @architecture.md --think-hard --focus architecture

# Security analysis with business implications
/analyze @security_assessment.pdf --business-panel --focus security

# Comprehensive system evaluation
/analyze @legacy_system/ --ultrathink --scope system
```

### `/research`
**Purpose**: Deep research with multi-hop analysis
**Global Configuration**: `~/.claude/RESEARCH_CONFIG.md`

**Syntax**:
```bash
/research [query] [--options]
```

**Options**:
- `--depth [quick|standard|deep|exhaustive]`: Research depth
- `--sources [n]`: Maximum sources to explore
- `--hops [n]`: Multi-hop exploration depth (1-5)
- `--confidence [threshold]`: Minimum confidence threshold (0.6-0.9)

**Examples**:
```bash
# Quick competitive research
/research "AI code generation market trends" --depth quick --sources 10

# Deep technical research
/research "microservices vs monolith 2025" --depth deep --hops 3

# Exhaustive industry analysis
/research "fintech regulatory landscape" --depth exhaustive --confidence 0.8
```

## ⚙️ **Development Commands / 開発コマンド**

### `/improve`
**Purpose**: Iterative enhancement with validation cycles
**Global Configuration**: `~/.claude/COMMANDS.md`

**Syntax**:
```bash
/improve [@target] [--options]
```

**Options**:
- `--iterations [n]`: Number of improvement cycles (1-10)
- `--business-panel`: Include business validation
- `--focus [quality|performance|usability|maintainability]`: Improvement target
- `--validate`: Include quality gates

**Examples**:
```bash
# Code quality improvement
/improve @src/components/ --iterations 3 --focus quality

# Business process enhancement
/improve @workflow.md --business-panel --focus usability

# Performance optimization
/improve @app.js --focus performance --validate
```

### `/delegate`
**Purpose**: Sub-agent task delegation with parallel execution
**Global Configuration**: `~/.claude/AGENTS.md`

**Syntax**:
```bash
/delegate [task] [--options]
```

**Options**:
- `--agents [list]`: Specific agent selection
- `--parallel`: Enable parallel agent execution
- `--coordination`: Enable cross-agent coordination
- `--scope [auto|files|folders]`: Delegation boundary

**Examples**:
```bash
# Parallel code review and testing
/delegate "review and test auth module" --agents "code-reviewer,app-quality-tester" --parallel

# Coordinated analysis
/delegate "comprehensive security audit" --coordination --scope files

# Auto-delegated refactoring
/delegate "modernize legacy codebase" --scope folders
```

## 🎨 **UI/Design Commands / UI/デザインコマンド**

### `/ui` or `/21`
**Purpose**: Modern UI component generation from 21st.dev patterns
**Project Configuration**: MCP Magic server in `.mcp.json`

**Syntax**:
```bash
/ui [component_description]
/21 [component_description]
```

**Examples**:
```bash
# Generate login form
/ui "create a responsive login form with validation"

# Generate data table
/21 "data table with sorting and pagination"

# Generate navigation
/ui "responsive navigation bar with dropdown menus"
```

### `/logo`
**Purpose**: Logo search and integration
**Project Configuration**: MCP Magic server in `.mcp.json`

**Syntax**:
```bash
/logo [company_name]
```

**Examples**:
```bash
# Single company logo
/logo "discord"

# Multiple logos
/logo "discord,github,slack"

# Specific brand
/logo "microsoft office"
```

## 💾 **Session Management Commands / セッション管理コマンド**

### `/sc:load`
**Purpose**: Restore project context and session state
**Global Configuration**: `~/.claude/AGENTS.md`

**Syntax**:
```bash
/sc:load [project_name] [--options]
```

**Options**:
- `--full`: Load complete project history
- `--recent`: Load last 7 days of context
- `--patterns`: Load learned patterns and preferences

**Examples**:
```bash
# Load current project context
/sc:load

# Load specific project with full history
/sc:load e-commerce-platform --full

# Load recent context only
/sc:load mobile-app --recent
```

### `/sc:save`
**Purpose**: Persist project state and learning patterns
**Global Configuration**: `~/.claude/AGENTS.md`

**Syntax**:
```bash
/sc:save [project_name] [--options]
```

**Options**:
- `--checkpoint`: Save intermediate state
- `--patterns`: Save learned patterns for reuse
- `--summary`: Include session summary

**Examples**:
```bash
# Save current session
/sc:save

# Create checkpoint during long session
/sc:save --checkpoint

# Save with pattern learning
/sc:save mobile-app-redesign --patterns --summary
```

## 🔄 **Workflow Commands / ワークフローコマンド**

### `/workflow`
**Purpose**: Execute predefined or custom workflows
**Global Configuration**: `~/.claude/COMMANDS.md`

**Syntax**:
```bash
/workflow [workflow_name] [--options]
```

**Predefined Workflows**:
- `startup-analysis`: Business model + technical architecture analysis
- `security-audit`: Comprehensive security assessment
- `performance-optimization`: End-to-end performance improvement
- `modernization`: Legacy system modernization planning
- `mvp-development`: Minimum viable product development cycle

**Examples**:
```bash
# Startup analysis workflow
/workflow startup-analysis @business_plan.pdf @architecture.md

# Custom security workflow
/workflow security-audit --scope system --business-panel

# Performance optimization cycle
/workflow performance-optimization --iterations 3 --validate
```

## 🛠️ **Project-Specific Commands / プロジェクト固有コマンド**

### Development Commands / 開発コマンド
| Command / コマンド | Purpose / 目的 | Configuration / 設定 |
|---------|---------|---------|
| `/test` | Run project test suites | CLAUDE.md project instructions |
| `/lint` | Code quality checking | DEVELOPMENT_RULES.md |
| `/build` | Project build process | .mcp.json + project scripts |
| `/deploy` | Deployment workflows | MCP servers + scripts |

### Git Commands / Gitコマンド
| Command / コマンド | Purpose / 目的 | Configuration / 設定 |
|---------|---------|---------|
| `/commit` | Intelligent git commit | .claude/settings.local.json |
| `/pr` | Create pull request | GitHub MCP server |
| `/branch` | Branch management | Git auto-approved commands |

## 🎯 **Behavioral Mode Flags / 行動モードフラグ**

### Mode Activation Flags / モード有効化フラグ
| Flag / フラグ | Purpose / 目的 | Global Config / グローバル設定 |
|---------|---------|---------|
| `--brainstorm` | Collaborative discovery mindset | ~/.claude/MODE_Brainstorming.md |
| `--introspect` | Meta-cognitive analysis | ~/.claude/MODE_Introspection.md |
| `--task-manage` | Hierarchical task organization | ~/.claude/MODE_Task_Management.md |
| `--orchestrate` | Intelligent tool selection | ~/.claude/MODE_Orchestration.md |
| `--token-efficient` | Symbol-enhanced communication | ~/.claude/MODE_Token_Efficiency.md |

### Analysis Depth Flags / 分析深度フラグ
| Flag / フラグ | Purpose / 目的 | Resource Usage / リソース使用量 |
|---------|---------|---------|
| `--think` | Standard analysis | ~4K tokens |
| `--think-hard` | Deep analysis | ~10K tokens |
| `--ultrathink` | Maximum depth analysis | ~32K tokens |

## 💡 **Command Chaining / コマンド連鎖**

### Sequential Workflows / 順次ワークフロー
```bash
# Research → Analysis → Design workflow
/research "cloud migration strategies" --depth standard
→ /analyze @research_results.md --business-panel --think-hard
→ /design migration-strategy --business-panel

# Load → Improve → Save cycle
/sc:load project-alpha --recent
→ /improve @codebase/ --iterations 3 --business-panel
→ /sc:save project-alpha --patterns
```

### Parallel Workflows / 並列ワークフロー
```bash
# Simultaneous analysis streams
/delegate "analyze frontend performance" --parallel
/delegate "analyze backend security" --parallel
/delegate "business requirements analysis" --parallel

# Coordinated development workflow
/delegate "design api-architecture" --coordination
/delegate "research frontend-frameworks" --coordination
/delegate "analyze database-requirements" --coordination
```

## 🔧 **Configuration Management / 設定管理**

### Global Configuration Files / グローバル設定ファイル
```
~/.claude/
├── CLAUDE.md                   # SuperClaude entry point
├── AGENTS.md                   # Advanced agents configuration
├── COMMANDS.md                 # Advanced slash commands
├── MODES.md                    # Behavioral modes
├── RESEARCH_CONFIG.md          # Deep research settings
├── BUSINESS_PANEL_EXAMPLES.md  # Business analysis examples
├── BUSINESS_SYMBOLS.md         # Business symbol system
├── FLAGS.md                    # Behavioral flags
├── PRINCIPLES.md               # Core principles
└── BUSINESS_*.md               # Business framework definitions
```

### Project Configuration Files / プロジェクト設定ファイル
```
.claude/
├── settings.local.json         # Claude Code permissions & MCP enablement
└── agents/                     # Local agent definitions (if any)

.mcp.json                       # MCP server definitions (21 servers)
CLAUDE.md                       # Claude Code project instructions
DEVELOPMENT_RULES.md            # Project-specific development rules
```

## 📊 **Performance Optimization / パフォーマンス最適化**

### Token Efficiency / トークン効率
- Commands use compressed communication when possible
- Symbol system reduces token usage by 30-50%
- Smart caching prevents redundant operations
- Progressive enhancement: start simple, scale up as needed

### Execution Efficiency / 実行効率
- Parallel command execution by default
- Intelligent agent delegation for complex tasks
- MCP server coordination for specialized operations
- Resource-aware scaling based on system constraints

### Quality Assurance / 品質保証
- Built-in validation gates for all commands
- Confidence scoring for research and analysis
- Pattern learning for continuous improvement
- Error recovery and graceful degradation

---

**🎯 Usage Philosophy / 使用哲学**: Commands are designed to be chainable, composable, and adaptive to context. Use the most specific command for your task, and leverage behavioral flags for optimal results.

**コマンドは連鎖可能、構成可能、コンテキスト適応的に設計されています。タスクに最適な特定コマンドを使用し、最適な結果のために行動フラグを活用してください。**