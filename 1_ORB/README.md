# ORB — Opening Range Breakout

## Overview
Ye ek intraday strategy hai jo market open hone ke baad pehle 15-minute ka high aur low track karti hai, aur jab price us range ko todta hai tab entry leti hai. Volatile stocks aur indices ke liye best hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    START
                      │
            Intraday trade karna hai?
                 /          \
               YES           NO
                │             │
      Market abhi open        └──→ ❌ Ye strategy
      hone wala hai?                sirf intraday hai.
           /       \                Dusri dekho.
         YES       NO
          │         │
          │    └──→ ❌ ORB sirf
          │        market open ke
          │        pehle 1-2 hr
          │        kaam karta hai.
          │
    Stock/Index liquid hai?
    (Reliance, Nifty, BankNifty)
         /          \
       YES           NO
        │             │
        │        └──→ ❌ Illiquid stocks
        │             mein spread zyada,
        │             false breakouts.
        │
    Opening range ka size
    theek hai? (na bahut
    chhota, na bahut bada)
         /          \
       YES           NO
        │             │
        │        └──→ ❌ Chhota range =
        │             weak breakout.
        │             Bada range =
        │             SL bahut dur.
        │
   ✅ ORB STRATEGY USE KARO!
   1_ORB.pine chart pe lagao
```

## Kaise Kaam Karta Hai
1. **Opening Range** — Market khulne ke baad pehle 15 minutes (configurable) mein strategy high aur low record karti hai.
2. **Breakout Entry** — Jab range set ho jaaye, price agar ORB High ke upar jaaye toh Long, aur ORB Low ke neeche jaaye toh Short.
3. **Exit** — ATR-based stop loss / take profit se, ya phir session end pe automatically close ho jaata hai.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Opening Range Session | 09:15–09:30 | Opening range ka time window (NSE ke liye adjust karo) |
| Trading Session | 09:15–15:30 | Trading hours (Indian market) |
| ATR Length | 14 | Stop loss ke liye ATR period |
| ATR Multiplier | 1.5 | ATR pe kitna multiply karna hai stop ke liye |
| Risk:Reward Ratio | 2.0 | Take profit = stop distance ka 2x |

## Best Used On
- **Timeframe:** 1m – 5m charts
- **Markets:** NSE/BSE stocks (Reliance, HDFC, TCS), Nifty/BankNifty futures
- **Sessions:** Market ke pehle 1–2 ghante mein sabse achha kaam karta hai

## Setup
1. TradingView kholo → Pine Editor
2. `1_ORB.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Session time ko Indian market ke hisaab se adjust karo (09:15–09:30)

## Example: Reliance Industries (RELIANCE) — 5 Minute Chart

**Scenario:** Reliance mein morning mein achha movement aa raha hai, Q3 results ke baad.

1. **09:15–09:30 (Opening Range ban raha hai)**
   - ORB High: ₹2,485
   - ORB Low: ₹2,462
   - Range = ₹23 (achha range hai, volatile day lag raha hai)

2. **09:38 — Breakout candle close hua ₹2,489 pe (ORB High ₹2,485 ke upar)**
   - **Entry:** Long at ₹2,489
   - ATR(14) = ₹18, ATR Mult = 1.5
   - **Stop Loss:** ₹2,489 − (₹18 × 1.5) = ₹2,462
   - **Take Profit:** ₹2,489 + (₹27 × 2.0 R:R) = ₹2,543

3. **10:20 — Reliance rally kar raha hai ₹2,530 tak**
   - Momentum strong hai, TP ke paas aa raha hai

4. **10:45 — Take profit hit at ₹2,543**
   - **Result:** +₹54/share (+2.2%)
   - Agar 100 shares the toh: **+₹5,400 profit**

**Kyun kaam kiya:** Reliance mein results ke baad institutional buying thi. Opening range clean tha aur breakout mein volume bhi achha tha. FII/DII dono buyers the.

**Dhyan rakho:**
- Agar range bahut chhota hai (<₹10 Reliance mein), toh breakout mein dum nahi hoga — skip karo.
- Agar price ORB High aur Low ke beech mein ghoom raha hai, toh range-bound day hai — stop out ho jaoge.
- Budget day, RBI policy day pe ORB range zyada wide hota hai — SL accordingly adjust karo.

## Notes
- ORB zone chart pe shaded region ki tarah dikhta hai high aur low ke beech.
- Strategy session end pe sab positions close kar deti hai — overnight risk nahi hai.
- VWAP ya volume filters ke saath combine karo better results ke liye.

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🟢 Beginner                      ║
║  Risk Level:   Medium                           ║
║  Timeframe:    5m (best), 15m                   ║
║  Frequency:    5-15 signals/day                 ║
║  Hold Time:    1-4 hours (intraday)             ║
║  Capital Need: ₹50,000+ (intraday margin)       ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Volatile opening day            ├── Sideways/range-bound day
├── News-driven gap + range         ├── Very small range (<0.3%)
├── High pre-market volume          ├── Budget/RBI policy day
├── Trending market day             ├── Low volume opening
├── Clear ORB high/low formed       ├── Holidays ke agle din
└── FII/DII data positive           └── Expiry day (whipsaws)
```

## 🔗 Best Strategy Combinations
- **#1 ORB + #6 VWAP** → VWAP confluence se ORB breakout confirm karo
- **#1 ORB + #16 Gap and Go** → Gap open pe ORB range extra strong hota hai
- **#1 ORB + #11 Pivot Points** → Pivot levels as ORB targets use karo
- **#1 ORB + #7 Scalper** → ORB breakout ke baad quick scalps le lo

## ⚠️ Common Mistakes
1. **Range bahut chhota hone pe bhi trade karna** → Min ₹10-15 range (large caps) chahiye
2. **Late entry** → ORB breakout ke 30+ min baad entry = edge khatam
3. **Volume ignore karna** → Breakout candle pe volume 1.5x+ hona chahiye
4. **Both sides trade karna** → Daily bias decide karo (gap up = long bias)
5. **Session end pe trade kholna** → 2:00 PM ke baad new ORB trade avoid

## 💡 Pro Tips
- Pre-market (9:00-9:15) mein order book depth check karo — buying/selling pressure samjho
- ORB range + VWAP agar same zone mein hai toh breakout very strong hota hai
- First 15-min candle body > 70% of range = strong conviction candle
- Expiry day pe ORB avoid karo — options activity se whipsaws zyada hote hain
- Nifty/BankNifty ka ORB pehle check karo — index direction individual stock ko follow karta hai
