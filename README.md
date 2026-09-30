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
* ⚡ **Dual AI Engine:**
  * **Pollinations AI:** 100% Free anonymous tier powered by `openai-fast` (`gpt-oss-20b`), with optional `POLLINATIONS_API_KEY`.
  * **Hugging Face Inference Providers:** OpenAI-compatible serverless router (`https://router.huggingface.co/v1/chat/completions`) supporting `Llama-3.1-8B-Instruct`, `Qwen2.5-72B`, `DeepSeek-R1`, etc. via free `HF_TOKEN`.
  * **Zero-Downtime Auto-Failover:** If one provider or model fails (e.g. 402/404/rate limits), the bot automatically fails over without breaking user chats.
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
   Open `.env` and set your variables:
   ```env
   BOT_TOKEN=123456789:ABCdefGhIJKlmNoPQRstuVWXyz
   OWNER_ID=1234567890

   # AI Provider: 'auto', 'pollinations', or 'huggingface'
   AI_PROVIDER=auto

   # Free without API key:
   POLLINATIONS_MODEL=openai-fast

   # Optional Hugging Face Token (from https://huggingface.co/settings/tokens):
   HF_TOKEN=
   HF_MODEL=meta-llama/Llama-3.1-8B-Instruct
   ```
   *(Send `/id` to the bot in Telegram to get your User ID)*

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
   * Key: `OWNER_ID` | Value: *(Aapka Telegram User ID for ♾️ Unlimited Credits)*
   * Key: `POLLINATIONS_MODEL` | Value: `openai-fast`
   * Key: `HF_TOKEN` | Value: *(Optional: Hugging Face token for Llama-3.1/Qwen backup)*
   * Key: `INITIAL_CREDITS` | Value: `30`
   * Key: `DAILY_BONUS` | Value: `20`

5. **Deploy:**
   Click **Deploy Web Service**. Render will build and run `npm start`.
   The built-in health-check server binds to Render's `$PORT` so your service will report **Healthy** and stay online!
