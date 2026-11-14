# Homing

Homing turns Android phones into an SMS gateway you control.

Install the Homing app on an Android phone with a SIM card and your software can send SMS, data SMS and MMS through it with a simple HTTP API. Delivery reports and received messages come back to you as signed webhooks.

## Two ways to run it

- **Local mode.** One phone serves the API on your own network. No account needed.
- **Homing Cloud.** Pair one or many phones and manage the whole fleet from the web console, with messages routed across phones and SIMs.

Both modes use the same request and response shapes, the same API key format and the same webhook signatures, so code written against one works with the other.

## Send a message

```bash
curl -X POST "$HOMING/messages" \
  -H "Authorization: Bearer $HOMING_KEY" \
  -H "Content-Type: application/json" \
  -d '{"type":"sms","to":"+15555215554","text":"Hello from Homing"}'
```

The phone answers `202 Accepted` and the message moves from `pending` to `sent` and, when the carrier confirms, `delivered`.
