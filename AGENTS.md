# HOUSE OF AI® Client Factory — coding agent rules
This repository is PUBLIC by owner choice until changed. NEVER commit customer records, secret tokens, private logos, private contracts, API keys or Stripe data.
- This repository is an SOP and templates, not yet a working or deployed customer platform.
- Make client-specific details configuration-driven. Enforce tenant isolation on every backend request and payment event.
- Payment-to-access: verify Stripe signature, merchant, status, amount/currency, product, capacity and idempotency; grant correct app AND gift entitlements, then issue transactional welcome.
- Brevo is the intended email provider. Never call Brevo live endpoints or use real contact lists before access, verified sender, approval and end-to-end tests.
- Transactional sends are independent of separately opted-in marketing flows. Honor unsubscribe and suppress upgraded purchasers.
- All sends need durable job status, provider ID, retry, failure alerts and deduplication.
- Keep onboarding data private and reusable, with voice-friendly questions, consent, correction and deletion.
- Brand assets must be original, authorized and client-specific.
- Live sales and live emails require owner signoff; do not fabricate that integrations are connected.
