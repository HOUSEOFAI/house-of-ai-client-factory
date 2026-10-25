# Brevo automation | HOUSE OF AI® Client Factory
**Implementation plan only. Not connected or live.**

## Configuration per client
1. Obtain client authorization and connect their chosen Brevo account, separate subaccount, or authorized sending setup. Do not assume that all clients can share sender reputation, data or billing.
2. Configure and verify sender/domain, reply-to, DNS authentication and sending requirements in Brevo, and note the per-tenant account configuration. Store API key only as backend secret (never GitHub, never browser).
3. Create reusable Brevo transactional templates using the exact email sequence in `templates/email-sequence.md`. Put generated template IDs into that client's private configuration.
4. Link application events to Brevo: `payment_verified`, `preflight_incomplete`, `class_start_minus_1_day`, `class_start_minus_1_hour`, `replay_ready`. Backend event worker dispatches transactional emails; scheduling must occur only for confirmed enrollees.
5. Post successful fulfillment, send the boarding-pass image hosted in authorized client asset storage (not as a false personalized ticket). Show personalized seat number and name in separate safe text unless image renderer exists.
6. Contact list / Brevo automation: sync opted-in contacts only, with client-specific tags and verified consent timestamp/source. Trigger optional `nurture_1` through `nurture_4` after class; cancel on unsubscribe, refund or premium purchase. Respect Brevo account consent and sending rules.
7. Store per-event idempotency key (e.g. `tenant:enrollment:template:version`), provider response message ID, sent/failed/retry status, timestamps and suppressed reason. Queue retries safely; do not send duplicate messages.
8. Confirm webhook-driven access to the *separate* Artificialis Intellectum app before offering gift access. A public link is NOT proof of entitlement.
9. Preflight collected responses must be stored tenant/private-user scoped. Instructor can receive a safe summary/alert after completion, not all protected answers by email.
10. Run full sandbox/test delivery and manual QA, obtain explicit founder approval, then enable production sending.

## Trigger map
| When | Trigger | Email | Consent |
| --- | --- | --- | --- |
| Immediately after verified paid entitlement | payment_verified | Confirmation + boarding pass + survey link | Transactional |
| About 3 days before start if needed | preflight pending | Preflight checklist | Transactional |
| 1 day before | confirmed and not cancelled | Class details | Transactional |
| 1 hour before | confirmed and not cancelled | Join link | Transactional |
| After replay exists | replay_ready | Replay and materials | Transactional |
| +1 day after class | marketing opted-in, not upgraded | Nurture 1 | Marketing |
| +3 days | opted-in, not upgraded | Nurture 2 | Marketing |
| +5 days | opted-in, not upgraded | Nurture 3 | Marketing |
| +7 days | opted-in, not upgraded | Nurture 4 | Marketing |

## Test and go-live gate
Never trigger sale-time emails before signature-verified successful payment and correct user entitlement. Test new buyer, invalid payment, failed link, absent gift permission, duplicate webhook, unsubscribed contact, upgrade purchase, sender authentication, broken links, mobile and delivery logs. Build a manual resend/recovery interface for admins. Check current Brevo API specs, app plan limits, and applicable email marketing regulations at implementation. 
