# HOUSE OF AI® Flight School — Brevo-ready email copy and variables
Placeholders resolved by secure server events, escaped appropriately. Replace live URLs only from verified tenant settings.

## T0 Confirmation (transactional, ONLY after paid access)
Subject: You're cleared for takeoff ✈️ Your cockpit is ready
Preview: Your boarding pass, preflight and welcome gift.
Hey {{first_name}}!
You're confirmed for {{offer_title}} on {{class_date}} at {{class_time}} {{timezone}}.
Your seat: {{seat_number}} of {{seat_capacity}}.
Your private cockpit: {{cockpit_link}}
Your gorgeous HOUSE OF AI boarding pass is below: {{boarding_pass_image}}
**Complete your guided 10-minute Preflight Survey:** {{preflight_link}}
It saves your answers so we can work on your actual business, not start over.
{{gift_section_if_verified}}
Bring your laptop, a working Claude sign-in, and one small task.
Questions? Reply to {{support_email}}.
Lisa | HOUSE OF AI®

## T1 Preflight reminder (transactional)
Subject: Your preflight checklist — ten minutes, tops
Hi {{first_name}}! Open {{preflight_link}} to sign in to Claude, complete your Business Snapshot, and pick one task. If you've finished, you're all set. See you on {{class_date}}!

## T2 Day before (transactional)
Subject: Tomorrow we fly. Here's your runway.
Hi {{first_name}}, we'll meet on {{class_date}} at {{class_time}} {{timezone}}. Live room: {{classroom_link}}. Cockpit: {{cockpit_link}}. Bring your laptop and one task. Lisa

## T3 Hour before (transactional)
Subject: Boarding starts in one hour ✈️
Your live room: {{classroom_link}}. See you soon! Lisa

## T4 Replay (transactional, only after real recording exists)
Subject: You flew it. Keep your controls.
Replay: {{replay_link}}. Your prompts, snapshot and flight manual: {{cockpit_link}}. Group support available through {{support_end}}.

## N1 Day after (optional marketing)
Subject: What are you never doing the old way again?
What did Claude make easier? Hit reply with your answer. If you want us to build your complete Business Brain together, the optional Private Cockpit founding beta is {{beta_price}}. Details: {{premium_link}}.
{{unsubscribe_link}}

## N2 Three days later (optional marketing)
Subject: Your Snapshot is the beginning. Not the entire brain.
We'll reuse your existing Snapshot and work with you on a full Business Brain and tailored Claude Project. The optional beta is {{beta_price}}: {{premium_link}}.
{{unsubscribe_link}}

## N3 Five days later (optional marketing)
Subject: Flying is one thing. Installing autopilot is another.
Your class taught practical Claude skills. Bespoke integrations and AI employees are different, separately scoped engagements. Explore whether that's what you need: {{premium_link}}.
{{unsubscribe_link}}

## N4 Seven days later (optional marketing)
Subject: Your next flight is entirely your call.
Your class resources stay yours. If you want deeper guided help with your business, here's your optional {{beta_price}} founding beta: {{premium_link}}. No manufactured deadlines.
{{unsubscribe_link}}

### Requirements
- Brevo integration not active simply because these files exist.
- No marketing sends without separately recorded affirmative consent and working unsubscribe.
- Suppress existing beta purchasers, cancellations and refunds appropriately.
- Price, availability, event schedule and real links are authoritative client config, not hardcoded promises.
