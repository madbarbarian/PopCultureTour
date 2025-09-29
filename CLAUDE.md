# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Architecture

This repository serves as a development base configuration for Claude Code with comprehensive MCP (Model Context Protocol) server integrations. The project is designed to provide AI-powered development capabilities through 16 different MCP servers spanning various domains including databases, office applications, design tools, multimedia processing, and real-time search.

### Core Configuration Structure

The project uses a dual-configuration approach:
- **`.mcp.json`**: Defines the available MCP servers and their startup commands
- **`.claude/settings.local.json`**: Controls Claude Code permissions and enables specific MCP servers

### MCP Server Categories

1. **Data & Backend**: Supabase (PostgreSQL), Codex (advanced code generation)
2. **Office & Productivity**: PowerPoint, Excel, Microsoft 365
3. **Design & Media**: Figma, Chrome DevTools, FFmpeg, YouTube, Veo 3 (AI video)
4. **Development**: GitHub, Context7 (documentation), Filesystem
5. **Communication**: Slack, Perplexity (real-time search)
6. **AI Presentation**: MulmoCast Vision (slide generation)

## Key Development Commands

### MCP Server Management
```bash
# No build/test commands - this is a configuration-only project
# Restart Claude Code to apply MCP changes
```

### Git Operations (Auto-approved in Claude Code)
```bash
git status
git add .
git commit -m "message"
git push
```

### NPM Operations (Auto-approved)
```bash
npm install package-name
npm uninstall package-name
npm cache clean --force
```

## Configuration Management

### Adding New MCP Servers

1. **Add server definition to `.mcp.json`**:
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

2. **Enable in Claude settings**:
Add server name to `enabledMcpjsonServers` array in `.claude/settings.local.json`

3. **Restart Claude Code** to activate changes

### Environment Variables for MCP Servers

Some servers require API keys:
```bash
export PERPLEXITY_API_KEY="your-api-key"
export GOOGLE_API_KEY="your-google-api-key"
export SLACK_BOT_TOKEN="your-slack-token"
export GITHUB_TOKEN="your-github-token"
```

## Development Rules and Constraints

### Cursor IDE Integration
The project includes comprehensive development rules in `.cursor/rules/`:

- **globals.mdc**: Strict development process requiring analysis, planning, and quality control
- **techstack.mdc**: Technology stack definitions (Next.js, React, TypeScript, Clerk, Prisma)
- **nextjs.mdc**: Next.js best practices and Server Components usage
- **uiux.mdc**: UI/UX design constraints using Shadcn/ui
- **db-blueprint.mdc**: Database design patterns
- **clerk.mdc**: Authentication implementation rules
- **todo.mdc**: Task management methodology

### Critical Constraints
1. **No unauthorized UI/UX changes** - Existing designs must not be modified without explicit approval
2. **Technology stack versions are locked** - Cannot change specified framework/library versions
3. **Strict adherence to established patterns** - Must follow existing directory structure and naming conventions
4. **DRY principle enforcement** - Always check for existing implementations before creating new ones

## Architecture Insights

### MCP Ecosystem Design
The configuration creates a comprehensive AI development environment where:
- **Data flows** between multiple specialized AI tools
- **Cross-server functionality** enables complex workflows (e.g., YouTube → Veo 3 for video analysis and generation)
- **Modular activation** allows selective enabling of servers based on needs

### Security Model
- **Principle of least privilege**: Only essential bash commands are auto-approved
- **API key isolation**: Sensitive credentials managed through environment variables
- **Sandbox constraints**: Filesystem access limited to specific directories (Desktop, Downloads)

### Documentation Strategy
The project maintains three levels of documentation:
1. **PROJECT_STRUCTURE.md**: Comprehensive project overview
2. **MCP_README.md**: Detailed MCP server configuration and usage
3. **GEMINI.md**: AI assistant context (legacy, being superseded by this CLAUDE.md)

## Working with this Repository

### Typical Development Flow
1. Modify MCP server configurations in `.mcp.json`
2. Update enabled servers in `.claude/settings.local.json`
3. Document changes in `MCP_README.md`
4. Commit and push changes using auto-approved git commands

### Quality Assurance
- All changes must be documented
- Configuration changes require Claude Code restart to take effect
- API integrations must include proper error handling and environment variable management