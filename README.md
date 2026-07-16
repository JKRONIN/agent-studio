# Agent Studio

A framework for multi-agent AI orchestration. One Director plans and delegates. Specialized workers execute. Ship faster with a team of AI agents.

## Architecture

```
┌─────────────────────────────────────┐
│            Director Agent           │
│      (Plans, Delegates, Reviews)    │
├──────────┬──────────┬───────────────┤
│ Builder  │ Reviewer │ Deployer ...  │
│ (Code)   │ (QA)     │ (Infra)      │
└──────────┴──────────┴───────────────┘
```

## Quick Start

```bash
git clone https://github.com/JKRONIN/agent-template.git
cd agent-template
npm install
cp config.example.yaml config.yaml
# Edit config.yaml with your API keys
node src/index.js "Build a REST API"
```

## How It Works

1. **Intake** — Understand the request
2. **Plan** — Break into tasks
3. **Delegate** — Assign to best-fit worker
4. **Review** — Verify quality
5. **Deliver** — Ship and report

## Workers

| Worker | Role |
|--------|------|
| Director | Plans, delegates, reviews, reports |
| Builder | Writes code, builds features |
| Reviewer | Checks security, performance, style |
| Deployer | Server ops, CI/CD, infrastructure |
| Researcher | Gathers info, writes docs |
| Custom | Add your own workers |

## Adding Workers

```javascript
class MyWorker extends BaseWorker {
  async execute(task) {
    // Your logic here
    return { content: 'Result' };
  }
}

director.registerWorker('my-worker', new MyWorker());
```

## Adding Skills

Create `skills/my-skill.md`:

```markdown
# Skill: My Skill

## Trigger
When X happens

## Steps
1. Do this
2. Do that

## Output
Structured result
```

## Links

- [Agent Template](https://github.com/JKRONIN/agent-template) — Get started
- [Live Site](https://jkronin.github.io/agent-studio/) — See it in action

## License

MIT
