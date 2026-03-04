# NR7 Range Breakout — Narrow Range Strategy

## Overview
Ye strategy NR7 pattern detect karti hai — jab current bar ka range pichle 7 bars ka sabse chhota ho. Ye extreme compression dikhata hai aur breakout ke baad big move expected hai. Inside bar ka advanced version hai ye.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum VOLATILITY COMPRESSION
        patterns trade karte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Trending entry chahiye?
                  |       #5 Strong Trending ya #12 Supertrend dekho
                  |
     Kya tumhe NARROW RANGE bar
     concept samajh aata hai?
                /     \
             YES       NO
              |         |
              |    ⚠️ Similar but simpler?
              |       #18 Inside Bar Breakout dekho
              |
     Kya stock mein BREAKOUT POTENTIAL hai
     (compression dikhta hai)?
                /     \
             YES       NO
              |         |
              |    ⏳ NR7 pattern ka wait karo
              |       ya #8 Bollinger Squeeze dekho
              |
     Kya VOLUME breakout pe above
     average hai (1.3x+)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Low volume breakout = false
              |       signal risk — wait karo
              |
     Kya TREND DIRECTION confirm hai
     (EMA filter)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Both sides possible —
              |       trend filter ON karo ya risk manage karo
              |
    ✅ NR7 RANGE BREAKOUT USE KARO!
    📁 25_NR7_Range_Breakout.pine
```

## Kaise Kaam Karta Hai
1. **NR7 Detection** — Current bar ka high-low range pichle 7 bars ka minimum hona chahiye.
2. **Breakout Entry** — NR7 bar ke high ke upar ya low ke neeche break pe entry.
3. **Volume Filter** — Breakout bar pe 1.3x+ average volume chahiye.
4. **Trend Filter** — Optional 50 EMA se direction bias.
5. **Expiry** — NR7 ke baad 3 bars ke andar breakout nahi hua toh signal cancel.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| NR Lookback | 7 | NR7 = last 7 bars ka narrowest range |
| Trend EMA | 50 | Direction filter |
| Volume Multiplier | 1.3x | Breakout pe min volume |
| Breakout Buffer | 0.1% | NR7 high/low ke upar/neeche buffer |
| ATR Multiplier | 1.5 | Stop loss distance |
| Risk:Reward | 2.5 | Higher R:R for compression breakouts |

## Best Used On
- **Timeframe:** 1H – Daily
- **Markets:** Pharma stocks (Dr Reddy's, Sun Pharma, Cipla), any stock with compression phases
- **Style:** Breakout / volatility expansion

## Setup
1. TradingView kholo → Pine Editor
2. `25_NR7_Range_Breakout.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Dr Reddy's (DRREDDY) — Daily Chart

**Scenario:** Dr Reddy's consolidation phase mein hai. NR7 pattern form ho raha hai — breakout aane wala hai.

1. **Compression Phase — NR7 Detection**
   - Last 7 bars ranges: ₹45, ₹38, ₹32, ₹28, ₹35, ₹40, ₹22
   - Today's range = ₹22 → **Sabse chhota! NR7 detected!** ✅
   - Purple background + "NR7" diamond marker dikhta hai
   - NR7 bar: High ₹6,480, Low ₹6,458
   - Market undecided hai — big move aane wala hai

2. **Next Day — Breakout!**
   - Dr Reddy's strong open ₹6,495 (FDA news positive)
   - NR7 high ₹6,480 + buffer (0.1%) = ₹6,487 → Close ₹6,510 uske upar ✅
   - 50 EMA = ₹6,400 → Price upar (trend bullish) ✅
   - Volume = 1.6x average ✅
   - "NR7↑" label dikhta hai
   - **Entry:** Long at ₹6,510

3. **Risk Management**
   - ATR(14) = ₹85, ATR Mult = 1.5
   - **Stop Loss:** ₹6,510 − (₹85 × 1.5) = ₹6,382
   - **Take Profit:** ₹6,510 + (₹128 × 2.5 R:R) = ₹6,830

4. **Week 2 — Compression release**
   - Dr Reddy's ne compressed energy release ki → ₹6,510 → ₹6,680 → ₹6,800
   - **Take profit hit at ₹6,830**
   - **Result:** +₹320/share (+4.9%)
   - 30 shares pe: **+₹9,600 profit**

**Kyun kaam kiya:** NR7 ne extreme compression identify kiya — 7 din ka sabse narrow bar. Ye "coiled spring" hai — jab release hua, move big aaya. Volume ne institutional interest confirm kiya.

**Dhyan rakho:**
- NR7 direction nahi batata — sirf compression batata hai. Trend filter breakout direction decide karta hai.
- Pharma stocks mein FDA/USFDA news sudden volatile moves laati hai — NR7 ke baad news catalysts powerful hote hain.
- Agar NR7 ke baad 3 bars mein breakout nahi hua = signal expired — fresh NR7 ka wait karo.
- NR4 (4-bar) ya NR14 (14-bar) bhi try kar sakte ho — lookback adjust karo.

## Notes
- Purple background NR7 bars highlight karta hai.
- "NR7" diamond markers narrow range bars pe dikhte hain.
- Breakout pending sirf 3 bars tak valid rehta hai.
- Higher R:R (2.5:1) compression breakouts ke explosive nature ke liye.
- Similar to #18 Inside Bar but mathematically defined (narrowest range).

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🟡 Intermediate                  ║
║  Risk Level:   Medium                           ║
║  Timeframe:    4H-Daily (best)                 ║
║  Frequency:    1-3 signals/day                  ║
║  Hold Time:    Days                             ║
║  Capital Need: ₹50,000+ (swing trading)         ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Range narrowing (compression)   ├── Already trending
├── Low vol before big move         ├── Gap opening days
├── Consolidation phases            ├── High volatility days
├── Pharma/healthcare stocks        ├── Penny stocks
├── Pre-event compression           ├── No clear compression
└── Volume declining setup          └── Random narrow bar
```

## 🔗 Best Strategy Combinations
- **#25 NR7 + #8 BB Squeeze** → Double compression = extremely powerful breakout
- **#25 NR7 + #18 Inside Bar** → NR7 + Inside Bar = triple compression signal
- **#25 NR7 + #1 ORB** → NR7 detected → next day ORB style breakout trade

## ⚠️ Common Mistakes
1. **Har NR7 bar trade karna** → NR7 + volume filter + trend direction chahiye
2. **Breakout direction guess karna** → Wait karo — breakout candle direction follow karo
3. **Dr Reddy's mein USFDA ignore** → Pharma stocks FDA decisions pe crash/rally karte hain
4. **3-bar expiry ignore karna** → NR7 ke 3 bars mein breakout na ho toh cancel — fresh setup wait
5. **Volume on breakout ignore** → Low volume breakout = fake, high volume = genuine

## 💡 Pro Tips
- NR7 + Inside Bar same bar pe = double compression — week mein 1-2 baar hota hai, very powerful
- Dr Reddy's mein ANDA/FDA approval dates track karo — NR7 before announcement = big move setup
- 3-bar expiry discipline important — stale setups work nahi karte
- Buffer (0.1%) use karo breakout levels pe — false breakout filter hota hai
- Weekly chart pe NR7 = multi-day breakout setup — hold for 3-5 days after breakout
