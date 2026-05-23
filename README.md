# Skills

A fork of [huggingface/skills](https://huggingface.co/skills) — a collection of AI skills and agents that can be used with Claude, Cursor, and other AI-powered development tools.

## Overview

This repository contains:
- **Skills**: Reusable AI capabilities that can be composed into agents
- **Agents**: Pre-built workflows combining multiple skills
- **Marketplace listings**: Metadata for publishing skills to Claude and Cursor plugin marketplaces
- **Evals**: Evaluation benchmarks for measuring skill performance

## Structure

```
├── .claude-plugin/          # Claude plugin configuration
│   ├── plugin.json          # Plugin metadata
│   └── marketplace.json     # Marketplace listing
├── .cursor-plugin/          # Cursor plugin configuration
│   ├── plugin.json          # Plugin metadata
│   └── marketplace.json     # Marketplace listing
├── .github/
│   └── workflows/           # CI/CD automation
│       ├── generate-agents.yml
│       ├── push-evals-leaderboard.yml
│       └── push-hackers-leaderboard.yml
├── skills/                  # Individual skill implementations
├── agents/                  # Composed agent definitions
└── evals/                   # Evaluation datasets and scripts
```

## Getting Started

### Prerequisites

- Python 3.10+
- [uv](https://github.com/astral-sh/uv) or pip
- Hugging Face account (for publishing)

### Installation

```bash
git clone https://github.com/your-org/skills
cd skills
pip install -e .
```

### Running Evals

```bash
python -m evals.run --skill <skill-name> --dataset <dataset-id>
```

### Generating Agents

Agents are automatically generated via the `generate-agents` GitHub Actions workflow, or you can run locally:

```bash
python scripts/generate_agents.py
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/my-new-skill`)
3. Add your skill under `skills/`
4. Add corresponding evals under `evals/`
5. Submit a pull request

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting.

## Security

See [.github/workflows/SECURITY.md](.github/workflows/SECURITY.md) for our security policy.

## License

Apache 2.0 — see [LICENSE](LICENSE) for details.
