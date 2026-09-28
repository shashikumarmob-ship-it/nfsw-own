# 🤖 Aether Telegram AI Bot (Pollinations AI)

An intelligent, unrestricted Telegram AI Chat Bot powered by the free cloud AI at **Pollinations.ai**.

## ✨ Features
* 🧠 **Human-Like Dual Memory System:**
  * **Short-Term Context Memory:** 16-turn rolling conversation thread so the AI remembers continuous chat threads like a real human.
  * **Long-Term User Fact Extraction:** Automatically notes name, interests, location, and relationship preferences in `user.memories` and weaves them organically into replies.
  * **Memory Management:** Dedicated `[ 🧠 View AI Memory ]` panel in Profile to view or clear stored facts.
* 🎭 **4 Distinct AI Personas:** Switch between Romantic Partner, Bold & Uncensored, Smart Assistant, and Anime Waifu.
* 💬 **Interactive Chat Mode:** Natural, emotionally present roleplay without robotic disclaimers.
* 👤 **Interactive Profile Card:** Real-time stats with inline action buttons.
* 🪙 **Credit Economy:** Credit balance deduction per message (1 credit per prompt).
* 🎁 **Daily Bonus:** Free daily credits claimable every 24 hours.
* 🧹 **Memory Reset:** Clear conversation memory at any time with 1 click.
* ⚡ **Pollinations AI Integration:** 100% Free, powered by `openai-fast` (`gpt-oss-20b`).
* 🚀 **Render Ready:** Includes built-in lightweight HTTP health-check server to satisfy Render's port-binding requirement.

---

## 🛠️ Local Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Configure `.env`:**
   Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```
   Open `.env` and paste your Bot Token from [@BotFather](https://t.me/BotFather):
   ```env
   BOT_TOKEN=123456789:ABCdefGhIJKlmNoPQRstuVWXyz
   ```

3. **Start the bot:**
   ```bash
   npm start
   ```

---

## ☁️ Deployment on Render.com (100% Free)

1. **Push your code to GitHub:**
   * Create a new repository on [GitHub](https://github.com).
   * Push all files (except `node_modules` and `.env`).

2. **Create Web Service on Render:**
   * Open [Render Dashboard](https://dashboard.render.com/).
   * Click **New +** -> **Web Service**.
   * Connect your GitHub repository.

3. **Configure Settings:**
   * **Name:** `my-telegram-ai-bot`
   * **Environment:** `Node`
   * **Region:** Any (e.g. Oregon / Singapore / Frankfurt)
   * **Build Command:** `npm install`
   * **Start Command:** `npm start`
   * **Instance Type:** `Free`

4. **Add Environment Variables (under 'Environment' tab on Render):**
   * Key: `BOT_TOKEN` | Value: *(Aapka BotFather token)*
   * Key: `POLLINATIONS_MODEL` | Value: `mistral`
   * Key: `INITIAL_CREDITS` | Value: `30`
   * Key: `DAILY_BONUS` | Value: `20`

5. **Deploy:**
   Click **Deploy Web Service**. Render will build and run `npm start`.
   The built-in health-check server binds to Render's `$PORT` so your service will report **Healthy** and stay online!
