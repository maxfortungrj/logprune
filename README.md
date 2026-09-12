# logprune

A tiny CLI to clean, rotate and archive old log files

## Getting started

```bash
pip install -r requirements.txt
python -m logwash --help
```

## What it does

- Filter by age (--older-than) or size (--larger-than)
- Scan directories for log files by glob pattern
- Dry-run mode shows what would happen, touches nothing
- Archive matched logs into a timestamped .tar.gz
- Exit codes friendly for cron and CI

## How to use

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Project structure

```text
├── .github/
│   └── dependabot.yml
├── docs/
│   ├── development.md
│   ├── faq.md
│   └── roadmap.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── errors.py
├── tests/
│   └── test_cli.py
├── .gitignore
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── Makefile
├── SECURITY.md
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT - see [LICENSE](LICENSE).
