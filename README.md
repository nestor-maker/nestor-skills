# Claude Code Skills Collection

A curated set of Claude Code skills for building agentic applications, MCP servers, and production web apps.

## What's Included

| Skill | What it does |
|-------|-------------|
| **agent-designer** | Design multi-agent system architectures |
| **agent-workflow-designer** | Design and map agent workflows |
| **mcp-builder** | Build MCP servers (Python FastMCP or Node/TypeScript) |
| **mcp-server-builder** | Detailed MCP server construction guide |
| **prompt-master** | Generate optimized prompts for any AI tool |
| **rag-architect** | Design and build production RAG pipelines |
| **skill-creator** | Create, improve, and evaluate Claude Code skills |
| **frontend-design** | Build distinctive, production-grade web interfaces |
| **webapp-testing** | Test web applications using Playwright |
| **doc-coauthoring** | Structured documentation co-authoring workflow |
| **gemini-review** | Cross-LLM code review using Gemini |
| **self-improving-agent** | Curate agent memory into durable project knowledge |
| **internal-comms** | Templates for internal communications |

## Installation

### Option 1: Copy individual skills (recommended)

Copy the skills you want into your project's `.claude/skills/` directory:

```bash
# From inside your project root
mkdir -p .claude/skills

# Copy a specific skill
cp -r path/to/nestor-skills/skills/agent-designer .claude/skills/

# Or copy all skills at once
cp -r path/to/nestor-skills/skills/* .claude/skills/
```

### Option 2: Clone and symlink

```bash
# Clone the repo somewhere on your machine
git clone https://github.com/nestor-maker/nestor-skills.git ~/nestor-skills

# Symlink individual skills into your project
ln -s ~/nestor-skills/skills/agent-designer .claude/skills/agent-designer
ln -s ~/nestor-skills/skills/mcp-builder .claude/skills/mcp-builder
# ... repeat for each skill you want
```

### Option 3: Clone directly into .claude/skills

```bash
# From your project root
git clone https://github.com/nestor-maker/nestor-skills.git /tmp/nestor-skills
cp -r /tmp/nestor-skills/skills/* .claude/skills/
```

## Verify Installation

After copying, start a new Claude Code session. Skills are auto-discovered from `.claude/skills/`. You can verify by asking Claude:

> "What skills do you have available?"

Or invoke a skill directly:

> "/prompt-master write a prompt for generating API documentation"

## Recommended Companion: Superpowers Plugin

These skills work best alongside the **superpowers** plugin, which adds process skills like brainstorming, planning, TDD, and debugging. Install it via:

```
/install-plugin superpowers
```

Key superpowers skills:
- **brainstorming** - structured ideation before building
- **writing-plans** - plan multi-step implementations
- **executing-plans** - execute plans with review checkpoints
- **test-driven-development** - TDD workflow
- **systematic-debugging** - debug methodically
- **verification-before-completion** - verify before claiming done

## Skill Structure

Each skill is a directory containing a `SKILL.md` file:

```
.claude/skills/
  agent-designer/
    SKILL.md        # Skill definition (name, description, instructions)
  mcp-builder/
    SKILL.md
  ...
```

The `SKILL.md` file contains frontmatter (name, description, triggers) and the full skill instructions that Claude follows when the skill is invoked.

## Tips for Getting the Most Out of These

1. **Start with prompt-master** - refine your prompts before sending to Claude
2. **Use gemini-review** - have a second LLM review Claude's code (prevents blind spots)
3. **Build modularly** - use mcp-builder to create separate MCP servers for each integration
4. **Plan before building** - use brainstorming + writing-plans before touching code
5. **Always verify** - use verification-before-completion before committing
