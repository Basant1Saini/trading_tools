# Slow & Steady — Swing Strategy

## Overview
Ye ek patient swing-trading strategy hai jo triple EMA alignment (50/100/200), MACD momentum confirmation, aur ADX trend strength filtering pe based hai. Bade sustained moves ke liye designed — jaldi baazi nahi, dheere dheere pakka kaam.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    START
                      │
        Weeks/months tak hold karne
        ki patience hai?
                 /          \
               YES           NO
                │             │
                │        └──→ ❌ Ye swing strategy
                │             hai. Quick trades ke
                │             liye Scalper (#7) ya
                │             ORB (#1) dekho.
                │
        EMA 50 > EMA 100 > EMA 200
        aligned hai? (ya ulta
        bearish ke liye)
              /         \
            YES          NO
             │            │
             │       └──→ ⏳ EMAs tangled hain.
             │            Alignment ka wait
             │            karo. Force mat karo.
             │
        ADX 20 ke upar hai?
        (Trend strong enough?)
              /         \
            YES          NO
             │            │
             │       └──→ ❌ ADX low = choppy
             │            market. Pivot Points
             │            (#11) ya RSI Extremes
             │            (#3) better rahega.
             │
        Price EMA 50 ke paas
        pullback pe hai ya
        MACD crossover hua?
              /         \
            YES          NO
             │            │
             │       └──→ ⏳ Pullback ya MACD
             │            crossover ka wait
             │            karo. Chase mat karo.
             │
     ✅ SLOW & STEADY USE KARO!
     4_Slow_and_Steady.pine lagao
```

## Kaise Kaam Karta Hai
1. **Trend Alignment** — Teeno EMAs ek line mein hone chahiye (50 > 100 > 200 bullish ke liye).
2. **Momentum Trigger** — MACD line jab signal line ko trend direction mein cross kare.
3. **Pullback Entries** — Price EMA 50 tak pullback kare aur bounce kare, MACD aur ADX confirm karein.
4. **ADX Filter** — Sirf trade karo jab ADX threshold ke upar ho (default 20).
5. **Exit** — Trailing stop ya trend break (EMA alignment toot jaaye).

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| EMA 50 / 100 / 200 | 50, 100, 200 | Triple EMA lengths |
| MACD Fast/Slow/Signal | 12, 26, 9 | Standard MACD settings |
| ADX Length | 14 | ADX calculation period |
| ADX Threshold | 20 | Minimum ADX trade ke liye |
| ATR Multiplier | 2.5 | Initial stop loss distance |
| Trailing Stop ATR | 3.0 | Trailing stop distance |

## Best Used On
- **Timeframe:** 4H – Daily
- **Markets:** NSE large-caps (Infosys, TCS, Reliance, HUL)
- **Style:** Swing trading (days se weeks tak hold)

## Setup
1. TradingView kholo → Pine Editor
2. `4_Slow_and_Steady.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Daily chart pe out of the box achha kaam karta hai

## Example: Infosys (INFY) — Daily Chart

**Scenario:** Infosys kaafi mahino se uptrend mein hai. Swing entry chahiye pullback pe.

1. **Trend Check**
   - EMA 50: ₹1,620 | EMA 100: ₹1,580 | EMA 200: ₹1,510
   - **50 > 100 > 200** → Teeno aligned bullish (green ribbon dikhega)
   - ADX = 27 (threshold 20 se upar → strong enough)

2. **Entry Signal — MACD Crossover**
   - 2 hafte ke pullback ke baad, Infosys ₹1,628 tak gira (EMA 50 ke paas)
   - MACD line ne signal line ko upar cross kiya
   - **Entry:** Long at ₹1,630

3. **Risk Management**
   - ATR(14) = ₹38, ATR Mult = 2.5
   - **Stop Loss:** ₹1,630 − (₹38 × 2.5) = ₹1,535
   - **Trailing Stop:** ATR × 3.0 = ₹114 trailing distance

4. **Week 1–3 — Uptrend resume**
   - Price ₹1,680 tak, phir ₹1,740
   - Trailing stop move: ₹1,740 − ₹114 = ₹1,626

5. **Week 5 — Trend break**
   - EMA 50 ne EMA 100 ko neeche cross kiya → **Exit at ₹1,710**
   - **Result:** +₹80/share (+4.9%) ~5 weeks mein
   - 200 shares pe: **+₹16,000 profit**

**Kyun kaam kiya:** Triple EMA alignment ne sustained uptrend confirm kiya. EMA 50 pe pullback entry low-risk thi.

**Dhyan rakho:**
- EMAs tangled/flat hain toh trade force mat karo — clean alignment ka wait karo.
- Results se pehle trend disrupt ho sakta hai — report se pehle exit sochna.
- IT stocks mein USD/INR movement ka bhi impact hota hai.

## Notes
- Green/red ribbon EMA 50 aur 200 ke beech fill hota hai.
- Arrow markers crossover aur pullback entries pe dikhte hain.
- EMA alignment break hone pe auto exit ho jaata hai.
