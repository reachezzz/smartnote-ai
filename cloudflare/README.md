# SmartNote AI — optional Cloudflare Worker

This Worker powers optional Claude, OpenAI and Gemini analysis. The **free local mode needs no Worker**.

## Deploy

1. Create a Cloudflare account and open **Workers & Pages → Create → Worker**.
2. Name it `smartnote-ai-api`, deploy, then edit its code with the contents of `worker.js` and deploy again.
3. Under **Settings → Variables and Secrets**, create encrypted secrets:
   - `ACCESS_TOKEN`: a long random token (at least 32 characters). Users of your personal Worker must enter this token in the app; do not publish it.
   - `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`: only the providers you want to enable.
4. Open SmartNote AI, select **Externe KI**, enter your Worker URL (for example `https://smartnote-ai-api.<your-subdomain>.workers.dev`) and your access token, and select a provider.
5. Try a short test note. Check Cloudflare logs if the request fails.

**Security:** The token is held in the browser's memory only, never stored. A shared token is appropriate for a private demo, **not for a public multi-user product**. Do not publish your Worker token or API keys. A production public service requires per-user authentication, per-user quotas, durable rate limiting, spending limits, monitoring and an abuse-prevention layer. CORS is not authentication. Provider API usage may incur charges. Cloudflare Workers free tier has limits. Model IDs may need updating; set optional `ANTHROPIC_MODEL`, `OPENAI_MODEL`, or `GEMINI_MODEL` variables to override defaults.

The Worker accepts POST JSON `{"provider":"anthropic|openai|gemini","text":"..."}` with `Authorization: Bearer <ACCESS_TOKEN>`, and responds with `{"result":"..."}`. Only `https://reachezzz.github.io` is allowed as a browser Origin.

**Privacy:** In external mode, the selected note is sent to Cloudflare and the chosen AI provider after confirmation. In free mode, notes stay in the browser.
