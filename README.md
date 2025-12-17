# OFF Demo

Version: **v0.453**  
Status: Public-facing demo backed by a real backend

This demo exists to **illustrate OFF**, not to replace the backend or bypass its rules.
If something looks right in the demo but is wrong in the backend, that is a bug — not a demo feature.

---

## What This Demo Is

The OFF demo is:
- A lightweight UI that talks to the real OFF backend
- A way to understand core flows (signals, vibes, messages)
- A credibility surface for showing how OFF behaves

The demo is intentionally simple and opinionated.

---

## What This Demo Is *Not*

The demo is not:
- A mocked backend
- A simulation of persistence
- A client-side prototype
- A substitute for API verification

There is no “demo-only logic” that changes correctness.

---

## Backend Relationship

The demo:
- Calls the real Render-hosted API
- Uses real authentication headers
- Is subject to the same:
  - role enforcement
  - idempotency rules
  - persistence guarantees

If the backend is unavailable or misconfigured, the demo should fail visibly.

---

## Real vs Simulated Elements

### Real
- API calls
- Authentication and roles
- Persistence of signals, vibes, and messages
- Idempotency behavior
- Error responses

### Simulated (UI-only)
- Timing and transitions
- Loading states
- Narrative flow
- Visual affordances

Simulation is limited strictly to presentation.

---

## API Keys & Safety

- Demo API keys are scoped specifically for demo use
- Keys are never displayed in the UI once saved
- Keys must be rotated if exposed

If you are screen-sharing:
- Assume anything visible could be recorded
- Treat demo keys as disposable

---

## Persistence Expectations

Actions performed in the demo:
- Write to the real database
- Persist beyond page refresh
- Are traceable via `request_id`

If data appears to “reset,” that indicates:
- a backend issue
- a deployment
- or a deliberate cleanup

Not normal demo behavior.

---

## Idempotency & Retries

The demo:
- Sends idempotency keys for mutating actions
- Relies on the backend to handle retries safely

Refreshing the page or re-clicking actions should not create duplicates.

---

## Error Handling Philosophy

Errors are:
- surfaced clearly
- not hidden for the sake of smoothness
- part of demonstrating trustworthiness

A visible error is preferable to silent failure.

---

## When to Use the Demo

Use the demo to:
- Walk through OFF’s mental model
- Validate backend behavior visually
- Support conversations and presentations

Do not use the demo to:
- Validate schema changes
- Debug subtle backend bugs
- Replace API-level testing

---

## Known Limitations (v0.453)

- No advanced matching or scoring
- Limited role differentiation
- Minimal UI state management
- No offline-first behavior

These are deliberate constraints.

---

## If Something Looks Wrong

If demo behavior seems incorrect:
1. Verify the backend using direct API calls
2. Check logs using `request_id`
3. Confirm environment configuration

Never “fix” the demo to hide backend issues.

---

## Related Documentation

- Root overview: `README.md`
- Trust rules: `docs/SECURITY.md`
- Architecture: `docs/ARCHITECTURE.md`
- API contract: `docs/openapi.yaml`

---

End of file.
