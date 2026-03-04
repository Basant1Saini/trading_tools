# Pivot Points — S/R Trading

## Overview
Ye strategy classic pivot point support aur resistance levels pe trade karti hai jo previous period ke high, low, aur close se calculate hote hain. Traditional, Fibonacci, aur Camarilla teeno pivot formulas support karti hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum well-defined S/R LEVELS
        pe trade karna chahte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Dynamic levels chahiye?
                  |       #12 Supertrend ya #9 Ichimoku dekho
                  |
     Kya tum INTRADAY ya short-term
     swing trade karte ho?
                /     \
             YES       NO
              |         |
              |    ❌ Long-term ke liye
              |       #13 Donchian ya #4 Slow & Steady dekho
              |
     Kya tum Nifty/BankNifty FUTURES
     ya liquid stocks trade karte ho?
                /     \
             YES       NO
              |         |
              |    ⚠️ Illiquid stocks mein pivots
              |       unreliable — #6 VWAP ya #5 Strong Trending dekho
              |
     Kya tumhe BOUNCE (reversal from level)
     ya BREAKOUT (through level) chahiye?
                /     \
          BOUNCE    BREAKOUT
              |         |
              |    ⚠️ Breakout mode use karo
              |       (R1/R2 ke upar ya S1/S2 ke neeche)
              |
     Kya price pivot level ke PAAS
     aa rahi hai (buffer ke andar)?
                /     \
             YES       NO
              |         |
              |    ⏳ Wait karo — price level
              |       se door hai abhi
              |
    ✅ PIVOT POINTS USE KARO!
    📁 11_Pivot_Points.pine
```

## Kaise Kaam Karta Hai
1. **Pivot Calculation** — PP, R1–R3, aur S1–S3 previous period (Daily by default) se calculate hota hai.
2. **Bounce Mode** — Support levels (S1/S2) pe long, resistance levels (R1/R2) pe short jab price touch karke reverse kare.
3. **Breakout Mode** — R1/R2 ke upar break pe long, S1/S2 ke neeche break pe short.
4. **Three Pivot Types** — Traditional, Fibonacci, aur Camarilla formulas.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Pivot Type | Traditional | Traditional, Fibonacci, ya Camarilla |
| Pivot Timeframe | Daily | Pivot calculation ka period |
| Entry Mode | Bounce | Levels se bounce ya breakout through |
| Bounce Buffer | 0.15% | Bounce entries ke liye proximity tolerance |
| ATR Multiplier | 1.5 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 5m – 1H (Daily pivots ke saath) ya 1H – 4H (Weekly pivots)
- **Markets:** Nifty 50, BankNifty futures, liquid stocks
- **Style:** Intraday ya swing S/R trading

## Setup
1. TradingView kholo → Pine Editor
2. `11_Pivot_Points.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Nifty 50 Index — 15 Minute Chart

**Scenario:** Nifty futures pe intraday trading kar rahe ho daily pivot levels ke saath.

1. **Previous Day Data (Pivot Calculation)**
   - Previous High: 22,480
   - Previous Low: 22,280
   - Previous Close: 22,420
   - **PP** = (22,480 + 22,280 + 22,420) / 3 = **22,393**
   - **R1** = (2 × 22,393) − 22,280 = **22,506**
   - **S1** = (2 × 22,393) − 22,480 = **22,306**
   - **R2** = 22,393 + (22,480 − 22,280) = **22,593**
   - **S2** = 22,393 − (22,480 − 22,280) = **22,193**

2. **10:00 AM — Price S1 ke paas aaya**
   - Nifty gir ke 22,315 tak aaya (S1 = 22,306 ke buffer mein)
   - Bounce Buffer = 0.15% → S1 + buffer = 22,340
   - Low 22,310 touch kiya, candle close 22,340 (S1 ke upar)
   - **Entry:** Long at 22,340 (S1 bounce)

3. **Risk Management**
   - ATR(14) on 15m = 45 points, ATR Mult = 1.5
   - **Stop Loss:** 22,340 − (45 × 1.5) = 22,273
   - **Take Profit:** 22,340 + (67 × 2.0 R:R) = 22,474

4. **11:30 AM — Pivot bounce kaam kiya**
   - Nifty S1 se bounce karke PP (22,393) ke paas aa gaya, phir R1 ki taraf
   - **Take profit hit at 22,474**
   - **Result:** +134 points
   - 1 lot (50 qty) pe: **+₹6,700 profit**

**Kyun kaam kiya:** Pivot points pe institutional order flow hoti hai. S1 ek widely-watched level hai jahan traders buy karte hain. Bounce clean tha volume ke saath.

**Dhyan rakho:**
- Nifty agar gap-up/gap-down open kare toh pivot levels ka context change ho jaata hai — PP se dur open ho toh dhyan se trade karo.
- Camarilla pivots tighter hain aur intraday range trading ke liye better hain.
- Expiry day pe pivot levels pe zyada activity hoti hai — lekin whipsaw bhi zyada hota hai.
- BankNifty ke pivots Nifty se alag calculate karo — dono ka behavior different hota hai.

## Notes
- Pivot levels horizontal lines ki tarah plot hote hain (yellow=PP, red=R levels, green=S levels).
- Camarilla pivots tighter hain intraday ke liye.
- Volume aur candle patterns ke saath combine karo higher conviction ke liye.

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🟡 Intermediate                  ║
║  Risk Level:   Medium                           ║
║  Timeframe:    5m-15m (best)                   ║
║  Frequency:    5-15 signals/day                 ║
║  Hold Time:    Minutes to Hours                 ║
║  Capital Need: ₹50,000+ (intraday margin)       ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Any market condition            ├── Very low volume days
├── Volatile intraday days          ├── Holiday-adjacent sessions
├── Index trading (Nifty/BN)        ├── Penny stocks
├── Clear pivot bounce/break        ├── Ignoring daily bias
├── Banking stocks intraday         ├── Fighting pivot direction
└── Gap open near pivot level       └── After 2:30 PM new trades
```

## 🔗 Best Strategy Combinations
- **#11 Pivot + #6 VWAP** → Pivot + VWAP same zone = institutional level
- **#11 Pivot + #1 ORB** → ORB breakout + Pivot target = clear plan
- **#11 Pivot + #20 StochRSI** → Pivot level pe StochRSI timing for entry

## ⚠️ Common Mistakes
1. **Exact pivot level pe entry** → Level ke pass reaction ka wait karo, exact level pe nahi
2. **R3/S3 trade karna** → R1/S1 most reliable, R3/S3 rarely hit hote hain
3. **Nifty 50 mein sirf pivot rely** → Nifty mein VWAP + Pivot combo use karo
4. **Previous day range ignore** → Small range = tight pivots, wide range = wide pivots
5. **All pivot types mix karna** → Ek type choose karo (Classic/Fibonacci) aur stick to it

## 💡 Pro Tips
- Nifty 50 pe Pivot Points internationally bhi respected hote hain — FII bhi use karte hain
- Gap open above R1 = very bullish day, gap open below S1 = very bearish day
- Pivot + VWAP ±₹5 ke andar ho toh very strong support/resistance zone
- Monday ko previous week pivots bhi check karo — weekly pivots strong hote hain
- Pivot point (P) ke upar open = bullish bias, neeche open = bearish bias — simple rule
