[![npm version](https://img.shields.io/npm/v/claude-code-templates.svg)](https://www.npmjs.com/package/claude-code-templates)
[![npm downloads](https://img.shields.io/npm/dt/claude-code-templates.svg)](https://www.npmjs.com/package/claude-code-templates)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Sponsored by Z.AI](https://img.shields.io/badge/Sponsored%20by-Z.AI-2563eb?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTEyIDJMMiAyMkgyMkwxMiAyWiIgZmlsbD0id2hpdGUiLz4KPC9zdmc+)](https://z.ai/subscribe?ic=8JVLJQFSKB&utm_source=github&utm_medium=badge&utm_campaign=readme)
[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-support-yellow?style=flat&logo=buy-me-a-coffee)](https://buymeacoffee.com/daniavila)
[![GitHub stars](https://img.shields.io/github/stars/davila7/claude-code-templates.svg?style=social&label=Star)](https://github.com/davila7/claude-code-templates)

<p align="center">
  <a href="https://trendshift.io/repositories/15113" target="_blank">
    <img src="https://trendshift.io/api/badge/repositories/15113" alt="davila7%2Fclaude-code-templates | Trendshift" style="width: 200px; height: 40px;" width="125" height="40"/>
  </a>
  <br />
  <br />
  <a href="https://vercel.com/oss">
  <img alt="Vercel OSS Program" src="https://vercel.com/oss/program-badge.svg" />
  </a>
</p>

---

<div align="center">
  <h3>🤝 Partnership</h3>
  <p>
    <strong>This project is sponsored by <a href="https://z.ai" target="_blank">Z.AI</a></strong><br/>
    Supporting Claude Code Templates with the <strong>GLM CODING PLAN</strong>
  </p>
  <p>
    <a href="https://z.ai/subscribe?ic=8JVLJQFSKB&utm_source=github&utm_medium=readme&utm_campaign=partnership" target="_blank">
      <img src="https://img.shields.io/badge/Get%2010%25%20OFF-GLM%20Coding%20Plan-2563eb?style=for-the-badge" alt="GLM Coding Plan" />
    </a>
  </p>
  <p>
    <em>Top-tier coding performance powered by GLM-4.6 • Starting at $3/month</em><br/>
    <em>Seamlessly integrates with Claude Code, Cursor, Cline & 10+ AI coding tools</em>
  </p>
  <p>
    <code>npx claude-code-templates@latest --setting partnerships/glm-coding-plan --yes</code>
  </p>
</div>

---

# Claude Code Templates ([aitmpl.com](https://aitmpl.com))

**Ready-to-use configurations for Anthropic's Claude Code.** A comprehensive collection of AI agents, custom commands, settings, hooks, external integrations (MCPs), and project templates to enhance your development workflow.

## Browse & Install Components and Templates

**[Browse All Templates](https://aitmpl.com)** - Interactive web interface to explore and install 100+ agents, commands, settings, hooks, and MCPs.

<img width="1049" height="855" alt="Screenshot 2025-08-19 at 08 09 24" src="https://github.com/user-attachments/assets/e3617410-9b1c-4731-87b7-a3858800b737" />

## 🚀 Quick Installation

```bash
# Install a complete development stack
npx claude-code-templates@latest --agent development-team/frontend-developer --command testing/generate-tests --mcp development/github-integration --yes

# Browse and install interactively
npx claude-code-templates@latest

# Install specific components
npx claude-code-templates@latest --agent development-tools/code-reviewer --yes
npx claude-code-templates@latest --command performance/optimize-bundle --yes
npx claude-code-templates@latest --setting performance/mcp-timeouts --yes
npx claude-code-templates@latest --hook git/pre-commit-validation --yes
npx claude-code-templates@latest --mcp database/postgresql-integration --yes
```

## What You Get

| Component | Description | Examples |
|-----------|-------------|----------|
| **🤖 Agents** | AI specialists for specific domains | Security auditor, React performance optimizer, database architect |
| **⚡ Commands** | Custom slash commands | `/generate-tests`, `/optimize-bundle`, `/check-security` |
| **🔌 MCPs** | External service integrations | GitHub, PostgreSQL, Stripe, AWS, OpenAI |
| **⚙️ Settings** | Claude Code configurations | Timeouts, memory settings, output styles |
| **🪝 Hooks** | Automation triggers | Pre-commit validation, post-completion actions |
| **🎨 Skills** | Reusable capabilities with progressive disclosure | PDF processing, Excel automation, custom workflows |

## 🎯 安装范围控制

### 1. 通过目标目录控制

使用 `--directory` 选项控制组件的安装位置：

```bash
# 安装到当前项目目录（默认）
npx claude-code-templates@latest --agent development-tools/code-reviewer --yes

# 安装到指定项目目录
npx claude-code-templates@latest --agent development-tools/code-reviewer --directory /path/to/project --yes

# 安装到用户主目录（全局/用户级别）
npx claude-code-templates@latest --agent development-tools/code-reviewer --directory ~/ --yes
```

### 2. 组件类型对应的安装路径

| 组件类型 | 安装路径 | 说明 |
|---------|---------|------|
| **Agents** | `{targetDir}/.claude-internal/agents/` | 始终安装到目标目录 |
| **Commands** | `{targetDir}/.claude-internal/commands/` | 始终安装到目标目录 |
| **Skills** | `{targetDir}/.claude-internal/skills/` | 始终安装到目标目录 |
| **Settings** | 见下方范围选项 | 可选择不同安装范围 |
| **Hooks** | 见下方范围选项 | 可选择不同安装范围 |

### 3. Settings 和 Hooks 的安装范围

对于 **Settings** 和 **Hooks** 组件，可以选择 4 种安装范围：

| 范围 | 安装位置 | 说明 |
|------|---------|------|
| `user` | `~/.claude/settings.json` | **全局级别** - 适用于所有项目 |
| `project` | `{project}/.claude/settings.json` | **项目级别** - 团队共享 |
| `local` | `{project}/.claude/settings.local.json` | **本地级别** - 个人配置，不提交到版本控制（使用 `--yes` 时的默认值） |
| `enterprise` | 系统路径 | **企业级** - 系统级策略（需要管理员权限） |

### 4. 交互模式 vs 静默模式

**交互模式**（不带 `--yes`）：
- 对于 settings 和 hooks，会提示您选择安装位置
- 可以同时选择多个位置

**静默模式**（带 `--yes`）：
- Settings 和 hooks 默认使用 `local` 范围
- 无提示，使用默认值

### 5. 使用示例

```bash
# 项目级别安装（settings 安装到 .claude/settings.local.json）
cd /my/project
npx claude-code-templates@latest --setting performance/mcp-timeouts --yes

# 全局/用户级别安装（安装到用户主目录）
npx claude-code-templates@latest --setting performance/mcp-timeouts --directory ~/ --yes

# 交互模式 - 会询问安装位置（可选择 user/project/local/enterprise）
npx claude-code-templates@latest --setting performance/mcp-timeouts

# 在指定目录的本地范围安装
npx claude-code-templates@latest --hook git/pre-commit-validation --directory /workspace/my-project --yes
```

> **注意**：目前没有直接的 `--global` 或 `--local` 标志。安装范围由以下因素控制：
> 1. 工作目录（通过 `--directory` 选项）
> 2. 交互式提示（对于 settings/hooks）或 `--yes` 的默认值
> 3. 目标目录决定了安装是项目本地还是全局

## 🛠️ Additional Tools

Beyond the template catalog, Claude Code Templates includes powerful development tools:

### 📊 Claude Code Analytics
Monitor your AI-powered development sessions in real-time with live state detection and performance metrics.

```bash
npx claude-code-templates@latest --analytics
```

### 💬 Conversation Monitor  
Mobile-optimized interface to view Claude responses in real-time with secure remote access.

```bash
# Local access
npx claude-code-templates@latest --chats

# Secure remote access via Cloudflare Tunnel
npx claude-code-templates@latest --chats --tunnel
```

### 🔍 Health Check
Comprehensive diagnostics to ensure your Claude Code installation is optimized.

```bash
npx claude-code-templates@latest --health-check
```

### 🔌 Plugin Dashboard
View marketplaces, installed plugins, and manage permissions from a unified interface.

```bash
npx claude-code-templates@latest --plugins
```

## 📖 Documentation

**[📚 docs.aitmpl.com](https://docs.aitmpl.com/)** - Complete guides, examples, and API reference for all components and tools.

## Contributing

We welcome contributions! **[Browse existing templates](https://aitmpl.com)** to see what's available, then check our [contributing guidelines](CONTRIBUTING.md) to add your own agents, commands, MCPs, settings, or hooks.

**Please read our [Code of Conduct](CODE_OF_CONDUCT.md) before contributing.**

## Attribution

This collection includes components from multiple sources:

**Scientific Skills:**
- **[K-Dense-AI/claude-scientific-skills](https://github.com/K-Dense-AI/claude-scientific-skills)** by K-Dense Inc. - MIT License (139 scientific skills for biology, chemistry, medicine, and computational research)

**Official Anthropic:**
- **[anthropics/skills](https://github.com/anthropics/skills)** - Official Anthropic skills (21 skills)
- **[anthropics/claude-code](https://github.com/anthropics/claude-code)** - Development guides and examples (10 skills)

**Community Skills & Agents:**
- **[obra/superpowers](https://github.com/obra/superpowers)** by Jesse Obra - MIT License (14 workflow skills)
- **[alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)** by Alireza Rezvani - MIT License (36 professional role skills)
- **[wshobson/agents](https://github.com/wshobson/agents)** by wshobson - MIT License (48 agents)
- **NerdyChefsAI Skills** - Community contribution - MIT License (specialized enterprise skills)

**Commands & Tools:**
- **[awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)** by hesreallyhim - CC0 1.0 Universal (21 commands)
- **[awesome-claude-skills](https://github.com/mehdi-lamrani/awesome-claude-skills)** - Apache 2.0 (community skills)
- **move-code-quality-skill** - MIT License
- **cocoindex-claude** - Apache 2.0

Each of these resources retains its **original license and attribution**, as defined by their respective authors.
We respect and credit all original creators for their work and contributions to the Claude ecosystem.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- **🌐 Browse Templates**: [aitmpl.com](https://aitmpl.com)
- **📚 Documentation**: [docs.aitmpl.com](https://docs.aitmpl.com)
- **💬 Community**: [GitHub Discussions](https://github.com/davila7/claude-code-templates/discussions)
- **🐛 Issues**: [GitHub Issues](https://github.com/davila7/claude-code-templates/issues)

## Stargazers over time
[![Stargazers over time](https://starchart.cc/davila7/claude-code-templates.svg?variant=adaptive)](https://starchart.cc/davila7/claude-code-templates)

---

**⭐ Found this useful? Give us a star to support the project!**

[![Buy Me A Coffee](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&slug=daniavila&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://buymeacoffee.com/daniavila)