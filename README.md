
Skip to content
Navigation Menu
Sign in

decolua /
devil's-router
Public

    Code
    Issues 283

    devil's-router

/README.md
author
decolua
last week
1312 lines (1012 loc) · 41.2 KB

devill's-Router Dashboard
devil's-Router - FREE AI Router & Token Saver

Never stop coding. Save 20-40% tokens with RTK + auto-fallback to FREE & cheap AI models.

Connect All AI Code Tools (Claude Code, Cursor, Antigravity, Copilot, Codex, Gemini, OpenCode, Cline, OpenClaw...) to 40+ AI Providers & 100+ Models.

npm Downloads License

decolua%2F9router | Trendshift

🚀 Quick Start • 💡 Features • 📖 Setup • 🌐 Website

🇻🇳 Tiếng Việt • 🇨🇳 中文 • 🇯🇵 日本語
🤔 Why 9Router?

Stop wasting money, tokens and hitting limits:

    ❌ Subscription quota expires unused every month
    ❌ Rate limits stop you mid-coding
    ❌ Tool outputs (git diff, grep, ls...) burn tokens fast
    ❌ Expensive APIs ($20-50/month per provider)
    ❌ Manual switching between providers

devil's-Router solves this:

    ✅ RTK Token Saver - Auto-compress tool_result content, save 20-40% tokens per request
    ✅ Maximize subscriptions - Track quota, use every bit before reset
    ✅ Auto fallback - Subscription → Cheap → Free, zero downtime
    ✅ Multi-account - Round-robin between accounts per provider
    ✅ Universal - Works with Claude Code, Codex, Cursor, Cline, any CLI tool

🔄 How It Works

┌─────────────┐
│  Your CLI   │  (Claude Code, Codex, OpenClaw, Cursor, Cline...)
│   Tool      │
└──────┬──────┘
       │ http://localhost:20128/v1
       ↓
┌─────────────────────────────────────────────┐
│           devil's-Router (Smart Router)            │
│  • RTK Token Saver (cut tool_result tokens) │
│  • Format translation (OpenAI ↔ Claude)     │
│  • Quota tracking                           │
│  • Auto token refresh                       │
└──────┬──────────────────────────────────────┘
       │
       ├─→ [Tier 1: SUBSCRIPTION] Claude Code, Codex, GitHub Copilot
       │   ↓ quota exhausted
       ├─→ [Tier 2: CHEAP] GLM ($0.6/1M), MiniMax ($0.2/1M)
       │   ↓ budget limit
       └─→ [Tier 3: FREE] Kiro, OpenCode Free, Vertex ($300 credits)

Result: Never stop coding, minimal cost + 20-40% token savings via RTK

⚡ Quick Start

1. Install globally:

npm install -g devil's-router
devil's-router

🎉 Dashboard opens at http://localhost:20128

2. Connect a FREE provider (no signup needed):

Dashboard → Providers → Connect Kiro AI (free Claude unlimited) or OpenCode Free (no auth) → Done!

3. Use in your CLI tool:

Claude Code/Codex/OpenClaw/Cursor/Cline Settings:
  Endpoint: http://localhost:20128/v1
  API Key: [copy from dashboard]
  Model: kr/claude-sonnet-4.5

That's it! Start coding with FREE AI models.

Alternative: run from source (this repository):

This repository package is private (devil's-router-app), so source/Docker execution is the expected local development path.

cp .env.example .env
npm install
PORT=20128 NEXT_PUBLIC_BASE_URL=http://localhost:20128 npm run dev

Production mode:

npm run build
PORT=20128 HOSTNAME=0.0.0.0 NEXT_PUBLIC_BASE_URL=http://localhost:20128 npm run start

Default URLs:

    Dashboard: http://localhost:20128/dashboard
    OpenAI-compatible API: http://localhost:20128/v1

Video Guides
devil's-Router Setup Tutorial
🇺🇸 English
devil's-Router + Claude Code FREE Setup
by Build AI With Hamid 	Tiết kiệm chi phí LLM với devil's-Router
🇻🇳 Tiếng Việt
Tiết kiệm chi phí LLM cho OpenClaw với devil's-Router
by Mì AI 	Claude Code FREE Forever
🇺🇸 English
Claude Code FREE Forever — Unlimited Models
by Build AI With Hamid
Claude CLI Free Setup
🇺🇸 English
Claude CLI Free Setup with devil's-Router 🚀
by CodeVerse Soban 	Cài đặt OpenClaw Free A-Z
🇻🇳 Tiếng Việt
Cài Đặt OpenClaw Free Từ A-Z + devil's-Router
by Mai Gia 	FREE OpenClaw with Claude Opus
🇺🇸 English
FREE OpenClaw + Claude Opus 4.6
by Build AI With Hamid

    🎬 Made a video about devil's-Router? Submit a Pull Request adding your video to this section — we'll merge it!

🛠️ Supported CLI Tools

devil's-Router works seamlessly with all major AI coding tools:
Claude Code
Claude-Code 	OpenClaw
OpenClaw 	Codex
Codex 	OpenCode
OpenCode 	Cursor
Cursor 	Antigravity
Antigravity
Cline
Cline 	Continue
Continue 	Droid
Droid 	Roo
Roo 	Copilot
Copilot 	Kilo Code
Kilo Code
🌐 Supported Providers
🔐 OAuth Providers
Claude Code
Claude-Code 	Antigravity
Antigravity 	Codex
Codex 	GitHub
GitHub 	Cursor
Cursor
🆓 Free Providers
Kiro
Kiro AI
Claude 4.5 + GLM-5 + MiniMax
Unlimited FREE 	OpenCode Free
OpenCode Free
No auth • Auto-fetch models
Unlimited FREE 	Vertex AI
Vertex AI
Gemini 3 Pro + GLM-5 + DeepSeek
$300 credits free

    Note: iFlow, Qwen and Gemini CLI free tiers were discontinued in 2026. Use Kiro / OpenCode Free / Vertex instead.

🔑 API Key Providers (40+)
OpenRouter
OpenRouter 	GLM
GLM 	Kimi
Kimi 	MiniMax
MiniMax 	OpenAI
OpenAI 	Anthropic
Anthropic
Gemini
Gemini 	DeepSeek
DeepSeek 	Groq
Groq 	xAI
xAI 	Mistral
Mistral 	Perplexity
Perplexity
Together
Together AI 	Fireworks
Fireworks 	Cerebras
Cerebras 	Cohere
Cohere 	NVIDIA
NVIDIA 	SiliconFlow
SiliconFlow

...and 20+ more providers including Nebius, Chutes, Hyperbolic, and custom OpenAI/Anthropic compatible endpoints
💡 Key Features
Feature 	What It Does 	Why It Matters
🚀 RTK Token Saver (RTK ⭐40K) 	Compress tool outputs (git diff, grep, ls, tree...) before sending to LLM 	Save 20-40% input tokens per request
🪨 Caveman Mode (Caveman ⭐52K) 	Inject caveman-speak prompt → LLM replies terse, technical substance preserved 	Save up to 65% output tokens
🎯 Smart 3-Tier Fallback 	Auto-route: Subscription → Cheap → Free 	Never stop coding, zero downtime
📊 Real-Time Quota Tracking 	Live token count + reset countdown 	Maximize subscription value
🔄 Format Translation 	OpenAI ↔ Claude ↔ Gemini ↔ Cursor ↔ Kiro ↔ Vertex 	Works with any CLI tool
👥 Multi-Account Support 	Multiple accounts per provider 	Load balancing + redundancy
🔄 Auto Token Refresh 	OAuth tokens refresh automatically 	No manual re-login needed
🎨 Custom Combos 	Create unlimited model combinations 	Tailor fallback to your needs
📝 Request Logging 	Debug mode with full request/response logs 	Troubleshoot issues easily
💾 Cloud Sync 	Sync config across devices 	Same setup everywhere
📊 Usage Analytics 	Track tokens, cost, trends over time 	Optimize spending
🌐 Deploy Anywhere 	Localhost, VPS, Docker, Cloudflare Workers 	Flexible deployment options
📖 Feature Details

💰 Pricing at a Glance
Tier 	Provider 	Cost 	Quota Reset 	Best For
🚀 TOKEN SAVER 	RTK (built-in) 	FREE 	Always on 	Save 20-40% tokens on EVERY request
💳 SUBSCRIPTION 	Claude Code (Pro/Max) 	$20-200/mo 	5h + weekly 	Already subscribed
	Codex (Plus/Pro) 	$20-200/mo 	5h + weekly 	OpenAI users
	GitHub Copilot 	$10-19/mo 	Monthly 	GitHub users
	Cursor IDE 	$20/mo 	Monthly 	Cursor users
💰 CHEAP 	GLM-5.1 / GLM-4.7 	$0.6/1M 	Daily 10AM 	Budget backup
	MiniMax M2.7 	$0.2/1M 	5-hour rolling 	Cheapest option
	Kimi K2.5 	$9/mo flat 	10M tokens/mo 	Predictable cost
🆓 FREE 	Kiro AI 	$0 	Unlimited 	Claude 4.5 + GLM-5 + MiniMax free
	OpenCode Free 	$0 	Unlimited 	No auth, auto-fetch models
	Vertex AI 	$300 credits 	New GCP accounts 	Gemini 3 Pro + DeepSeek + GLM-5

💡 Pro Tip: RTK + Kiro AI + OpenCode Free combo = $0 cost + 20-40% token savings!
📊 Understanding 9Router Costs & Billing

devil's-Router Billing Reality:

✅ devil's-Router software = FREE forever (open source, never charges)
✅ Dashboard "costs" = Display/tracking only (not actual bills)
✅ You pay providers directly (subscriptions or API fees)
✅ FREE providers stay FREE (iFlow, Kiro, Qwen = $0 unlimited)
❌ devil's-Router never sends invoices or charges your card

How Cost Display Works:

The dashboard shows estimated costs as if you were using paid APIs directly. This is not billing - it's a comparison tool to show your savings.

Example Scenario:

Dashboard Display:
• Total Requests: 1,662
• Total Tokens: 47M
• Display Cost: $290

Reality Check:
• Provider: iFlow (FREE unlimited)
• Actual Payment: $0.00
• What $290 Means: Amount you SAVED by using free models!

Payment Rules:

    Subscription providers (Claude Code, Codex): Pay them directly via their websites
    Cheap providers (GLM, MiniMax): Pay them directly, 9Router just routes
    FREE providers (iFlow, Kiro, Qwen): Genuinely free forever, no hidden charges
    9Router: Never charges anything, ever

🎯 Use Cases
Case 1: "I have Claude Pro subscription"

Problem: Quota expires unused, rate limits during heavy coding

Solution:

Combo: "maximize-claude"
  1. cc/claude-opus-4-7        (use subscription fully)
  2. glm/glm-5.1               (cheap backup when quota out)
  3. kr/claude-sonnet-4.5      (free emergency fallback)

Monthly cost: $20 (subscription) + ~$5 (backup) = $25 total
vs. $20 + hitting limits = frustration

Case 2: "I want zero cost"

Problem: Can't afford subscriptions, need reliable AI coding

Solution:

Combo: "free-forever"
  1. kr/claude-sonnet-4.5      (Claude 4.5 free unlimited)
  2. kr/glm-5                  (GLM-5 free via Kiro)
  3. oc/<auto>                 (OpenCode Free, no auth)

Monthly cost: $0
Quality: Production-ready models + RTK saves 20-40% tokens

Case 3: "I need 24/7 coding, no interruptions"

Problem: Deadlines, can't afford downtime

Solution:

Combo: "always-on"
  1. cc/claude-opus-4-7        (best quality)
  2. cx/gpt-5.5                (second subscription)
  3. glm/glm-5.1               (cheap, resets daily)
  4. minimax/MiniMax-M2.7      (cheapest, 5h reset)
  5. kr/claude-sonnet-4.5      (free unlimited)

Result: 5 layers of fallback = zero downtime
Monthly cost: $20-200 (subscriptions) + $10-20 (backup)

Case 4: "I want FREE AI in OpenClaw"

Problem: Need AI assistant in messaging apps (WhatsApp, Telegram, Slack...), completely free

Solution:

Combo: "openclaw-free"
  1. kr/claude-sonnet-4.5      (Claude 4.5 free)
  2. kr/glm-5                  (GLM-5 free)
  3. kr/MiniMax-M2.5           (MiniMax free)

Monthly cost: $0
Access via: WhatsApp, Telegram, Slack, Discord, iMessage, Signal...

❓ Frequently Asked Questions
📊 Why does my dashboard show high costs?

💳 Will I be charged by 9Router?

🆓 Are FREE providers really unlimited?

💰 How do I minimize my actual AI costs?

📈 What if my usage suddenly spikes?

📖 Setup Guide
🔐 Subscription Providers (Maximize Value)

💰 Cheap Providers (Backup)

🆓 FREE Providers (Recommended)

🎨 Create Combos

🔧 CLI Integration

🚀 Deployment

		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		

📊 Available Models
View all available models

🐛 Troubleshooting

"Language model did not provide messages"

    Provider quota exhausted → Check dashboard quota tracker
    Solution: Use combo fallback or switch to cheaper tier

Rate limiting

    Subscription quota out → Fallback to GLM/MiniMax
    Add combo: cc/claude-opus-4-7 → glm/glm-5.1 → kr/claude-sonnet-4.5

OAuth token expired

    Auto-refreshed by devil's-Router
    If issues persist: Dashboard → Provider → Reconnect

High costs

    Enable RTK in Dashboard → Endpoint settings (default ON, saves 20-40% tokens)
    Check usage stats in Dashboard
    Switch primary model to GLM/MiniMax
    Use free tier (Kiro, OpenCode Free, Vertex) for non-critical tasks

Dashboard opens on wrong port

    Set PORT=20128 and NEXT_PUBLIC_BASE_URL=http://localhost:20120

First login not working

    Check INITIAL_PASSWORD in .env
    If unset, fallback password is 123456

No request logs under logs/

    Set ENABLE_REQUEST_LOGS=true

🛠️ Tech Stack

    Runtime: Node.js 20+
    Framework: Next.js 16
    UI: React 19 + Tailwind CSS 4
    Database: LowDB (JSON file-based)
    Streaming: Server-Sent Events (SSE)
    Auth: OAuth 2.0 (PKCE) + JWT + API Keys

📝 API Reference
Chat Completions

POST http://localhost:20120/v1/chat/completions
Authorization: Bearer your-api-key
Content-Type: application/json

{
  "model": "cc/claude-opus-4-6",
  "messages": [
    {"role": "user", "content": "Write a function to..."}
  ],
  "stream": true
}

List Models

GET http://localhost:20128/v1/models
Authorization: Bearer your-api-key

→ Returns all models + combos in OpenAI format

📧 Support

    Website: 
    GitHub: github.com/decolua/devil's-router
    Issues: github.com/decolua/devil's-router/issues

👥 Contributors

Thanks to all contributors who helped make devil's-Router better!

Contributors
📊 Star Chart

Star Chart
🔀 Forks

OmniRoute — A full-featured TypeScript fork of devil's-Router. Adds 36+ providers, 4-tier auto-fallback, multi-modal APIs (images, embeddings, audio, TTS), circuit breaker, semantic cache, LLM evaluations, and a polished dashboard. 368+ unit tests. Available via npm and Docker.
🙏 Acknowledgments

Built on the shoulders of giants:

    CLIProxyAPI — original Go implementation that inspired this JavaScript port.
    RTK Stars — Rust token-saver. 9Router ports its compression pipeline to JS → −20-40% input tokens on every request.
    Caveman Stars by @JuliusBrussee — viral "why use many token when few token do trick". devil's-Router adapts its prompt → −65% output tokens.

Huge thanks to these authors — without their work, devil's-1Router's token-saving features wouldn't exist. ⭐ them on GitHub!
📄 License

MIT License - see LICENSE for details.
Built with ❤️ for developers who code 24/7
