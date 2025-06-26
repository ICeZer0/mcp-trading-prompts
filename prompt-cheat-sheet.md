# Prompt Cheat Sheet
**Quick Copy-Paste Reference for All 15 Trading Prompts**

This is your quick reference sheet. For detailed explanations and context, see **[trading-prompts.md](trading-prompts.md)**.

---

## 🔍 Market Research & Analysis

### 1. Daily Market Check
```
Get the latest quote for [SYMBOL] and show me:
- Current price and daily change
- Today's high/low range
- Volume compared to average
- Any significant price movements

Then analyze if this looks like a good entry opportunity based on the data.
```

### 2. Technical Analysis Setup
```
For [SYMBOL], get the last 20 days of price history and analyze:
- Current price trend (bullish/bearish)
- Support and resistance levels
- Recent volume patterns
- Any notable price breakouts or breakdowns

Provide a technical summary with entry and exit suggestions.
```

### 3. Multi-Stock Comparison
```
Compare the latest quotes for [SYMBOL1], [SYMBOL2], and [SYMBOL3]:
- Which is showing the strongest momentum today?
- Which has the best risk-reward setup?
- Which would you prioritize for a swing trade?

Give me your analysis and ranking.
```

---

## 💰 Basic Trading Operations

### 4. Smart Market Entry
```
I want to buy [QUANTITY] shares of [SYMBOL]. First:
1. Get the current quote and assess the entry timing
2. Check my account balance to ensure I have sufficient buying power
3. If conditions look good, place a market order
4. Confirm the order and show me my updated position

Walk me through each step.
```

### 5. Limit Order with Logic
```
Place a limit order to buy [QUANTITY] shares of [SYMBOL] at [PRICE], but first:
- Verify the limit price is reasonable compared to current market price
- Check that my buying power is sufficient
- Explain why this might be a good entry point
- Set the order and track it

Keep me updated on the order status.
```

### 6. Quick Exit Strategy
```
I need to sell my [SYMBOL] position. First show me:
- Current position size and average cost
- Current market price and P&L
- Market conditions (is this a good time to sell?)

Then execute a market sell order and confirm the sale.
```

---

## 📊 Portfolio Management

### 7. Portfolio Health Check
```
Give me a complete portfolio analysis:
- Show all current positions with P&L
- Calculate my total portfolio value and daily change
- Identify my best and worst performing positions
- Show my current buying power and cash balance
- Suggest any rebalancing opportunities

Provide an executive summary with key insights.
```

### 8. Position Sizing Calculator
```
I want to buy [SYMBOL] with proper position sizing. Help me:
1. Check my current account balance
2. Calculate 2% risk per trade based on my portfolio
3. Get the current price of [SYMBOL]
4. Determine appropriate share quantity for 2% risk
5. Place the order if everything looks good

Show your calculations and reasoning.
```

### 9. Profit-Taking Assistant
```
Review my [SYMBOL] position and if it's up more than [THRESHOLD]%, 
sell [PERCENTAGE]% of the position to lock in profits.

First show me:
- Current position details and unrealized P&L
- Whether it meets the profit-taking criteria
- How many shares to sell for partial profit

Execute if appropriate and explain your decision.
```

---

## ⚡ Advanced Trading Strategies

### 10. Bracket Order Setup
```
Set up a bracket order for [SYMBOL]:
- Entry: Buy [QUANTITY] shares at market price
- Take Profit: [PROFIT_TARGET]% above entry
- Stop Loss: [STOP_LOSS]% below entry

First get the current price, calculate exact profit and stop levels,
then place the bracket order. Explain the risk-reward ratio.
```

### 11. Trailing Stop Strategy
```
For my existing [SYMBOL] position, set up a trailing stop:
- Trail by [TRAIL_PERCENT]% from the highest price
- Explain how this protects my profits
- Show current position details before setting

Monitor and update me if the stop adjusts.
```

### 12. OCO (One-Cancels-Other) Order
```
I have [QUANTITY] shares of [SYMBOL]. Set up an OCO order:
- Profit target at [HIGH_PRICE] (limit sell)
- Stop loss at [LOW_PRICE] (stop sell)

Show me the current position, explain the OCO strategy,
and place both orders so one cancels the other.
```

---

## 🛡️ Risk Management & Monitoring

### 13. Daily Risk Assessment
```
Perform my daily risk check:
1. Show all open positions and their current P&L
2. Calculate my total portfolio exposure
3. Identify any positions down more than 5%
4. Check for any orders that need attention
5. Flag any positions that should be reviewed

Provide a risk summary with action items.
```

### 14. Stop Loss Implementation
```
For my [SYMBOL] position, implement a stop loss:
1. Show current position size and average cost
2. Calculate stop loss price at [PERCENTAGE]% below average cost
3. Place a stop-limit order to protect the position
4. Explain the protection this provides

Confirm the stop loss is in place.
```

### 15. Emergency Portfolio Exit
```
Emergency situation - I need to close all positions safely:
1. Show me all current positions and their values
2. Cancel any pending orders
3. Close all positions using market orders
4. Confirm all exits and show final cash balance
5. Provide a summary of realized P&L

Execute this carefully and confirm each step.
```

---

## 🎯 Sample Replacements

Replace the bracketed placeholders with your actual values:

- `[SYMBOL]` → AAPL, TSLA, NVDA, etc.
- `[QUANTITY]` → 10, 25, 100, etc.
- `[PRICE]` → 150.00, 220.50, etc.
- `[THRESHOLD]` → 15, 20, 25 (for 15%, 20%, 25%)
- `[PERCENTAGE]` → 25, 50, 75 (for 25%, 50%, 75%)
- `[PROFIT_TARGET]` → 8, 12, 15 (for 8%, 12%, 15%)
- `[STOP_LOSS]` → 4, 6, 8 (for 4%, 6%, 8%)
- `[TRAIL_PERCENT]` → 3, 5, 7 (for 3%, 5%, 7%)
- `[HIGH_PRICE]` → 180.00, 250.00, etc.
- `[LOW_PRICE]` → 140.00, 200.00, etc.

---

## 💡 Pro Tips

1. **Always start with paper trading** until you're comfortable
2. **Test connectivity first**: "Can you ping the Alpaca server?"
3. **Check your account balance** before placing orders
4. **Use stop losses** for risk management
5. **Keep position sizes reasonable** (2-5% of portfolio max)
6. **Review AI suggestions** before executing trades

---

## 🆘 Quick Help

**Can't connect?** Check your Claude Desktop config file paths
**Orders failing?** Verify you're in paper trading mode first
**Need help?** [Join our Discord](http://agentic.embeddednature.com/start)

**© 2025 Embedded Nature - Built for the MCP Community** 