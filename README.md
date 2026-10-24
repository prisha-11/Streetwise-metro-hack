# Streetwise AI

Streetwise AI helps local business owners review a storefront, menu, product, or promotion through a customer-first lens, then turn the observations into practical marketing actions.

## Run locally

1. Install Node.js 20 or newer.
2. Run `npm install`.
3. Copy `.env.example` to `.env` and set `OPENAI_API_KEY` on the server. Optionally set `OPENAI_MODEL` (default `gpt-4.1-mini`). Never add a key to client code or commit `.env`.
4. Run `npm run dev` and open the Vite URL (normally http://localhost:5173).

The browser talks to `/api` endpoints through the Vite development proxy. The API key is read only by Express. Uploaded JPG, PNG, and WebP images are held in memory for the request, up to 8 MB. They are not persisted by the server. Browser-side audit history is stored in local storage on that device.

## Demo

“Try a sample audit” runs the sample storefront through OpenAI when the server key is configured. When OpenAI is not configured or unavailable, the app shows a clearly labelled deterministic demo audit and example makeover content. Uploaded-image audits and live campaign generation require the API.

The opportunity score is a model-generated heuristic, not a validated benchmark. Customer perspectives are simulated hypotheses, not actual customer interviews. The tool does not measure business performance or guarantee results.

## Limitations

This MVP has no account sync, database, analytics, or production hosting configuration. History is local to the browser. For production, add deployment-specific API proxying, request throttling, stronger operational monitoring, and a privacy policy appropriate to the deployment.
