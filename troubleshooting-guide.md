# 🚨 Troubleshooting Guide
**Common Issues and Solutions for MCP Trading Setup**

Having trouble getting your MCP trading setup working? This guide covers the most common issues and their solutions.

---

## Common Issue 1: "Failed to spawn" Error

**Symptoms:**
```
error: Failed to spawn: `invest-pilot`
Caused by: No such file or directory (os error 2)
```

**Solutions:**

1. **Use absolute paths** (most common fix):
```json
{
  "command": "/Users/yourname/.local/bin/uv",
  "cwd": "/Users/yourname/path/to/invest-pilot"
}
```

2. **Check uv installation**:
```bash
which uv
# Use this path in your config
```

3. **Verify file permissions**:
```bash
chmod +x /path/to/uv
```

---

## Common Issue 2: Module Import Errors

**Symptoms:**
```
ModuleNotFoundError: No module named 'mcp'
```

**Solutions:**

1. **Reinstall dependencies**:
```bash
cd invest-pilot
source .venv/bin/activate
uv pip install -e .
```

2. **Verify installation**:
```bash
uv pip list | grep -E "fastmcp|alpaca-py"
```

---

## Common Issue 3: Authentication Failures

**Symptoms:**
```
Error: Invalid API credentials
```

**Solutions:**

1. **Verify API keys** in your .env file
2. **Check paper trading mode**:
```bash
export ALPACA_PAPER="true"
```

3. **Test credentials directly**:
```bash
# In Python
from alpaca.trading.client import TradingClient
client = TradingClient('your_key', 'your_secret', paper=True)
print(client.get_account())
```

---

## Common Issue 4: Server Won't Start

**Symptoms:**
- No server response
- Connection timeouts

**Solutions:**

1. **Check port conflicts**:
```bash
lsof -i :6274
# Kill any competing processes
```

2. **Run server manually first**:
```bash
cd invest-pilot
uv run src/main.py
# Look for error messages
```

3. **Check logs**:
```bash
# Claude Desktop logs
tail -f ~/.claude/logs/mcp-*.log

# Cursor logs (macOS)
tail -f ~/Library/Application\ Support/Cursor/logs/*/window*/exthost/anysphere.cursor-always-local/Cursor\ MCP.log
```

---

## Common Issue 5: Tool Calls Failing

**Symptoms:**
- "Tool not found" errors
- Timeout errors

**Solutions:**

1. **Restart your MCP client** completely
2. **Verify server connection**:
```bash
uv run mcp dev mcp_dev_adapter.py
# Test tools in web interface
```

3. **Check environment variables** are loaded correctly

---

## Cursor-Specific Issues

### Issue: MCP Server Won't Connect in Cursor

**Symptoms:**
- "Failed to connect to MCP server" in Cursor
- Tools not appearing in chat

**Solutions:**

1. **Use full uv command with dependencies**:
```json
{
  "command": "/absolute/path/to/uv",
  "args": ["run", "--with", "requests", "--with", "requests-oauthlib", "--with", "python-dotenv", "--", "python", "src/main.py"]
}
```

2. **Check folder naming**:
   - Avoid spaces in folder names: `invest-pilot` not `invest pilot`
   - Avoid brackets: `trading-bot` not `trading-bot[v2]`

3. **Verify MCP config location**:
```bash
# macOS
ls ~/Library/Application\ Support/Cursor/User/globalStorage/anysphere.cursor-always-local/mcp.json

# Windows
dir %APPDATA%\Cursor\User\globalStorage\anysphere.cursor-always-local\mcp.json
```

### Issue: Cursor MCP Logs Show Import Errors

**Symptoms:**
```
ImportError: No module named 'alpaca'
```

**Solutions:**

1. **Use uv with explicit dependencies**:
```json
{
  "args": ["run", "--with", "alpaca-py", "--with", "fastmcp", "--", "python", "src/main.py"]
}
```

2. **Test dependencies manually**:
```bash
uv run --with alpaca-py --with fastmcp python -c "import alpaca; print('Dependencies OK')"
```

### Issue: Cursor Can't Find uv Command

**Solutions:**

1. **Find uv path**:
```bash
which uv
# Use full path like /Users/yourname/.local/bin/uv
```

2. **Alternative: Use system Python with full path**:
```json
{
  "command": "/usr/bin/python3",
  "args": ["-m", "uv", "run", "src/main.py"],
  "cwd": "/absolute/path/to/invest-pilot"
}
```

---

## Emergency Reset Procedure

If everything is broken:

```bash
# 1. Stop all processes
pkill -f "invest-pilot"
pkill -f "Claude"
pkill -f "Cursor"

# 2. Clean reinstall
cd invest-pilot
rm -rf .venv
uv venv
source .venv/bin/activate
uv pip install -e .

# 3. Test manually
uv run src/main.py

# 4. Restart your MCP client
# 5. Test with simple prompt: "Can you ping the server?"
```

---

## 🛡️ Safety & Risk Management

### Before You Start Trading

**⚠️ Critical Safety Rules:**

1. **Start with Paper Trading**: Always use `ALPACA_PAPER="true"`
2. **Never risk more than 2%** per trade of your portfolio
3. **Always set stop losses** before entering positions
4. **Review every AI suggestion** before executing
5. **Keep a trading journal** of all decisions

### Recommended Safety Prompts

**Before any trade:**
```
Before executing this trade, show me:
- My current account balance
- Position size as % of portfolio
- Risk-reward ratio of this trade
- How this fits my overall strategy
```

**Daily risk check:**
```
Show me my current risk exposure:
- Total portfolio value
- Largest position by %
- Any positions without stop losses
- Overall portfolio beta/volatility
```

### Paper Trading Setup

**Verify paper trading mode:**
```bash
# In your .env file
ALPACA_PAPER="true"

# Verify in Claude
ping()
# Should show paper trading environment
```

**Benefits of paper trading:**
- Learn the system without risk
- Test strategies with real market data
- Build confidence before real money
- Perfect your prompt techniques

---

## 📞 Get Help

**Still having issues?**

1. **Community Discord**: [Join our MCP Trading channel](http://agentic.embeddednature.com/start)
2. **Technical Issues**: isaac@embeddednature.com
3. **GitHub Issues**: [invest-pilot repository](https://github.com/Embedded-Nature/invest-pilot/issues)

**When asking for help, include:**
- Your operating system
- Error messages (full text)
- Steps you've already tried
- Your Claude Desktop config (without API keys)

---

**© 2025 Embedded Nature - Built for the MCP Community** 