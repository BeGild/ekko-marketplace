# Ekko Marketplace

Claude Code plugins curated by BeGild for workflow automation and development tools.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add BeGild/ekko-marketplace
```

## Available Plugins

### tmux-worktree

**Description:** Creates isolated git worktree development environments with tmux sessions. Automatically manages branch naming, creates dedicated tmux windows with AI tool integration.

**Categories:** Development, Git, Workflow, AI

**Features:**
- Smart branch naming (auto-increments if exists)
- Isolated git worktrees for parallel work
- Tmux integration for organized sessions
- Configurable AI tools (claude, cursor, aider, etc.)
- Result capture via RESULT.md files
- Interactive cleanup

**Install:**
```bash
/plugin install tmux-worktree@ekko-marketplace
```

**Usage:**

When working with an AI agent that supports Agent Skills, the skill is invoked automatically based on task context:

```
User: I need to add OAuth2 login to the app

Agent: [Uses tmux-worktree skill]
       → Creates worktree at .worktrees/add-oauth2-login
       → Creates branch feature/add-oauth2-login
       → Opens tmux window with Claude ready
```

**Requirements:**
- Git
- Tmux
- An AI tool (claude, cursor, aider, etc.)
- Claude Code with plugin support

**Repository:** https://github.com/BeGild/tmux-worktree

---

## Configuration

After installing tmux-worktree, configure your AI tool:

```bash
# Query configuration
./skills/tmux-worktree/bin/tmux-worktree query-config

# Edit config file
~/.config/tmux-worktree/config.yaml
```

Example configuration:
```yaml
ai_command: "claude {prompt}"  # or cursor, aider, etc.
worktree_dir: ".worktrees"

result_prompt_suffix: |
  Please save your final results to a file named RESULT.md in the current directory.
  Include a summary of changes, files modified, testing notes, and any next steps.
```

## Support

- **Issues:** https://github.com/BeGild/ekko-marketplace/issues
- **Plugin Repository:** https://github.com/BeGild/tmux-worktree

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses
