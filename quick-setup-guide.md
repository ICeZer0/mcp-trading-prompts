# Quick Setup Guide
**Get MCP Trading Working in 15 Minutes**

This guide gets you from zero to trading with any MCP client (Claude Desktop, Cursor, etc.). Once setup is complete, return to **[trading-prompts.md](trading-prompts.md)** for the 15 trading prompts.

---

## ⚡ Express Setup (Step-by-Step)

### Step 1: Get Alpaca Account & API Keys
1. Sign up at [alpaca.markets](https://alpaca.markets)
2. Go to Account → API Keys
3. Create Paper Trading API key
4. **Save these securely:**
   - API Key ID
   - API Secret Key

### Step 2: Install Prerequisites
```bash
# Install uv package manager
curl -LsSf https://astral.sh/uv/install.sh | sh

# Verify installation
uv --version
```

### Step 3: Clone & Setup Repository
```bash
# Clone repository
git clone https://github.com/Embedded-Nature/invest-pilot.git
cd invest-pilot

# Setup virtual environment
uv venv
source .venv/bin/activate

# Install dependencies  
uv pip install -e .
```

### Step 4: Configure Environment
```bash
# Create .env file (replace with your actual keys)
cat > .env << EOF
ALPACA_API_KEY="your_paper_api_key_id"
ALPACA_SECRET_KEY="your_paper_api_secret_key"
ALPACA_PAPER="true"
LOG_LEVEL="INFO"
EOF
```

### Step 5: Test the Server
```bash
# Quick test
uv run src/main.py &

# Better test with web interface
uv run mcp dev mcp_dev_adapter.py
# Opens http://localhost:6274
```

### Step 6: Configure Your MCP Client

Choose your MCP client and follow the appropriate configuration:

#### **Claude Desktop Configuration**
**Find config file:**
- macOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
- Windows: `%APPDATA%\Claude\claude_desktop_config.json`

**Add this configuration:**
```json
{
  "mcpServers": {
    "invest-pilot": {
      "command": "/absolute/path/to/uv",
      "args": ["run", "src/main.py"],
      "cwd": "/absolute/path/to/invest-pilot",
      "env": {
        "ALPACA_API_KEY": "your_paper_api_key_id",
        "ALPACA_SECRET_KEY": "your_paper_api_secret_key",
        "ALPACA_PAPER": "true"
      }
    }
  }
}
```

#### **Cursor Configuration**
**Find config file:**
- macOS: `~/Library/Application Support/Cursor/User/globalStorage/anysphere.cursor-always-local/mcp.json`
- Windows: `%APPDATA%\Cursor\User\globalStorage\anysphere.cursor-always-local\mcp.json`

**Add this configuration:**
```json
{
  "mcpServers": {
    "invest-pilot": {
      "command": "/absolute/path/to/uv",
      "args": ["run", "--with", "requests", "--with", "requests-oauthlib", "--with", "python-dotenv", "--", "python", "src/main.py"],
      "cwd": "/absolute/path/to/invest-pilot",
      "env": {
        "ALPACA_API_KEY": "your_paper_api_key_id",
        "ALPACA_SECRET_KEY": "your_paper_api_secret_key",
        "ALPACA_PAPER": "true"
      }
    }
  }
}
```

#### **Other MCP Clients**
For other MCP-compatible clients, use the server startup command:
```bash
uv run src/main.py
```

**Important:** Replace `/absolute/path/to/` with your actual paths.

### Step 7: Restart & Test
1. Quit your MCP client completely
2. Restart the application
3. Test: "Can you ping the Alpaca server?"

---

## 🆘 Quick Troubleshooting

**"Failed to spawn" error?**
- Use absolute paths in config
- Check `which uv` and use that path

**Module import errors?**
- Run `uv pip install -e .` in invest-pilot directory
- Make sure virtual environment is activated

**Authentication failures?**
- Double-check API keys in .env file
- Ensure `ALPACA_PAPER="true"` is set

**Server won't start?**
- Check for port conflicts: `lsof -i :6274`
- Run manually first: `uv run src/main.py`

**Cursor-specific issues?**
- Use full `uv run --with` command in configuration
- Check MCP logs in Cursor settings
- Ensure folder names don't have spaces or special characters

---

## ✅ Success Checklist

- [ ] Alpaca account created with paper trading API keys
- [ ] `uv` package manager installed and working
- [ ] invest-pilot repository cloned and dependencies installed
- [ ] `.env` file created with your API keys
- [ ] Server starts without errors
- [ ] MCP client config updated with absolute paths
- [ ] MCP client restarted
- [ ] Test prompt works: "Can you ping the Alpaca server?"

---

## 🎯 First Test Prompts

Once setup is complete, try these:

**Basic connectivity:**
```
Can you ping the Alpaca server?
```

**Account check:**
```
Show me my account information and current buying power.
```

**Market data:**
```
Get the latest quote for AAPL.
```

**Paper trading safety:**
```
Confirm I'm in paper trading mode and show me my paper account balance.
```

---

## 📞 Get Help

- **Discord**: [Join our MCP Trading channel](https://discord.gg/embedded-nature)
- **Email**: isaac@embeddednature.com
- **Docs**: Full troubleshooting in main bonus pack

**Built by Embedded Nature for the MCP community** 