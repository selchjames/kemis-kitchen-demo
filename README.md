# AI Customer Support Chatbot: Portfolio Demo

**Built by Dinah Vertex Ltd (AI consultancy, Abuja)**

This demo shows "Ada", a support assistant for **Kemi's Kitchen & Delivery**, a *fictional* Lagos food business. All names, phone numbers, bank details, orders and prices are made up.

## What it shows
- **Works offline with no API key.** It uses a local knowledge base covering the menu and naira prices, how to order, delivery zones in Lagos and Abuja and their fees, payment by transfer, card or USSD, refunds and cancellations, opening hours, catering and dietary questions.
- **Intent routing** with keyword and phrase matching, plus typo tolerance (Levenshtein), so a message like "delivrey fee" still gets the right answer.
- **Small talk in a Nigerian-friendly tone**, with light Pidgin ("How far!", "No wahala", "I dey kampe") and Yoruba, Igbo and Hausa greetings or thanks.
- **Order tracking** with demo order IDs: `KK-1042` (out for delivery), `KK-2087` (being prepared), `KK-3155` (delivered) and `KK-4410` (awaiting payment).
- **Handoff to a human.** The bot collects a name, a Nigerian mobile number (checked and normalised to +234) and the issue, then shows a support ticket on screen.
- **Quick-reply chips**, a typing indicator, a responsive layout that goes full-screen on mobile, and consistent branding.
- **Optional LLM mode.** Click ⚙ AI mode and paste an OpenAI-compatible key, base URL and model. Answers are then grounded in the same knowledge base. The key is held only in memory and is never written to storage. If the call fails, the bot falls back to its offline answers.

## How to run
Open `index.html` in any browser. There is no build step, server or dependency.
Tests (optional): `npm i playwright-core`, then `node test.mjs`. The test script uses Chrome at /usr/bin/google-chrome.

## Adapting it for a real client
- **Knowledge base:** replace the `KB` array with the client's FAQs, or load them from a Google Sheet or CMS so staff can edit answers themselves. For larger document sets, use embeddings or RAG.
- **Website widget:** wrap the chat as a floating bubble and add it to the site with a single `<script>` tag.
- **WhatsApp:** connect the same routing and LLM logic to the WhatsApp Business Cloud API (or Twilio or 360dialog) through a small serverless webhook. Quick-reply chips become WhatsApp interactive buttons.
- **Order status:** replace the `ORDERS` mock with a call to the client's POS, Shopify or WooCommerce store, or delivery API.
- **CRM and ticketing:** send handoff tickets to HubSpot, Zoho, Freshdesk or Google Sheets, and notify agents on Slack or WhatsApp.
- **Production LLM:** keep API keys on the server (never in the browser), add rate limiting, logging and analytics, and comply with the NDPA (Nigeria Data Protection Act) for customer data.
