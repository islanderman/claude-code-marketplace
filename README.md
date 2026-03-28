# Jerry's Personal Marketplace

Curated marketplace of Claude Code plugins for specialized domains.

## Installation

Add the marketplace, then install individual plugins:

```bash
/plugin marketplace add https://github.com/islanderman/claude-code-marketplace
/plugin install finance-pack
```

## Available Plugins

### finance-pack

Institutional-grade quantitative finance toolkit with 15 firm-based agents, 11 analytical skills, and a portfolio analysis command.

**Agents (15):** Goldman Sachs, Renaissance Technologies, Two Sigma, Citadel, Jane Street, AQR, D.E. Shaw, Bridgewater, Bloomberg, Virtu, Point72, Man Group, Millennium, Dimensional Fund Advisors methodologies.

**Skills (11):** Adversarial business model analysis, bull/bear steelman, catalyst timelines, competitive moat audits, earnings call translation, SEC filing decoding, investment thesis construction, portfolio overlap detection, sector theme mapping, valuation sanity checks, and full portfolio deep analysis.

**Commands:** `/portfolio-analysis` — runs all 15 agents in parallel on your portfolio.

See [plugins/finance-pack/README.md](plugins/finance-pack/README.md) for detailed usage.

### middle-schooler

Education and tutoring toolkit for middle school academic competitions — Spelling Bee and National Science Bowl (NSB).

**Agents (2):** Spelling bee instructor (NLP-powered word analysis, etymology teaching, adaptive practice) and Science Bowl instructor (curriculum synthesis across 6 subjects using TF-IDF/BM25/n-gram analysis).

**Skills (1):** Science Bowl question prep — ingest, categorize, solve, and format question sets into study materials and PDFs.

See [plugins/middle-schooler/README.md](plugins/middle-schooler/README.md) for detailed usage.

## Marketplace Structure

```
claude-code-marketplace/
├── .claude-plugin/
│   └── marketplace.json       # Marketplace registry
├── plugins/
│   ├── finance-pack/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json    # Plugin manifest
│   │   ├── agents/            # 15 firm-based expert agents
│   │   ├── commands/          # Executable workflows
│   │   ├── skills/            # 11 analytical skill frameworks
│   │   ├── DISCLAIMER.md
│   │   └── README.md
│   └── middle-schooler/
│       ├── .claude-plugin/
│       │   └── plugin.json    # Plugin manifest
│       ├── agents/            # Spelling Bee + Science Bowl agents
│       ├── skills/            # Question prep skill
│       └── README.md
├── README.md
└── LICENSE
```

## Adding New Plugins

1. Create `plugins/<plugin-name>/` with `.claude-plugin/plugin.json`, `agents/`, `skills/`, and `commands/` directories
2. Add the plugin entry to `.claude-plugin/marketplace.json`
3. Keep versions in sync between `marketplace.json` and the plugin's `plugin.json`

## Disclaimer

**All plugins provide analytical frameworks for educational and research purposes only.** Firm-based agents are original works inspired by publicly known methodologies — not affiliated with or endorsed by any referenced firm. See each plugin's DISCLAIMER.md for details.

## License

MIT
