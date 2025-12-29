# 目录迁移总结

## 修改概述
将所有 Dashboard 相关命令的配置目录从 `.claude` 迁移到 `.claude-internal`

## 修改的文件列表

### 核心 Dashboard 文件
1. ✅ `cli-tool/src/analytics.js` - Analytics Dashboard (端口 3333)
2. ✅ `cli-tool/src/chats-mobile.js` - Mobile Chats Interface (端口 9876)
3. ✅ `cli-tool/src/plugin-dashboard.js` - Plugin Dashboard (端口 3336)
4. ✅ `cli-tool/src/skill-dashboard.js` - Skill Dashboard (端口 3337)
5. ✅ `cli-tool/src/index.js` - 主入口文件

### 辅助模块文件
6. ✅ `cli-tool/src/sandbox-server.js`
7. ✅ `cli-tool/src/agents.js`
8. ✅ `cli-tool/src/command-scanner.js`
9. ✅ `cli-tool/src/health-check.js`
10. ✅ `cli-tool/src/hook-stats.js`
11. ✅ `cli-tool/src/file-operations.js`
12. ✅ `cli-tool/src/command-stats.js`
13. ✅ `cli-tool/src/hook-scanner.js`
14. ✅ `cli-tool/src/session-sharing.js`
15. ✅ `cli-tool/src/templates.js`
16. ✅ `cli-tool/src/claude-api-proxy.js`

## 修改详情

### 目录路径映射

| 旧路径 | 新路径 |
|--------|--------|
| `~/.claude/` | `~/.claude-internal/` |
| `./.claude/` | `./.claude-internal/` |
| `~/.claude/projects/` | `~/.claude-internal/projects/` |
| `~/.claude/statsig/` | `~/.claude-internal/statsig/` |
| `~/.claude/agents/` | `~/.claude-internal/agents/` |
| `~/.claude/plugins/` | `~/.claude-internal/plugins/` |
| `~/.claude/skills/` | `~/.claude-internal/skills/` |
| `~/.claude/commands/` | `~/.claude-internal/commands/` |
| `~/.claude/settings.json` | `~/.claude-internal/settings.json` |

### Dashboard 监控目录更新

#### Analytics Dashboard (端口 3333)
- ✅ `~/.claude-internal/` - 主目录
- ✅ `~/.claude-internal/projects/` - 项目对话
- ✅ `~/.claude-internal/statsig/` - 会话信息
- ✅ `~/.claude-internal/agents/` - 用户级 Agents

#### Chats Mobile (端口 9876)
- ✅ `~/.claude-internal/` - 主目录
- ✅ `~/.claude-internal/projects/` - 项目对话

#### Plugin Dashboard (端口 3336)
- ✅ `~/.claude-internal/plugins/marketplaces/` - 插件市场
- ✅ `~/.claude-internal/settings.json` - 插件配置

#### Skill Dashboard (端口 3337)
- ✅ `~/.claude-internal/skills/` - 个人技能
- ✅ `./.claude-internal/skills/` - 项目技能
- ✅ `~/.claude-internal/plugins/marketplaces/*/plugins/*/skills/` - 插件技能

## 验证状态

### 语法检查
- ✅ analytics.js - 通过
- ✅ chats-mobile.js - 通过
- ✅ plugin-dashboard.js - 通过
- ✅ skill-dashboard.js - 通过
- ✅ index.js - 通过

### 替换完成度
- ✅ 单引号路径 `'.claude'` → `'.claude-internal'` - 全部替换完成
- ✅ 双引号路径 `".claude"` → 未发现需要替换的实例
- ✅ 模板字符串 - 未发现硬编码路径

## 使用命令（无需更改）

所有 Dashboard 命令保持不变，只是底层监控的目录变更：

```bash
# Analytics Dashboard
cct --analytics

# Chats Mobile Interface
cct --chats

# Plugin Dashboard
cct --plugins

# Skill Dashboard
cct --skills-manager

# Agents Dashboard
cct --agents
```

## 注意事项

1. **确保目录存在**: 使用前需要确保 `~/.claude-internal/` 目录存在
2. **数据迁移**: 如果之前使用 `.claude` 目录，可能需要手动迁移数据到 `.claude-internal`
3. **权限检查**: 确保新目录有正确的读写权限
4. **路径一致性**: 所有 Dashboard 现在统一使用 `.claude-internal` 目录

## 测试建议

1. 创建测试目录：
   ```bash
   mkdir -p ~/.claude-internal/projects
   mkdir -p ~/.claude-internal/plugins
   mkdir -p ~/.claude-internal/skills
   mkdir -p ~/.claude-internal/agents
   ```

2. 测试每个 Dashboard：
   ```bash
   cct --analytics
   cct --chats
   cct --plugins
   cct --skills-manager
   ```

3. 检查错误日志，确保没有路径相关错误

## 完成时间
$(date)

## 修改作者
Claude Code Assistant
完成时间: 2025-12-29 22:32:25
