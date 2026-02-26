# Lesson 1: Setup & First Agent

**Goal:** Get OpenClaw running and build your first working agent  
**Time:** 30-45 minutes  
**Prerequisites:** None (start here!)

---

## What You'll Build

By the end of this lesson, you'll have:
- ✅ OpenClaw installed and running
- ✅ Connected to Telegram/Slack/WhatsApp
- ✅ Your first agent: Daily briefing reminder
- ✅ Sent your first commands

---

## Part 1: Installation (15 min)

### Requirements

- **Computer:** Mac, Linux, or Raspberry Pi
- **Node.js:** v18 or higher
- **API Key:** Anthropic (Claude) or OpenAI (GPT)

### Quick Install

```bash
# Clone the repo
git clone https://github.com/openclaw/openclaw.git
cd openclaw

# Install dependencies
npm install

# Run setup wizard
npm run setup
```

The setup wizard will ask you:
1. **API provider** — Choose Anthropic (recommended) or OpenAI
2. **API key** — Paste your key from the provider's dashboard
3. **Messaging platform** — Telegram, Slack, or WhatsApp

### Getting API Keys

**Anthropic (Recommended):**
1. Go to https://console.anthropic.com
2. Sign up / log in
3. Create API key
4. Copy it

**OpenAI (Alternative):**
1. Go to https://platform.openai.com
2. Sign up / log in
3. API Keys → Create new
4. Copy it

---

## Part 2: Connect Messaging (15 min)

### Option A: Telegram (Easiest)

1. Open Telegram and message **@BotFather**
2. Send `/newbot`
3. Choose a name: "My OpenClaw Bot"
4. Choose a username: "myopenclawbot" (must end in "bot")
5. Copy the API token
6. Add it to OpenClaw config

```bash
# In your OpenClaw folder
nano config.json

# Add your token:
{
  "telegram": {
    "token": "YOUR_TOKEN_HERE"
  }
}
```

7. Start OpenClaw:

```bash
npm start
```

8. Find your bot on Telegram and send: `/start`

### Option B: Slack

1. Go to https://api.slack.com/apps
2. Create New App → From scratch
3. Name it "OpenClaw"
4. Choose your workspace
5. OAuth & Permissions → Add Bot Token Scopes:
   - `chat:write`
   - `im:read`
   - `im:write`
6. Install to Workspace
7. Copy Bot User OAuth Token
8. Add to OpenClaw config (similar to Telegram)

### Option C: WhatsApp

1. OpenClaw will show a QR code
2. Open WhatsApp on your phone
3. Settings → Linked Devices → Link a Device
4. Scan the QR code
5. Your agent is now on WhatsApp

---

## Part 3: Your First Agent (15 min)

### Build a Daily Briefing Agent

This agent will send you a reminder every morning at 8 AM.

**Tell your agent:**

> "Create a daily briefing agent that runs every morning at 8 AM. It should review my calendar, tasks, and send me a brief summary covering:
> 1. Top 3 priorities for today
> 2. Any meetings that need preparation
> 3. Follow-ups I might be missing
> 
> Keep it short, actionable, and formatted as bullets. Don't delete anything."

Your agent will:
1. Create a cron job for 8 AM daily
2. Set up the briefing format
3. Configure delivery to your messaging app
4. Confirm it's scheduled

### Test It Now

Don't want to wait until tomorrow? Test immediately:

> "Run the daily briefing agent now (skip the schedule)"

Your agent will execute immediately and you'll see the output.

---

## Part 4: Understanding What Just Happened

### What Did You Actually Build?

You created an **isolated session agent** that:
- Runs on a schedule (cron job)
- Executes independently (doesn't need you online)
- Delivers results to your messaging app
- Remembers context across runs

### The Files Created

Your agent created several files:

```
workspace/
├── agents/
│   └── daily-briefing/
│       ├── SOUL.md          ← Agent's identity
│       └── SKILL.md         ← What it does
└── cron-jobs.json           ← Schedule config
```

**Try this:** Ask your agent to show you these files:

> "Show me agents/daily-briefing/SOUL.md"

---

## Part 5: Send Your First Commands

Now that everything is running, try these commands:

### Basic Commands

**Check status:**
> "What's my session status?"

**See scheduled jobs:**
> "List my cron jobs"

**Ask about the weather:**
> "What's the weather today?"

**Set a reminder:**
> "Remind me in 1 hour to check email"

### Understanding Responses

Your agent responds in your messaging app. Responses are:
- Conversational (not robotic)
- Actionable (with clear next steps)
- Contextual (remembers previous messages)

---

## ✅ Lesson 1 Complete!

You now have:
- ✅ OpenClaw installed and running
- ✅ Connected to messaging
- ✅ Your first scheduled agent (daily briefing)
- ✅ Understanding of basic commands

---

## 🎯 Next Steps

**Optional practice:**
1. Create a different briefing (weekly instead of daily)
2. Add custom sections (e.g., "Check unread emails")
3. Try changing the time (9 AM instead of 8 AM)

**When ready, move to Lesson 2:**
> "Read lessons/02-file-operations.md and start lesson 2"

---

## 🆘 Troubleshooting

**Agent not responding?**
- Check that `npm start` is running
- Verify API key is correct
- Ensure messaging app is connected

**Cron job not running?**
- Check timezone settings
- Verify cron syntax
- Test with immediate execution first

**Commands not working?**
- Make sure you're messaging the right bot
- Try `/start` to initialize
- Check logs with `npm run logs`

---

**Questions?** Ask your agent to explain anything you don't understand!
