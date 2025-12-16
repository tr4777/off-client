# OFF — Live Backend Demo (v0.453)

This page demonstrates the **OFF backend running live**.

Nothing here is mocked.  
Nothing is simulated.  
Every action executes against the real API and persists to the database.

---

## What this demo shows

A complete OFF interaction lifecycle:

1. **Health check**
   - Confirms backend availability

2. **Guest creates a signal**
   - Intent + location
   - Persisted to Supabase with event tracking

3. **Admin creates an offer**
   - Linked to the signal
   - Fully persisted with database constraints enforced

4. **Guest accepts the offer**
   - Idempotent by design
   - Safe to replay without duplication or side effects

5. **Guest creates a vibe**
   - Establishes a shared interaction space

6. **Guest sends a message**
   - Actor identity is derived from authentication
   - Header spoofing is ignored by the server

7. **Guest and concierge fetch messages**
   - Both roles see the same canonical state

---

## What’s special here

### 🔒 Identity safety
- `X-Actor-Id` headers are ignored
- Actor identity is derived exclusively from auth context
- Spoofing attempts are safely neutralised server-side

### ♻️ Idempotency
- Offer acceptance is replay-safe
- Duplicate requests never create duplicate state
- Replay behavior is explicit and observable

### 🧱 Persistence-first architecture
- Signals, offers, vibes, and messages are all persisted
- Database constraints enforce correctness
- No UI-level illusion of success

### 🧠 Calm engineering
- Deterministic outcomes
- No race conditions
- No hidden side effects

---

## Intended audience

This demo is designed for:
- Engineers
- Technical founders
- Platform partners
- Investors evaluating system integrity

It prioritises **clarity and correctness** over visual polish.

---

## Version

**v0.453**  
Backend stabilisation milestone

Includes:
- Signals
- Offers
- Vibes
- Messages
- Auth-derived identity
- Idempotency guarantees

---

Future enhancements may include:
- Visual status indicators (green / yellow / red)
- Live terminal-style activity feed
- Inline explanations per lifecycle step
