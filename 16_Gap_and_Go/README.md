# Gap and Go — Opening Gap Strategy

## Overview
Ye strategy opening gap trade karti hai — jab stock previous close se significantly upar ya neeche open ho aur gap ki direction mein momentum continue kare. Gap ki direction mein pehle 15-30 min mein entry leti hai volume confirmation ke saath.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya stock aaj GAP UP ya GAP DOWN
        open hua hai (>0.5%)?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ No gap = no trade
                  |       #1 ORB ya #6 VWAP Bounce dekho
                  |
     Kya gap size REASONABLE hai
     (0.5% – 5%, extreme nahi)?
                /     \
             YES       NO
              |         |
              |    ❌ Extreme gap (>5%) risky
              |       gap fill ka chance — skip karo
              |
     Kya VOLUME above average hai
     (1.5x+ normal volume)?
                /     \
             YES       NO
              |         |
              |    ⏳ Low volume gap = weak
              |       wait karo ya #7 Scalper dekho
              |
     Kya price gap direction mein
     CONTINUE kar rahi hai (fill nahi)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Gap fill ho raha hai —
              |       #3 RSI Extremes better hoga
              |
     Kya pehle 15-30 min ke andar ho
     (entry window active)?
                /     \
             YES       NO
              |         |
              |    ❌ Late entry = reduced edge
              |       kal ka gap wait karo
              |
    ✅ GAP AND GO USE KARO!
    📁 16_Gap_and_Go.pine
```

## Kaise Kaam Karta Hai
1. **Gap Detection** — Previous close vs today open se gap % calculate hota hai.
2. **Direction Confirm** — Price gap direction mein continue kare (gap up mein upar, gap down mein neeche).
3. **Volume Filter** — 1.5x average volume chahiye — indicates institutional interest.
4. **Entry Window** — Sirf pehle 3 bars (configurable) mein entry — late entry avoid.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Min Gap % | 0.5% | Minimum gap size trade karne ke liye |
| Max Gap % | 5.0% | Maximum gap — extreme gaps avoid |
| Avoid Gap Fill | On | Gap fill direction mein trade avoid |
| Volume Multiplier | 1.5x | Min volume vs 20-bar average |
| ATR Multiplier | 1.5 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |
| Entry Window | 3 bars | Gap open ke baad kitne bars mein entry |

## Best Used On
- **Timeframe:** 5m – 15m
- **Markets:** IT stocks (HCL Tech, TCS, Infosys), high-beta stocks
- **Style:** Intraday momentum — first 30 minutes

## Setup
1. TradingView kholo → Pine Editor
2. `16_Gap_and_Go.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Session window Indian market ke liye: 09:15–09:45

## Example: HCL Tech (HCLTECH) — 5 Minute Chart

**Scenario:** HCL Tech ne strong Q3 results report kiye hain. Market gap up open hone wala hai.

1. **Previous Day Close & Today Open**
   - Previous close: ₹1,680
   - Today open: ₹1,712 (gap up +₹32, +1.9%)
   - Gap range: 0.5% – 5% ✅
   - 20 EMA = ₹1,690 → Open EMA ke upar ✅

2. **09:20 AM — First 5-min candle close**
   - HCL Tech close ₹1,718 (open ke upar, gap continue)
   - Volume: 2.1x average (heavy institutional buying) ✅
   - Gap fill check: ₹1,718 > ₹1,680 (previous close ke upar) ✅
   - **Entry:** Long at ₹1,718

3. **Risk Management**
   - ATR(14) on 5m = ₹8.50, ATR Mult = 1.5
   - **Stop Loss:** ₹1,718 − (₹8.50 × 1.5) = ₹1,705
   - **Take Profit:** ₹1,718 + (₹13 × 2.0 R:R) = ₹1,744

4. **10:00 AM — Gap and Go worked!**
   - IT sector mein broad buying, HCL Tech ₹1,748 tak rally
   - **Take profit hit at ₹1,744**
   - **Result:** +₹26/share (+1.5%)
   - 200 shares pe: **+₹5,200 profit**

**Kyun kaam kiya:** Strong results ne genuine gap create kiya. Volume 2x+ tha — institutional buying confirm. Gap fill nahi hua — momentum continue kiya.

**Dhyan rakho:**
- Result day pe gap bahut common hai lekin volatile bhi — tight SL rakho.
- Agar gap 5% se zyada hai, usually gap fill hota hai — avoid karo.
- IT stocks mein US market overnight movement bhi gap ka reason hota hai.
- 09:15–09:20 ke beech order mat do — pehla candle close hone do.

## Notes
- Green/red background entry window dikhata hai.
- "GAP↑" / "GAP↓" labels entry points pe dikhte hain.
- Gap fill filter default ON hai — safer trades.
- Best results trending market mein aate hain, na ki choppy days mein.

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🟡 Intermediate                  ║
║  Risk Level:   Medium-High                      ║
║  Timeframe:    5m (best), 15m                  ║
║  Frequency:    1-3 signals/morning              ║
║  Hold Time:    1-3 hours (morning session)      ║
║  Capital Need: ₹50,000+ (intraday margin)       ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Gap up/down > 0.5%             ├── No gap / flat open
├── Volume 1.5x+ on open           ├── Extreme gap > 5%
├── Results/news driven gap         ├── Low volume gap
├── Gap direction continuing        ├── Gap filling immediately
├── First 30 min window             ├── After 10:00 AM entry
└── IT/Pharma results season        └── Random gap no catalyst
```

## 🔗 Best Strategy Combinations
- **#16 Gap + #1 ORB** → Gap + ORB range breakout = double confirmation
- **#16 Gap + #7 Scalper** → Gap morning mein scalp opportunities maximum
- **#16 Gap + #6 VWAP** → Gap direction + VWAP level = strong bias

## ⚠️ Common Mistakes
1. **5% se bada gap trade karna** → Extreme gaps usually fill hote hain — avoid
2. **First candle close se pehle entry** → 9:15-9:20 wait karo, pehla candle close hone do
3. **Gap fill ke against trade karna** → Gap filling = momentum reverse — exit ya skip
4. **HCL Tech results pe full size** → Results day volatile — half position se start
5. **10:00 ke baad gap trade** → Edge sirf pehle 30-45 min hai — late entry avoid

## 💡 Pro Tips
- Results day gaps sabse reliable hote hain — genuine institutional buying/selling
- HCL Tech/TCS mein US market overnight move = gap ka primary reason
- Pre-market (9:00-9:15) mein expected gap calculate karo (SGX Nifty/GIFT Nifty se)
- Gap up + open = high of day rarely → usually gap direction continue karta hai
- Volume first 5 min candle mein 2x+ = institutional participation confirmed
