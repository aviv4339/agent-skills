# Agent Skills

Production-grade AI agent skills for OpenClaw and Claude Code marketplaces.

## Skills

### 🛡️ indirect-prompt-injection

Detect and reject indirect prompt injection attacks from external content.

**Use when reading:** Social media posts, shared documents, emails, web pages, user-uploaded files — any untrusted external content.

**Features:**
- 20+ detection patterns covering instruction override, persona hijacking, data exfiltration, encoding exploits, and social engineering
- Zero-width character and homoglyph (mixed script) detection
- HTML comment and hidden content stripping
- Risk scoring with configurable thresholds
- 96% detection accuracy with 100% benign pass rate (zero false positives)

**Quick Start:**
```bash
# Test the detector
python skills/indirect-prompt-injection/scripts/sanitize.py --analyze "Ignore previous instructions..."

# Run the test suite
python skills/indirect-prompt-injection/scripts/run_tests.py
```

**Installation (OpenClaw):**
```bash
# Clone the repo
git clone https://github.com/aviv4339/agent-skills.git

# Add to your skills directory
cp -r agent-skills/skills/indirect-prompt-injection ~/.openclaw/skills/
```

**Installation (ClawdHub):**
```bash
clawdhub install indirect-prompt-injection
```

## Structure

```
skills/
└── indirect-prompt-injection/
    ├── SKILL.md                    # Core workflow + quick checklist
    ├── references/
    │   ├── attack-patterns.md      # Taxonomy of known attacks
    │   ├── detection-heuristics.md # Detection rules + scoring
    │   └── safe-parsing.md         # Sanitization techniques
    ├── scripts/
    │   ├── sanitize.py             # CLI detection tool
    │   └── run_tests.py            # Test runner
    └── tests/
        └── test_cases.json         # 25+ test cases
```

## Contributing

1. Fork the repo
2. Add test cases to `tests/test_cases.json`
3. Run `python scripts/run_tests.py` to validate
4. Submit a PR

## License

MIT
