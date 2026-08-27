# lognest

A tiny CLI to clean, rotate and archive old log files

## Usage

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## What it does

- Exit codes friendly for cron and CI
- Dry-run mode shows what would happen, touches nothing
- Scan directories for log files by glob pattern
- Filter by age (--older-than) or size (--larger-than)
- Archive matched logs into a timestamped .tar.gz

## Install

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   ├── dependabot.yml
│   └── pull_request_template.md
├── docs/
│   ├── development.md
│   ├── roadmap.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── utils.py
├── tests/
│   ├── test_cli.py
│   └── test_smoke.py
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── LICENSE
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

MIT. Do whatever you want.
