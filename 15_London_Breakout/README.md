# London Breakout — Session Strategy

## Overview
Ye ek forex-focused strategy hai jo Asian session ki range ka breakout London open ke time trade karti hai. London session mein jab liquidity aati hai toh volatility expand hoti hai — us move ko capture karna hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum FOREX trading karte ho
        (USD/INR, EUR/INR, etc.)?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Stocks ke liye
                  |       #1 ORB ya #6 VWAP Bounce dekho
                  |
     Kya tum SESSION-BASED breakout
     trade karna chahte ho?
                /     \
             YES       NO
              |         |
              |    ⚠️ Session timing nahi follow karte?
              |       #5 Strong Trending ya #12 Supertrend dekho
              |
     Kya Asian session mein TIGHT RANGE
     bani hai (narrow, <30 paise)?
                /     \
             YES       NO
              |         |
              |    ❌ Wide range = low breakout
              |       probability — skip karo, kal try karo
              |
     Kya London session open ho gayi
     (12:30 PM IST / 07:00 UTC)?
                /     \
             YES       NO
              |         |
              |    ⏳ Wait karo — London open
              |       ka time hone do
              |
     Kya price Asian range + buffer ke
     UPAR ya NEECHE break kar rahi hai?
                /     \
             YES       NO
              |         |
              |    ⏳ Breakout nahi hua —
              |       patience rakho, force mat karo
              |
    ✅ LONDON BREAKOUT USE KARO!
    📁 15_London_Breakout.pine
```

## Kaise Kaam Karta Hai
1. **Asian Range** — Asian session (00:00–07:00 UTC) ke dauran high aur low record karo.
2. **London Breakout** — London open (07:00 UTC) ke baad price agar Asian range ke upar/neeche break kare toh entry with pip buffer.
3. **One Shot** — Din mein sirf 1 trade (configurable) — whipsaws se bachne ke liye.
4. **Close Window** — London/NY overlap khatam hone tak position close ho jaati hai.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Asian Range Session | 00:00–07:00 UTC | Range building ka time window |
| London Trading Window | 07:00–11:00 UTC | Breakout entry ka allowed window |
| Breakout Buffer | 5 pips | Range ke upar/neeche buffer |
| Pip Value | 0.0001 | Pip size (JPY pairs ke liye 0.01) |
| ATR Multiplier | 1.5 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |
| Max Trades/Day | 1 | Session mein max entries |

## Best Used On
- **Timeframe:** 5m – 30m
- **Markets:** Forex pairs (USD/INR, EUR/INR, GBP/USD, EUR/USD)
- **Style:** Session-based intraday breakout

## Setup
1. TradingView kholo → Pine Editor
2. `15_London_Breakout.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Session times apne chart ke timezone ke hisaab se adjust karo
5. USD/INR ke liye Pip Value 0.01 set karo

## Example: USD/INR — 15 Minute Chart

**Scenario:** USD/INR mein Asian session mein tight range bani hai. London open pe breakout dhundh rahe ho.

1. **Asian Session (IST 05:30–12:30, UTC 00:00–07:00)**
   - USD/INR Asian range build ho rahi hai
   - Asian High: ₹83.45
   - Asian Low: ₹83.28
   - Range = 17 paise (₹0.17)
   - Purple background Asian session dikhata hai

2. **12:30 PM IST (London Open) — Breakout!**
   - London session open hota hai, European banks active hote hain
   - USD/INR ₹83.52 pe close karta hai (Asian High ₹83.45 + 5 pip buffer = ₹83.50 ke upar)
   - Yellow background London trading window dikhata hai
   - "LDN" label dikhta hai
   - **Entry:** Long at ₹83.52

3. **Risk Management**
   - ATR(14) on 15m = ₹0.12, ATR Mult = 1.5
   - **Stop Loss:** ₹83.52 − (₹0.12 × 1.5) = ₹83.34
   - **Take Profit:** ₹83.52 + (₹0.18 × 2.0 R:R) = ₹83.88

4. **04:30 PM IST — London session mein move aa gaya**
   - Dollar strengthening pe USD/INR ₹83.82 tak gaya
   - **Take profit hit at ₹83.88**
   - **Result:** +₹0.36 per unit (+0.43%)
   - 1 lot (1,000 units) pe: **+₹360 profit**
   - 10 lots pe: **+₹3,600 profit**

**Kyun kaam kiya:** Asian session mein tight range bani thi — low volatility. London open ke baad European institutional flows ne USD/INR mein directional move diya. Clean breakout tha volume ke saath.

**Dhyan rakho:**
- RBI intervention days pe USD/INR mein strategy unreliable ho sakti hai — RBI circular / intervention news check karo.
- Asian range bahut wide ho (>30 paise) toh breakout ke chances kam hain — skip karo.
- Indian forex market mein liquidity Indian business hours (09:00–17:00 IST) mein best hoti hai.
- Fed meeting, US jobs data, ya RBI policy day pe extreme volatility — buffer zyada rakho ya skip karo.
- USD/INR ke alawa EUR/INR, GBP/INR pe bhi try kar sakte ho — lekin spread zyada hota hai.

## Notes
- Purple background = Asian session; Yellow background = London trading window.
- Teal shaded box chart pe Asian range dikhata hai.
- "LDN" labels breakout entries pe dikhte hain.
- Session times apne chart ke timezone se adjust karo.
- High London session volume wale pairs pe best kaam karta hai.

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🔴 Advanced                      ║
║  Risk Level:   High                             ║
║  Timeframe:    15m (best), 5m-30m              ║
║  Frequency:    1-2 signals/session              ║
║  Hold Time:    2-6 hours                        ║
║  Capital Need: ₹2,00,000+ (forex margin)        ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Forex/currency pairs            ├── Equity stocks
├── Trending forex environment      ├── RBI policy day
├── Tight Asian range formed        ├── Wide Asian range (>1%)
├── London session overlaps         ├── US holiday (low vol)
├── Clear session boundaries        ├── INR pairs on low vol day
└── USD/INR, EUR/INR pairs          └── Exotic currency pairs
```

## 🔗 Best Strategy Combinations
- **#15 London BO + #1 ORB** → Similar concept, use ORB logic for breakout timing
- **#15 London BO + #11 Pivot Points** → Daily pivots as targets for London breakout
- **#15 London BO + #12 Supertrend** → Supertrend direction = breakout bias

## ⚠️ Common Mistakes
1. **Session times galat set karna** → IST mein Asian = 4:00-12:30, London = 12:30-21:00
2. **RBI policy day pe trade** → RBI announcement se INR volatile — session irrelevant
3. **Asian range too wide trade karna** → Tight Asian range (< 0.5%) = better breakout
4. **USD/INR mein dollar index ignore** → DXY movement INR ko directly affect karta hai
5. **Overnight position hold karna** → Forex session strategy hai — session end pe exit

## 💡 Pro Tips
- USD/INR best pair for London Breakout — good liquidity + clear session impact
- Asian range 12:30-2:30 PM IST (Indian time) mein check karo
- DXY (Dollar Index) direction = USD/INR ka broad direction — daily check karo
- RBI intervention rumours mein INR pairs mein extra caution rakho
- EUR/INR less liquid — USD/INR se start karo, then expand
