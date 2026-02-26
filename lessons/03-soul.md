# Lesson 3: Building Your Bot's SOUL

**Goal:** Understand and customize your agent's identity  
**Time:** 30-40 minutes  
**Prerequisites:** Lesson 1 & 2 complete

---

## What You'll Learn

By the end of this lesson, you'll understand:
- ✅ What SOUL.md is and why it matters
- ✅ The difference between SOUL, SKILL, USER, and TOOLS
- ✅ How to view and edit your agent's files
- ✅ How to give your agent a personality

---

## Part 1: The File Structure (10 min)

### The Core Files

OpenClaw agents have four core identity files:

```
workspace/
├── SOUL.md          ← WHO the agent is (personality, voice, values)
├── USER.md          ← WHO you are (preferences, context, goals)
├── TOOLS.md         ← WHERE things are (local setup, environment)
├── MEMORY.md        ← WHAT it remembers (long-term knowledge)
```

### The Key Principle

**SOUL = WHO** (identity, personality)  
**SKILL = HOW** (workflow, tools, outputs)  
**USER = FOR WHOM** (your preferences)  
**TOOLS = WHERE** (your local environment)

---

## Part 2: Understanding SOUL.md (15 min)

### What Is SOUL.md?

SOUL.md defines **WHO your agent is**. Not what it does — WHO it is.

Think of it as:
- Personality (formal vs casual, serious vs playful)
- Values (what it prioritizes)
- Voice (how it communicates)
- Boundaries (what it will/won't do)

### View Your Current SOUL

Ask your agent:

> "Show me SOUL.md"

You'll see something like:

```markdown
# SOUL.md - Who You Are

## Core Truths

**Be genuinely helpful, not performatively helpful.**
Skip the "Great question!" and just help.

**Have opinions.** You're allowed to disagree, prefer things,
find stuff amusing or boring.

**Be resourceful before asking.** Try to figure it out first.

## Boundaries

- Private things stay private. Period.
- When in doubt, ask before acting externally.
- You're not the user's voice — be careful in group chats.
```

### Why This Matters

Without SOUL.md, your agent is generic. With it, your agent has personality, judgment, and consistency.

**Example:**

**Without SOUL:**
> "I'll be happy to help you with that! Let me get started on your request right away! 😊"

**With SOUL:**
> "On it. Give me a sec."

---

## Part 3: Customize Your Agent's Personality (15 min)

### Exercise: Define Your Ideal Assistant

Think about:
1. **Tone:** Formal or casual? Serious or playful?
2. **Proactivity:** Should it suggest things or wait for instructions?
3. **Communication:** Verbose or concise? Emoji or plain text?
4. **Boundaries:** What should it never do without asking?

### Update SOUL.md

Tell your agent:

> "Update SOUL.md to reflect my preferences:
> - Be casual and direct (no corporate speak)
> - Proactive: suggest improvements without asking
> - Concise: short answers unless I ask for detail
> - Boundary: Never send emails or messages externally without explicit approval
> - Use occasional emoji but don't overdo it"

Your agent will update SOUL.md with these preferences.

### Test the Changes

Start a new session (this reloads SOUL.md) and ask:

> "What's your personality?"

You should see your agent describe itself based on the updated SOUL.

---

## Part 4: Understanding the Other Files (10 min)

### USER.md — Who You Are

USER.md tells the agent about YOU:
- Your name, pronouns, timezone
- What you care about
- Your projects and goals
- Preferences (communication style, work hours)

**View it:**
> "Show me USER.md"

**Update it:**
> "Update USER.md — I'm Tim, Sr Director CS, new dad to Luca, working on Warren (portfolio agent) and Marc (content agent). I'm focused on revenue and building in public."

### TOOLS.md — Your Local Setup

TOOLS.md contains environment-specific details:
- Camera names and locations
- SSH hosts and aliases
- Preferred TTS voices
- Device nicknames

**Example:**

```markdown
# TOOLS.md

## SSH Hosts
- home-server → 192.168.1.100

## TTS
- Preferred voice: "Nova"
- Default speaker: Kitchen HomePod
```

This keeps your personal setup separate from shared skills.

### MEMORY.md — Long-Term Knowledge

MEMORY.md is your agent's consolidated memory:
- Significant decisions
- Lessons learned
- Important context that persists
- Project status and history

**It's read-only for this lesson** — we'll cover memory in Lesson 4.

---

## Part 5: Sub-Agent SOULs (10 min)

### Multiple Agents, Multiple Personalities

Each agent in `agents/` has its own SOUL.md.

**Example: Warren (Portfolio Agent)**

```markdown
# SOUL.md — Warren

**Mission:** Find undervalued stocks with rabid communities

**Personality:** Contrarian, data-driven, skeptical of hype

**Voice:** Direct, no-BS, cite sources

**Values:** Deep research > quick pumps
```

**Example: Marc (Content Agent)**

```markdown
# SOUL.md — Marc

**Mission:** Extract insights from work, draft content

**Personality:** Creative, witty, strategic

**Voice:** Casual but professional, Twitter-friendly

**Values:** Build in public, practical over theoretical
```

### View Sub-Agent SOULs

Ask your agent:

> "Show me agents/warren/SOUL.md"

### Why Separate SOULs Matter

Different agents should have different personalities based on their roles:
- **Portfolio agent:** Analytical, skeptical, risk-aware
- **Content agent:** Creative, engaging, audience-focused
- **CS agent:** Empathetic, proactive, customer-first

---

## ✅ Lesson 3 Complete!

You now understand:
- ✅ SOUL vs SKILL vs USER vs TOOLS
- ✅ How to customize your agent's personality
- ✅ How to view and edit identity files
- ✅ Why sub-agents have separate SOULs

---

## 🎯 Practice Exercise

**Challenge:** Create a custom sub-agent with a unique personality

> "Create a new agent called 'Scout' whose job is to monitor X (Twitter) for mentions of specific topics and alert me. Give Scout a personality: curious, fast, alert. Scout's voice should be short and punchy ('🚨 New mention: [topic]')."

Your agent will:
1. Create `agents/scout/` folder
2. Write SOUL.md with the personality
3. Write SKILL.md with the monitoring workflow
4. Set up the agent to run

---

## 🎯 Next Steps

**When ready, move to Lesson 4:**
> "Read lessons/04-memory.md and start lesson 4"

---

## 🆘 Key Takeaways

**SOUL is identity, SKILL is workflow**
- Don't mix them. SOUL = WHO, SKILL = HOW

**Be specific about personality**
- "Be helpful" is vague. "Be direct, skip filler" is actionable.

**Different roles need different SOULs**
- Portfolio agent ≠ content agent ≠ CS agent

**Test after changes**
- Start new session to reload updated SOUL

---

**Questions?** Ask your agent to explain anything you don't understand!
