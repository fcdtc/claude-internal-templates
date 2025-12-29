# Package Rename Summary

## Changes Made

### Package Information
- **Old Name**: `claude-code-templates`
- **New Name**: `claude-internal-templates`
- **Old Binary**: `cct` (claude-code-templates)
- **New Binary**: `cit` (claude-internal-templates)

### Updated Files
1. ✅ `package.json`
   - Changed package name
   - Updated description
   - Changed bin command names
   - Updated keywords and author

### Command Changes

| Old Command | New Command |
|-------------|-------------|
| `npx claude-code-templates@latest` | `npx claude-internal-templates@latest` |
| `cct --analytics` | `cit --analytics` |
| `cct --chats` | `cit --chats` |
| `cct --plugins` | `cit --plugins` |
| `cct --skills-manager` | `cit --skills-manager` |
| `cct --agents` | `cit --agents` |

### Local Development

After rename, use:
```bash
npm link
cit --analytics
cit --chats
```

### Publishing to npm

```bash
# First time publishing under new name
npm version patch
npm publish

# Users install with
npm install -g claude-internal-templates

# Or use directly
npx claude-internal-templates@latest --analytics
```

### Migration Notes

This package is now specifically for **Claude Internal** (the CLI tool), not the general Claude Code.

The directory structure also changed:
- Old: `~/.claude/`
- New: `~/.claude-internal/`

