# Homing

Homing turns Android phones into an SMS gateway you control.

Install the Homing app on an Android phone with a SIM card and your software can send SMS, data SMS and MMS through it with a simple HTTP API. Delivery reports and received messages come back to you as signed webhooks.

## Built for your own messages

Homing is for the messages your product sends to its own users and team: one-time codes, order and appointment updates, alerts and replies, sent from your own phone and SIM. It is not a bulk marketing service or a way to route other people's traffic. You message only people who agreed to hear from you, Homing honors opt-out replies, and you follow your carrier's terms and local law.

## Two ways to run it

- **Local mode.** One phone serves the API on your own network. No account needed.
- **Homing Cloud.** Pair your phones and manage them from the web console, with team access, message history and signed webhooks.

Both modes use the same request and response shapes, the same API key format and the same webhook signatures, so code written against one works with the other.

## Send a message

```bash
curl -X POST "$HOMING/messages" \
  -H "Authorization: Bearer $HOMING_KEY" \
  -H "Content-Type: application/json" \
  -d '{"type":"sms","to":"+15555215554","text":"Hello from Homing"}'
```

The phone answers `202 Accepted` and the message moves from `pending` to `sent` and, when the carrier confirms, `delivered`.

## Legal

[Terms of Service](https://homingsms.com/legal/terms) · [Acceptable Use Policy](https://homingsms.com/legal/acceptable-use) · [Privacy Policy](https://homingsms.com/legal/privacy)
