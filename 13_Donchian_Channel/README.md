# Donchian Channel — Turtle Trading

## Overview
Richard Dennis ke legendary Turtle Trading system pe based hai. 20-period Donchian Channel ke breakout pe entry aur 10-period channel pe exit, saath mein favorable moves pe position pyramid karna.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum LONG-TERM trend follow
        karna chahte ho (weeks/months)?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Short-term chahiye?
                  |       #7 Scalper ya #1 ORB dekho
                  |
     Kya tum SYSTEMATIC rules follow
     kar sakte ho (no emotions)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Turtle system mechanical hai —
              |       discretionary? #10 Fibonacci ya #9 Ichimoku dekho
              |
     Kya stock mein BREAKOUT potential hai
     (consolidation ke baad, catalyst hai)?
                /     \
             YES       NO
              |         |
              |    ❌ Range-bound stocks mein
              |       Donchian breakouts false hote hain — #11 Pivot Points dekho
              |
     Kya tum PYRAMIDING risk handle
     kar sakte ho (position adding)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Pyramid off karo settings mein
              |       ya #4 Slow & Steady use karo
              |
     Kya tum PATIENCE rakh sakte ho
     (weeks tak hold karna padega)?
                /     \
             YES       NO
              |         |
              |    ❌ Quick results chahiye?
              |       #7 Scalper ya #6 VWAP Bounce dekho
              |
    ✅ DONCHIAN CHANNEL USE KARO!
    📁 13_Donchian_Channel.pine
```

## Kaise Kaam Karta Hai
1. **Entry Channel (20)** — Price 20-bar high ke upar break kare toh long; 20-bar low ke neeche toh short.
2. **Exit Channel (10)** — Long exit jab price 10-bar low ke neeche; short exit jab 10-bar high ke upar.
3. **Skip Filter** — Pichla trade agar winner tha toh next entry skip karo (Turtle System 1 rule).
4. **Pyramid** — Har 0.5 ATR favorable move pe position add karo, max limit tak.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Entry Channel | 20 | Breakout entry ka lookback |
| Exit Channel | 10 | Trailing exit ka lookback |
| Skip if Last Won | On | Turtle System 1 filter |
| ATR Length | 20 | Position sizing aur stops ke liye ATR |
| ATR Multiplier | 2.0 | Stop loss distance |
| Max Pyramid | 3 | Max add-on entries |

## Best Used On
- **Timeframe:** Daily – Weekly (original Turtle system daily tha)
- **Markets:** Trending stocks (ITC, HUL, Asian Paints), commodities, Nifty
- **Style:** Long-term trend following / position trading

## Setup
1. TradingView kholo → Pine Editor
2. `13_Donchian_Channel.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: ITC Limited (ITC) — Daily Chart

**Scenario:** ITC lamba consolidation phase ke baad breakout de raha hai FMCG growth aur demerger news ke chalte.

1. **Channel Levels**
   - 20-day High: ₹465 (entry channel top)
   - 20-day Low: ₹440 (entry channel bottom)
   - 10-day Low: ₹452 (exit channel bottom)
   - Previous trade: Loss tha (skip filter = OK, entry allowed)

2. **Breakout!**
   - ITC ₹468 pe close — 20-day high ₹465 ke upar break kiya
   - Skip filter check: Last trade loss tha → **Entry allowed** ✅
   - **Entry:** Long at ₹468
   - Exit channel stop: 10-day low = ₹452

3. **Pyramid Entries**
   - ATR(20) = ₹8.50
   - ITC ₹473 pe pahuncha (₹468 + ₹4.25 = half ATR move) → **Pyramid #1 at ₹473**
   - ITC ₹478 pe (₹473 + ₹4.25) → **Pyramid #2 at ₹478**
   - ITC ₹483 pe (₹478 + ₹4.25) → **Pyramid #3 at ₹483** (max reached)

4. **Week 3–6 — ITC trend continue karta hai**
   - Price ₹505 tak rally, 10-day low ab ₹492 pe move hua

5. **Week 7 — Exit channel trigger**
   - ITC dip karta hai ₹490 tak → 10-day low ₹492 ke neeche
   - **Exit all at ₹490**
   - Entry 1: +₹22 (+4.7%), Entry 2: +₹17 (+3.6%), Entry 3: +₹12 (+2.5%), Entry 4: +₹7 (+1.4%)
   - 200 shares per entry pe: **Total ₹11,600 profit**

**Kyun kaam kiya:** ITC ka breakout genuine tha — lamba consolidation ke baad demerger catalyst ne institutional buying layi. Pyramiding ne trending phase mein gains multiply kiye.

**Dhyan rakho:**
- ITC jaisi slow-moving stocks mein 20-day breakout zyada reliable hota hai — chotu timeframe mat use karo.
- Skip filter choppy market mein false breakouts se losses kam karta hai.
- Pyramid entries risk multiply karti hain — har entry pe size chota rakho.
- FMCG stocks mein trends slow but steady hote hain — patience rakho, jaldi exit mat karo.

## Notes
- Blue channel 20-period entry range; orange lines 10-period exit range dikhate hain.
- "TURTLE" labels breakout entries pe dikhte hain.
- Skip filter false breakouts ke losses kam karta hai.
- Systematic strategy hai — rules mechanically follow karo.

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🔴 Advanced                      ║
║  Risk Level:   Medium-High                      ║
║  Timeframe:    Daily-Weekly (best)             ║
║  Frequency:    1-3 signals/month                ║
║  Hold Time:    Weeks to Months                  ║
║  Capital Need: ₹2,00,000+ (drawdown buffer)     ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Strong trending market          ├── Sideways/range-bound
├── Commodity/metal stocks          ├── Weak trend/low ADX
├── Breakout with volume            ├── Small cap/illiquid
├── Patience for weeks hold         ├── Impatient trading style
├── Systematic rule-following       ├── Discretionary exits
└── Position sizing discipline      └── Over-leveraging
```

## 🔗 Best Strategy Combinations
- **#13 Donchian + #9 Ichimoku** → Ichimoku direction confirm + Donchian breakout
- **#13 Donchian + #4 Slow & Steady** → Donchian entry + Slow&Steady hold style
- **#13 Donchian + #21 Chandelier** → Chandelier trailing with Donchian breakout

## ⚠️ Common Mistakes
1. **Jaldi exit karna (drawdown se dar)** → Turtle system mein 10-20% drawdown normal hai
2. **Pyramid position bahut badi** → Per-add max 0.5-1% risk, total max 2%
3. **ITC mein unrealistic expectations** → ITC slow mover — patient raho, target realistic
4. **20-day breakout ignore karke lower entry** → System follow karo — entries predefined hain
5. **Sideways market mein Donchian** → Channel tight hai = no breakout, avoid!

## 💡 Pro Tips
- Turtle Trading original rules follow karo — 20-day breakout entry, 10-day exit
- ITC mein FMCG sector momentum check karo — sector rotation mein ITC late mover hai
- Pyramiding: har breakout add pe stop tighten karo — net risk same rakhne ke liye
- Monthly chart pe Donchian channel break = multi-month trend start signal
- Win rate 35-40% expected hai — R:R 3:1+ se system profitable banta hai
