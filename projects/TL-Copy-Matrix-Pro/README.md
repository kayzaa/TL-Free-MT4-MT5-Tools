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

## Overview

One Expert Advisor for both sides. Attach it in SENDER mode on the account you copy FROM and in RECEIVER mode on every account you copy TO. All terminals must run on the same PC or VPS (they talk through the MetaTrader common data folder - no DLL, no internet, no server, no extra software).

## Quick Start

- Sender terminal: open any chart, attach "TL Copy Matrix Pro", Mode = SENDER. That's all (works with the investor / read-only password).
- Receiver terminal: attach the EA on any chart, Mode = RECEIVER, "For Receiver: account number(s) to copy from" = the sender's account number.
- Press AutoTrading in the receiver terminal (and keep "Allow Algo Trading" ticked). The dashboard shows "LIVE" / CONNECTED as soon as the sender is found. One EA per terminal is enough - it copies every symbol.

Topologies: one-to-many, many-to-one (comma list of sender numbers in ONE receiver), many-to-many.

## What Is Copied

- Market positions and pending orders (limit, stop, stop-limit, expiry converted between broker time zones)
- SL / TP, and every later SL / TP / pending price change
- Partial closes, volume adds (netting senders), full closes
- A sender pending that fills before ours: our pending is replaced by a market copy
- Reverse mode: Buy <-> Sell, SL <-> TP, limit <-> stop
- Copies closed by hand on the receiver are never re-opened

## Lot & Risk

Lot mode: sender lot x multiplier / fixed lot / balance ratio x multiplier / equity ratio x multiplier / risk % at the SL. Contract size adjustment between brokers, min / max lot, below-minimum rule (use the minimum or skip).

## Symbols

Automatic: EURUSD = EURUSD.m = EURUSDm = EURUSD.pro, XAUUSD = GOLD, US30 = DJ30 = WS30, NAS100 = USTEC, GER40 = DE40 ... Manual: SymbolMappings "XAUUSD:GOLD,US30:DJ30". Prefix / suffix, white list and black list. Price mode RELATIVE keeps the SL / TP distance in pips when the two brokers quote different prices (indices, gold, crypto).

## Filters

Buy only / sell only, sender magic numbers (0 = manual trades), max spread, max distance to the sender's entry (never chase a moved price), max open copies, max trade age, copy trades already open at the start (on / off), trading days (Mon-Sun) and a time window (server, GMT or local time) with an optional close-all at the window end.

## Drawdown Protection (receiver)

based on equity or balance. Action: block new copies / close all + block until the reset / close all + pause for the cooldown. Daily reset at ResetHour:ResetMinute (server time). RESET button in the dashboard re-bases the start balance. Daily profit target: close all copies and pause until the next reset.

## Safety

- The sender never broadcasts while its terminal is disconnected; removals are confirmed for 60 ms, so a re-syncing terminal never makes receivers close trades.
- Sender offline (no heartbeat for N seconds): copies are KEPT, never closed by mistake. Optional: close everything after N minutes offline.
- Broker rejections are retried with a back-off (1.5 s ... 60 s), no spam.
- Dry run: the receiver shows and logs what it would copy without sending orders.
- Only trades with the EA's own magic number + copy tag are ever touched.

## Dashboard

Account info, sync status, copy speed in milliseconds (last / average / best), copy speed (sender), live configuration (lot multiplier +/-, reverse, pending, X closes the panel to a small pill, click the pill to open it, drag the header to move.

## Alerts

Popup, sound, push notification (mobile), e-mail. Important events always, every copied trade optionally.

## Notes

- Copy speed = time from the sender terminal seeing the trade until the copy is filled (same PC clock). Typically a few tens of milliseconds plus the broker's execution time.
- Netting receiver accounts are supported (one net position per symbol); pending orders are copied there when they fill.
- Links in the panel need "Allow DLL imports" (only used to open the browser).

trader.lifestyle  ·  YouTube @traderlifestyle

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
