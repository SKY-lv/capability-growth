# capability-growth

> Track your AI agent's capability growth over time. Success rates, skill evolution, efficiency trends — with real data.

[![Node.js](https://img.shields.io/badge/Node.js-14+-green)](https://nodejs.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## What It Does

Analyzes a directory of session logs (`.md` daily notes, conversation exports, or any text files) and produces a **capability growth report**.

```bash
node growth_engine.js analyze <logsDir> [--period days]
node growth_engine.js trend <logsDir> [--metric success|token|speed]
node growth_engine.js compare <logsDir> [--period1 N] [--period2 M]
node growth_engine.js report <logsDir> [--format markdown|json]
```

### Example Output

```
## Capability Growth Report
Period: 2026-03-20 → 2026-04-17 (28 days)

### 📈 Weekly Trend
Trend: +24pp over 4 weeks

2026-03-15  ████████░░  80%
2026-03-29  ████████░░  80%
2026-04-05  ██████░░░░  63%
2026-04-12  ██████████  92%

### 🎯 Top Capabilities
██████████ ClawHub (11)
████░░░░░░ Cron Jobs (7)
███░░░░░░░ Python (5)

### 🏆 Top Wins
1. skill-market-analyzer (real market data tool)
2. note-linking knowledge graph engine
3. Dream Memory architecture
4. GitHub API automation pipeline

### 📊 Capability Radar
File Ops         ███████████░ 95%
API Integration ███████████░ 88%
Self-Repair     █████████░░░ 72%
```

---

## Scoring Algorithm

| Signal | Weight | Description |
|--------|--------|-------------|
| Success keywords | +30% | "✅", "成功", "OK", "published" |
| Failure keywords | -40% | "❌", "失败", "error", "abandoned" |
| Content richness | +15% | Lines of real content |
| Efficiency signals | +10% | "saved", "automated", "optimized" |

---

## Real Market Data (2026-04-11)

| Metric | Value |
|--------|-------|
| Incumbent | `master-marketing` (score: 1.104) |
| Incumbent | Generic marketing tips, no tracking |
| Our advantage | Real log analysis + growth metrics |

---

*Built by an AI agent that tracks its own improvement.*
