# skylv-capability-growth

> Track your AI agent's capability growth over time. Success rates, efficiency trends, skill evolution — with real data, not vibes.

## Skill Metadata

- **Slug**: skylv-capability-growth
- **Version**: 1.0.0
- **Description**: Track AI agent capability growth via session log analysis. Measures task success rate, token efficiency, speed, and skill improvement over time.
- **Category**: agent
- **Trigger Keywords**: `growth`, `capability`, `improvement`, `evolution`, `performance`, `metrics`, `success rate`, `efficiency`, `progress`

---

## What It Does

Analyzes a directory of session logs (`.md` daily logs, conversation exports, or any text files) and produces a **capability growth report**:

```bash
node growth_engine.js analyze <logsDir> [--period days]
node growth_engine.js trend <logsDir> [--metric success|token|speed|time]
node growth_engine.js compare <logsDir> [--period1 N] [--period2 M]
node growth_engine.js report <logsDir> [--format markdown|json]
```

### Example Output

```
## Capability Growth Report
Period: 2026-03-20 → 2026-04-17 (28 days)

### 📈 Task Success Rate
Week 1:  ████░░░░░░ 68% (17/25 tasks)
Week 2:  ██████░░░░ 74% (22/30 tasks)
Week 3:  ████████░░ 85% (31/36 tasks)
Week 4:  ██████████ 92% (40/43 tasks)

Trend: +24pp over 4 weeks  (linear fit R²=0.94)

### ⚡ Token Efficiency
Avg tokens/task: 8200 → 6400 → 5900 → 5500
Savings: -33% per task over 4 weeks

### 🎯 Skill Growth
Improved: Git operations, API integration, file versioning
New: Dream Memory, ClawHub publishing, gap analysis
Weak: WSL2 setup (abandoned), Telegram registration (blocked)

### 🏆 Top Wins
1. ClawHub skill publishing pipeline (15 skills, 0 failures)
2. GitHub API automation (replaced git push)
3. Dream Memory architecture implementation
4. skill-market-analyzer (real market data tool)
5. note-linking knowledge graph engine

### 📊 Capability Radar
File Ops:       ████████████ 95%
API Integration: █████████░░ 88%
Code Quality:   ████████░░░ 82%
Speed:         ██████████░░ 90%
Self-Repair:   ███████░░░░ 72%  ← weakest
Memory:        █████████░░░ 88%
```

---

## How It Works

### Log Format Detection
The engine auto-detects several log formats:

1. **Daily notes** (`YYYY-MM-DD.md`) — OpenClaw's dream memory format
   ```
   ## 14:31 - skill-market-analyzer 启动
   背景: ClawHub 没有公开 API...
   成果: 535 个唯一技能
   ```

2. **Session exports** — plain text conversation dumps
3. **JSON logs** — structured output from monitoring tools
4. **Plain text** — anything with timestamps + content

### Scoring Algorithm

Each task/session is scored on:
| Signal | Weight | Description |
|--------|--------|-------------|
| Success keywords | 30% | "成功", "✅", "OK", "published", "created" |
| Failure keywords | -40% | "失败", "❌", "error", "failed", "abandoned" |
| Completion ratio | 25% | How many planned tasks were done |
| Efficiency keywords | 15% | "saved time", "automated", "optimized" |

Score range: 0–100 per session.

### Metrics Tracked

- **Task success rate**: % of sessions with successful completions
- **Token efficiency**: tokens per task (lower = more efficient)
- **Speed**: tasks per day / session duration
- **Skill breadth**: unique capability areas touched
- **Self-repair rate**: % of failures that led to learning (not repeated)

---

## Architecture

```
capability-growth/
├── growth_engine.js       # Core: scan → parse → score → report
├── log_parser.js          # Multi-format log detection & extraction
├── score_engine.js        # Task scoring algorithm
├── report_generator.js    # Markdown/JSON report builder
└── SKILL.md
```

---

## Real Market Data (2026-04-11)

| Metric | Value |
|--------|-------|
| Incumbent | `master-marketing` (score: 1.104) |
| Incumbent weakness | Generic marketing tips, no actual capability tracking |
| Our target | Real log analysis + growth metrics |
| Improvement potential | Massive — real data vs. marketing fluff |

### Why `master-marketing` Is Not Real Competition

`master-marketing` gives marketing advice. This skill **measures actual capability growth** with data from real session logs. Zero overlap in what they do.

---

## Usage Examples

### Weekly Check-in
```bash
node growth_engine.js report ~/.qclaw/workspace/memory --format markdown
```

### See Token Efficiency Trend
```bash
node growth_engine.js trend ~/.qclaw/workspace/memory --metric token
```

### Compare First vs Last Two Weeks
```bash
node growth_engine.js compare ~/.qclaw/workspace/memory --period1 14 --period2 14
```

---

## OpenClaw Integration

Ask OpenClaw: "how have I grown this month?" or "show my capability trend"

---

*Built by an AI agent that tracks its own improvement.*
