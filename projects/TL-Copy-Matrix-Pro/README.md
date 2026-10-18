<div align="center">

# ⚡ TL Copy Matrix Pro

**Local trade copier — one EA for sender and receiver, lot multipliers, netting support and millisecond copy speed.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Copy_Matrix_Pro_live_receiver.png" alt="TL Copy Matrix Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Copy Matrix Pro.ex5`](MT5/TL%20Copy%20Matrix%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **One EA, two roles** — attach it as **SENDER** on the account you copy from and as **RECEIVER** on every account you copy to.
- **No DLL, no internet, no server** — terminals on the same PC or VPS talk through the MetaTrader common data folder.
- **Copies everything that matters** — market positions, pending orders, SL / TP edits, partial closes, volume adds and full closes.
- **Smart lot sizing** — multiplier, fixed lot, balance or equity ratio, or risk % at the SL, with contract-size adjustment between brokers.
- **Built-in safety net** — equity protection, offline-sender handling, retry back-off and a dry-run mode.
- **Speed you can see** — the dashboard shows copy speed in milliseconds (last / average / best).

## 🚀 Quick start

1. **Sender terminal:** open any chart, attach **TL Copy Matrix Pro**, set **Mode = SENDER**. That's it — it even works with the investor (read-only) password.
2. **Receiver terminal:** attach the EA on any chart, set **Mode = RECEIVER** and enter the sender's account number in **"For Receiver: account number(s) to copy from"**.
3. Press **AutoTrading** in the receiver terminal and keep **"Allow Algo Trading"** ticked. The dashboard switches to **LIVE / CONNECTED** as soon as the sender is found.

One EA per terminal is enough — it copies every symbol.

**Topologies:** one-to-many, many-to-one (a comma-separated list of sender numbers in ONE receiver) and many-to-many.

## 🧠 How it works

### What is copied

- Market positions and pending orders (limit, stop, stop-limit) — expiry is converted between broker time zones.
- SL / TP, plus every later SL / TP / pending-price change.
- Partial closes, volume adds (netting senders) and full closes.
- If a sender pending order fills before ours, our pending is replaced by a market copy.
- **Reverse mode:** Buy ↔ Sell, SL ↔ TP, limit ↔ stop.
- Copies you close by hand on the receiver are never re-opened.

### Lot & risk

| Lot mode | Lot on the receiver |
|---|---|
| Multiplier | Sender lot × multiplier |
| Fixed | A fixed lot |
| Balance ratio | Balance ratio × multiplier |
| Equity ratio | Equity ratio × multiplier |
| Risk % | Risk % at the SL |

Plus contract-size adjustment between brokers, min / max lot, and a below-minimum rule (use the minimum or skip).

### Symbol matching

- **Automatic:** EURUSD = EURUSD.m = EURUSDm = EURUSD.pro, XAUUSD = GOLD, US30 = DJ30 = WS30, NAS100 = USTEC, GER40 = DE40 …
- **Manual:** `SymbolMappings` such as `XAUUSD:GOLD,US30:DJ30`.
- Prefix / suffix handling, white list and black list.
- **Price mode RELATIVE** keeps the SL / TP distance in pips when the two brokers quote different prices (indices, gold, crypto).

### Filters

Buy only / sell only, sender magic numbers (0 = manual trades), max spread, max distance to the sender's entry (never chase a moved price), max open copies, max trade age, copy trades already open at the start (on / off), trading days (Mon–Sun) and a time window (server, GMT or local time) with an optional close-all at the window end.

### Equity protection (receiver)

- Based on equity or balance.
- **Actions:** block new copies / close all + block until the reset / close all + pause for the cooldown.
- Daily reset at `ResetHour:ResetMinute` (server time); the **RESET** button in the dashboard re-bases the start balance.
- **Daily profit target:** close all copies and pause until the next reset.

### Safety

- The sender never broadcasts while its terminal is disconnected; removals are confirmed for 60 ms, so a re-syncing terminal never makes receivers close trades.
- **Sender offline** (no heartbeat for N seconds): copies are **kept**, never closed by mistake. Optional: close everything after N minutes offline.
- Broker rejections are retried with a back-off (1.5 s … 60 s) — no spam.
- **Dry run:** the receiver shows and logs what it would copy without sending orders.
- Only trades with the EA's own magic number + copy tag are ever touched.

## 🖥️ Dashboard & alerts

- Account info, sync status, copy speed in milliseconds (last / average / best) and sender-side copy speed.
- Live configuration right on the panel: lot multiplier − / +, reverse, pending.
- **X** collapses the panel to a small pill, click the pill to reopen it, drag the header to move it.
- **Alerts:** popup, sound, push notification (mobile) and e-mail. Important events are always reported; every copied trade optionally.

## 🛠️ Installation

1. Copy `TL Copy Matrix Pro.ex5` into **File → Open Data Folder → MQL5 → Experts** in every terminal (sender and receivers).
2. Refresh the Navigator (or restart MT5).
3. Attach the EA to any chart and choose **Mode = SENDER** or **Mode = RECEIVER** (see Quick start).
4. On the receiver, enable **AutoTrading** and keep **"Allow Algo Trading"** ticked.

## 📋 Requirements

- All terminals must run on the **same PC or VPS** (they share the MetaTrader common data folder).
- **"Allow DLL imports"** is only needed for the link buttons in the panel (used to open the browser).

## ⚠️ Notes

- **Copy speed** = time from the sender terminal seeing the trade until the copy is filled (same PC clock). Typically a few tens of milliseconds plus the broker's execution time.
- **Netting receiver accounts** are supported (one net position per symbol); pending orders are copied there when they fill.
- Copying multiplies exposure across accounts — test your setup on demo accounts first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
