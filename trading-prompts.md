# The 15 Trading Prompts
**Natural Language Commands for AI-Powered Trading**

These prompts work with the invest-pilot MCP server to execute trades, analyze markets, and manage portfolios through any MCP client (Claude Desktop, Cursor, or other MCP-compatible tools). Each prompt includes validation steps and safety checks.

**Prerequisites**: Complete setup using **[quick-setup-guide.md](quick-setup-guide.md)** first.

---

## 🚀 Quick Start

### Prerequisites
- Claude Desktop account
- Alpaca trading account (paper trading recommended)
- 15 minutes for setup

### What These Prompts Enable
- **Market Analysis**: Real-time quotes, historical data, technical indicators
- **Order Management**: Market, limit, stop-loss, and bracket orders
- **Portfolio Monitoring**: Account balances, positions, P&L tracking
- **Risk Management**: Automated profit-taking, position sizing
- **Advanced Strategies**: OCO orders, trailing stops, bracket trades

---

## 📋 The 15 Trading Prompts

### 🔍 **Category 1: Market Research & Analysis**

#### **Prompt 1: Daily Market Check**
```
Get the latest quote for [SYMBOL] and show me:
- Current price and daily change
- Today's high/low range
- Volume compared to average
- Any significant price movements

Then analyze if this looks like a good entry opportunity based on the data.
```

**Use Case**: Morning market routine, screening opportunities
**Example**: "Get the latest quote for AAPL and show me..."

---

#### **Prompt 2: Technical Analysis Setup**
```
For [SYMBOL], get the last 20 days of price history and analyze:
- Current price trend (bullish/bearish)
- Support and resistance levels
- Recent volume patterns
- Any notable price breakouts or breakdowns

Provide a technical summary with entry and exit suggestions.
```

**Use Case**: Before entering any position
**Example**: "For TSLA, get the last 20 days of price history..."

---

#### **Prompt 3: Multi-Stock Comparison**
```
Compare the latest quotes for [SYMBOL1], [SYMBOL2], and [SYMBOL3]:
- Which is showing the strongest momentum today?
- Which has the best risk-reward setup?
- Which would you prioritize for a swing trade?

Give me your analysis and ranking.
```

**Use Case**: Sector analysis, choosing between similar stocks
**Example**: "Compare the latest quotes for MSFT, GOOGL, and AMZN..."

---

### 💰 **Category 2: Basic Trading Operations**

#### **Prompt 4: Smart Market Entry**
```
I want to buy [QUANTITY] shares of [SYMBOL]. First:
1. Get the current quote and assess the entry timing
2. Check my account balance to ensure I have sufficient buying power
3. If conditions look good, place a market order
4. Confirm the order and show me my updated position

Walk me through each step.
```

**Use Case**: Careful market entries with validation
**Example**: "I want to buy 10 shares of NVDA..."

---

#### **Prompt 5: Limit Order with Logic**
```
Place a limit order to buy [QUANTITY] shares of [SYMBOL] at [PRICE], but first:
- Verify the limit price is reasonable compared to current market price
- Check that my buying power is sufficient
- Explain why this might be a good entry point
- Set the order and track it

Keep me updated on the order status.
```

**Use Case**: Patient entries at specific price levels
**Example**: "Place a limit order to buy 25 shares of AMD at $140..."

---

#### **Prompt 6: Quick Exit Strategy**
```
I need to sell my [SYMBOL] position. First show me:
- Current position size and average cost
- Current market price and P&L
- Market conditions (is this a good time to sell?)

Then execute a market sell order and confirm the sale.
```

**Use Case**: Quick exits when needed
**Example**: "I need to sell my AAPL position..."

---

### 📊 **Category 3: Portfolio Management**

#### **Prompt 7: Portfolio Health Check**
```
Give me a complete portfolio analysis:
- Show all current positions with P&L
- Calculate my total portfolio value and daily change
- Identify my best and worst performing positions
- Show my current buying power and cash balance
- Suggest any rebalancing opportunities

Provide an executive summary with key insights.
```

**Use Case**: Weekly portfolio reviews
**Example**: Perfect for Sunday planning sessions

---

#### **Prompt 8: Position Sizing Calculator**
```
I want to buy [SYMBOL] with proper position sizing. Help me:
1. Check my current account balance
2. Calculate 2% risk per trade based on my portfolio
3. Get the current price of [SYMBOL]
4. Determine appropriate share quantity for 2% risk
5. Place the order if everything looks good

Show your calculations and reasoning.
```

**Use Case**: Disciplined risk management
**Example**: "I want to buy TSLA with proper position sizing..."

---

#### **Prompt 9: Profit-Taking Assistant**
```
Review my [SYMBOL] position and if it's up more than [THRESHOLD]%, 
sell [PERCENTAGE]% of the position to lock in profits.

First show me:
- Current position details and unrealized P&L
- Whether it meets the profit-taking criteria
- How many shares to sell for partial profit

Execute if appropriate and explain your decision.
```

**Use Case**: Systematic profit-taking
**Example**: "Review my NVDA position and if it's up more than 15%, sell 50%..."

---

### ⚡ **Category 4: Advanced Trading Strategies**

#### **Prompt 10: Bracket Order Setup**
```
Set up a bracket order for [SYMBOL]:
- Entry: Buy [QUANTITY] shares at market price
- Take Profit: [PROFIT_TARGET]% above entry
- Stop Loss: [STOP_LOSS]% below entry

First get the current price, calculate exact profit and stop levels,
then place the bracket order. Explain the risk-reward ratio.
```

**Use Case**: Complete position management in one order
**Example**: "Set up a bracket order for AAPL: Buy 20 shares, profit at 8%, stop at 4%"

---

#### **Prompt 11: Trailing Stop Strategy**
```
For my existing [SYMBOL] position, set up a trailing stop:
- Trail by [TRAIL_PERCENT]% from the highest price
- Explain how this protects my profits
- Show current position details before setting

Monitor and update me if the stop adjusts.
```

**Use Case**: Protecting profits while staying in trends
**Example**: "For my TSLA position, set up a trailing stop with 5% trail"

---

#### **Prompt 12: OCO (One-Cancels-Other) Order**
```
I have [QUANTITY] shares of [SYMBOL]. Set up an OCO order:
- Profit target at [HIGH_PRICE] (limit sell)
- Stop loss at [LOW_PRICE] (stop sell)

Show me the current position, explain the OCO strategy,
and place both orders so one cancels the other.
```

**Use Case**: Set and forget position management
**Example**: "I have 50 shares of AMD. Set up OCO: profit at $160, stop at $135"

---

### 🛡️ **Category 5: Risk Management & Monitoring**

#### **Prompt 13: Daily Risk Assessment**
```
Perform my daily risk check:
1. Show all open positions and their current P&L
2. Calculate my total portfolio exposure
3. Identify any positions down more than 5%
4. Check for any orders that need attention
5. Flag any positions that should be reviewed

Provide a risk summary with action items.
```

**Use Case**: Daily trading routine, risk monitoring
**Example**: Perfect for end-of-day reviews

---

#### **Prompt 14: Stop Loss Implementation**
```
For my [SYMBOL] position, implement a stop loss:
1. Show current position size and average cost
2. Calculate stop loss price at [PERCENTAGE]% below average cost
3. Place a stop-limit order to protect the position
4. Explain the protection this provides

Confirm the stop loss is in place.
```

**Use Case**: Adding protection to existing positions
**Example**: "For my AAPL position, implement a 8% stop loss"

---

#### **Prompt 15: Emergency Portfolio Exit**
```
Emergency situation - I need to close all positions safely:
1. Show me all current positions and their values
2. Cancel any pending orders
3. Close all positions using market orders
4. Confirm all exits and show final cash balance
5. Provide a summary of realized P&L

Execute this carefully and confirm each step.
```

**Use Case**: Market crash protection, rapid exit
**Example**: Use sparingly, in genuine emergencies only

---

## 🔧 Setup

**New to MCP trading?** Follow the **[quick-setup-guide.md](quick-setup-guide.md)** for step-by-step installation.

**Having issues?** Check the **[troubleshooting-guide.md](troubleshooting-guide.md)** for solutions.

**Ready to trade?** Use the prompts below with your MCP client.



---

## 💡 Advanced Workflow Examples

### Example 1: Morning Trading Routine

**Combined prompt:**
```
Run my morning trading routine:

1. Show my current portfolio status and overnight P&L
2. Get quotes for my watchlist: AAPL, TSLA, NVDA, AMD, MSFT
3. Identify any positions that hit stop losses overnight
4. Check for any pending orders that need attention
5. Highlight any stocks showing unusual volume or price movement

Provide a summary with today's action items.
```

### Example 2: Swing Trading Strategy

**Combined prompt:**
```
Execute my swing trading analysis for [SYMBOL]:

1. Get 30 days of price history
2. Identify current trend direction
3. Calculate potential entry price (near support)
4. Set profit target at 12% gain
5. Set stop loss at 6% loss
6. If setup looks good, place bracket order

Walk me through your analysis and reasoning.
```

### Example 3: Portfolio Rebalancing

**Combined prompt:**
```
Help me rebalance my portfolio:

1. Show all current positions with % allocation
2. Identify positions over 10% of portfolio
3. Suggest reducing oversized positions
4. Calculate proceeds from sales
5. Recommend diversification into underweight sectors

Provide a step-by-step rebalancing plan.
```

---

## 🤝 Join Our Community

### Connect with Other MCP Traders

**Embedded Nature Community Hub:**
- 🗣️ **Discord**: [Join our MCP Trading Channel](http://agentic.embeddednature.com/start)
- 📧 **Newsletter**: Weekly MCP insights and new prompts
- 🐦 **Twitter**: [@EmbeddedNature](https://twitter.com/embeddednature) - Follow for updates
- 💼 **LinkedIn**: Professional MCP discussions and case studies

### Exclusive Member Benefits

**As an MCP Bonus Pack member, you get:**
- ✅ **Priority support** for technical issues
- ✅ **New prompt releases** delivered monthly
- ✅ **Advanced strategy workshops** (live training)
- ✅ **Direct access** to the MCP development team
- ✅ **Community challenges** with prizes
- ✅ **Beta access** to new MCP servers

### Share Your Success

**We'd love to see your results!**
- Share successful trades using our prompts
- Post screenshots of your MCP workflows
- Contribute new prompt ideas
- Help other community members

**Tag us on social:**
- `#MCPTrading`, `#AgenticEra`
- `#EmbeddedNature`
- `@EmbeddedNature`

### Get Help & Support

**Need assistance?**
1. **Community Discord**: Fastest response from community experts
2. **Technical Issues**: isaac@embeddednature.com
3. **Strategy Questions**: Share in our Discord trading channel
4. **Feedback & Ideas**: We're always improving based on user input

### Monthly Community Events

**Join our regular events:**
- 📅 **First Friday**: Monthly MCP strategy review
- 🎯 **Trading Challenges**: Put your prompts to the test
- 📚 **Tutorial Thursdays**: Learn advanced MCP techniques
- 💬 **Q&A Sessions**: Direct access to developers

---

## 📈 What's Next?

### Advanced MCP Servers Coming Soon:
- **Options Trading MCP**: Complex options strategies
- **Crypto Trading MCP**: Multi-exchange crypto automation
- **Portfolio Analytics MCP**: Advanced risk metrics
- **News & Sentiment MCP**: AI-powered market intelligence

### Stay Updated:
- Follow [@EmbeddedNature](https://twitter.com/embeddednature)

- Subscribe to our [newsletter](http://agentic.embeddednature.com/start)

---

**Built by traders, for traders. Welcome to the future of AI-powered investing.**

*© 2025 Embedded Nature LLC. This bonus pack is provided as educational material. Trading involves risk of loss. Always practice proper risk management.*