# Maintenance notes

- `blurbs.txt` — one line per tool: `<project folder>|<one-sentence description>`. Used for the tagline under each tool title and the "What it does" column of the main README. Edit freely.
- Project READMEs that still start with `<!-- auto-generated ... -->` are rebuilt on every local publish. **Remove that first line after hand-editing** a README, then it is never overwritten again.
- The root `README.md` table is regenerated on every local publish — change its text via `blurbs.txt`, not directly.
- Compiled builds (`MT4/`, `MT5/`) are refreshed from the local Forex Factory release zips. Never add source code (`.mq4`, `.mq5`, `.mqh`, `.py`, `.pine`).
- Public texts: English, no backtest numbers (no PF, win rate, net profit, drawdown figures), neutral risk note only.
