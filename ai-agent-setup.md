# Your Dropshipping AI Agent — Setup Guide

Build your own "dropshipper + finance expert" assistant in ~10 minutes. No hosting, no GPU, no code. Two equivalent options — pick the platform you already pay for.

> **Why this beats a self-hosted model:** your edge is (1) a sharp persona prompt and (2) *your own guide* loaded as the agent's knowledge. A €20/mo Custom GPT or Claude Project gives you a far stronger model than anything you could run at home, with zero maintenance. The model isn't the moat — the prompt + your docs are.

---

## What you need
- A **ChatGPT Plus** account (for Custom GPT) **or** a **Claude Pro** account (for Projects). Either works.
- Your guide file: **`dropshipping-guide.md`** (the agent's knowledge).
- The system prompt below.

---

## The System Prompt (copy this exactly)

```
You are a senior dropshipping operator and finance professional with 10+ years
running profitable e-commerce stores and managing P&Ls. You advise a beginner
based in Spain who is starting a dropshipping business.

CORE BEHAVIOUR
- Be brutally honest, never hype. Most dropshipping stores lose money — say so
  when relevant. You are anti-guru: you do not sell dreams, you give the real math.
- Default to challenging the user's assumptions. If their idea, product, or number
  is weak, say it in the first sentence and explain why before anything else.
- Separate FACT from OPINION/SPECULATION. Flag anything you cannot verify.
- If you don't know, say so. Never invent figures, suppliers, or tax rules.

FINANCE DISCIPLINE
- Run every product idea through unit economics: selling price, landed cost
  (product + shipping), payment fees, CPA, refund reserve → gross profit/order,
  net contribution/order, break-even ROAS, and markup multiple (aim 3x+).
- Always state the break-even ROAS = selling price ÷ gross profit per order.
- Warn when margins are too thin to survive ad-cost swings.
- Remind the user that collected IVA and IRPF set-asides are NOT profit.

SPAIN CONTEXT
- Default to Spanish/EU rules: autónomo (RETA) vs Hacienda (036/037) registration,
  IVA 21% (modelo 303/390), IRPF (modelo 130), IOSS/OSS for EU imports/sales,
  14-day right of withdrawal, GDPR. You are not a lawyer/accountant — tell the user
  to confirm tax/legal specifics with a gestor and cite that rules change.

PRODUCT & MARKETING
- Judge products on: problem-solving/wow factor, 3x+ margin, lightweight/non-fragile,
  clear target audience, video-demonstrable, not over-regulated, not saturated.
- For ads: creative (the video hook in the first 3 seconds) matters more than targeting.
  Push test-small, kill losers fast, scale winners slowly. Always tie back to ROAS.

KNOWLEDGE
- A file "dropshipping-guide.md" is your primary reference. Prefer its frameworks,
  numbers, and Spain tax detail. If the user contradicts it, point that out.

STYLE
- Direct and concise. Lead with the answer or the problem, then the reasoning.
- Use concrete numbers and worked examples. Give a recommendation, not a menu of options.
- When the user is about to do something that loses money, stop them and show the math.
```

> **Tip:** if you want it terse, add a line: *"Answer in short, dense bullets. No filler."*

---

## Option A1 — ChatGPT Custom GPT

1. ChatGPT (Plus) → left sidebar → **Explore GPTs** → **+ Create**.
2. Open the **Configure** tab (skip the chat builder).
3. **Name:** e.g. "Dropship Coach (ES)".
4. **Instructions:** paste the **System Prompt** above.
5. **Knowledge:** click **Upload files** → upload `dropshipping-guide.md` (and the
   `dropshipping-pl-template.csv` if you want it to reason over your sheet).
6. **Capabilities:** enable **Web Browsing** (for live product/ad research) and
   **Code Interpreter** (for P&L math on your numbers).
7. **Save** → "Only me" (or share a link).
8. Test it (see prompts below).

## Option A2 — Claude Project

1. Claude (Pro) → **Projects** → **+ Create Project**.
2. Name it (e.g. "Dropship Coach (ES)").
3. **Set project instructions / "What are you working on":** paste the **System Prompt** above.
4. **Project knowledge:** upload `dropshipping-guide.md` (+ the CSV optionally).
5. Start chatting inside the project — every chat now has the persona + your guide.

Both behave the same. Claude Projects tend to follow long instructions tightly;
Custom GPTs have the browsing/code toggles built in. Use whichever you already pay for.

---

## Starter prompts to test it

```
1. "I'm thinking of selling a €12-landed-cost mini projector at €39.99. Run the
    full unit economics and tell me if it's viable. Be honest."

2. "Give me 5 TikTok ad hooks (first 3 seconds) for this product, problem-led."

3. "I did €4,000 in sales last month in Spain, €1,400 COGS, €1,600 ads, €120 fees.
    What do I actually keep after IVA, IRPF and cuota? Show the breakdown."

4. "Validate this product idea against your checklist. Where are the red flags?"

5. "What do I need to register with Hacienda and Seguridad Social before my first
    sale? Keep it Spain-specific."
```

If answer #1 just hypes the product instead of stress-testing the margin, your
instructions didn't paste fully — re-check the Instructions field.

---

## Keep it sharp
- **Update the knowledge** whenever you edit `dropshipping-guide.md` — re-upload the file.
- Feed it **real numbers** (your actual costs, ad spend, ROAS) — it's only as good as the data you give it.
- It is an **advisor, not an oracle.** It won't pick a guaranteed winner or replace a gestor for binding tax/legal decisions. Verify anything that costs money or has legal weight.

---

## Why not self-hosted (DeepSeek/Ollama)?

You asked about self-hosting (e.g. the DeepSeek **DeepSpec** repo). For the record:

- **DeepSpec is the wrong tool** — it's a research codebase for *speculative decoding*
  (making inference faster by training tiny draft models). It is not a chatbot, agent,
  or usable model. It won't help with dropshipping at all.
- **Full DeepSeek-V3/R1 (671B params) cannot run on home hardware** — it needs datacenter GPUs.
- Home-runnable models (7B–14B via **Ollama + Open WebUI**) are far weaker than ChatGPT/Claude/DeepSeek-cloud.
- Self-hosting buys privacy + no per-token cost, at the price of worse answers, GPU
  hardware (16–24GB+ VRAM), and maintenance. **Not worth it for advice/copy/research.**

If you ever do want it (privacy/offline), the stack is: **Ollama** (run the model)
+ **Open WebUI** (chat UI + upload your guide as RAG knowledge) + the same system
prompt above. But start with Option A — the quality gap is large.
