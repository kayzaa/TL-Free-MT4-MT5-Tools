# Rules for Claude sessions in this repository

This is the PUBLIC showcase of trader.lifestyle's free MetaTrader tools (Forex Factory releases).
Read `_meta/README.md` for the maintenance details.

## Never
- Never add source code: no `.mq4`, `.mq5`, `.mqh`, `.py`, `.pine`, `.cpp`, `.dll`. Only compiled `.ex4` / `.ex5`, README.md pages and screenshots.
- Never touch the `.ex4` / `.ex5` binaries — they are refreshed from the local release zips.
- Never publish test or performance numbers: no profit factor, win rate, net profit / R, drawdown, "no edge", backtest trade counts, "0 deviations". Neutral risk note only.
- Never invent features, parameters or results. Only describe what the tool's own text states.
- Never edit the root `README.md` table directly — change `_meta/blurbs.txt` (`<project folder>|<one sentence>`); the table is regenerated locally.

## Always
- English for every public text.
- Credit the original author / Forex Factory thread / video of each idea and name our own additions concretely.
- Keep in every project README: header with shields.io badges, hero screenshot, "📥 Download" table, footer with Forex Factory thread (https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4), YouTube (https://www.youtube.com/@traderlifestyle), WhatsApp (https://wa.me/18585003724) and the bold "✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨" line.
- Mention honestly when a platform build is compile-only / runtime-unverified.
- After hand-editing a project README, delete its first line `<!-- auto-generated: ... -->` so the local publish script keeps your text.
- Hero screenshots: real charts only; never a screenshot whose panel shows red result statistics.
- Commit directly to `main`; the owner's local publish script pulls with rebase before pushing.
