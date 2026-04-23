# Shy Media (Future Feature – Phase 3+)

> **Note:** This is a speculative feature for consideration after Flash’s core signal protocol is established. It is **not** part of v0.5 or Phase 1‑2.

## Definition

A **Shy Media flash** is a tap‑to‑view, 2‑second vanishing photo or video clip attached to a **fleeting warmth flash** (or as a standalone “secret” mode). The receiver must deliberately choose to see it, and it disappears permanently after 2 seconds.

## Behaviour

| Aspect | Detail |
|--------|--------|
| **Sender flow** | After picking “Warmth”, attach 1 photo or 1 video clip (max 2 seconds). No caption, no editing. |
| **Receiver flow** | Notification arrives (1‑second poke + ghost window). Instead of soldiers, receiver sees a blurred thumbnail or a **“👁️ Tap to view”** button. |
| **Viewing** | On tap, the media plays/shows for **exactly 2 seconds**, then disappears permanently from device and server. |
| **No replay** | No option to replay. If missed, it’s gone. |
| **Screenshot warning** | UI shows: *“This moment will vanish after 2 seconds – no saving.”* (System cannot technically prevent screenshots.) |
| **History** | Only a **daily counter** of shy media flashes sent/received. No content, no timestamps, no sender attribution in the log (except per‑contact totals). |
| **Rate limit** | 5 shy media flashes per relationship per day (configurable). |

## Use cases

- “Look at this cute thing my kid just did” – shared once, then gone.
- “This made me think of you” – a photo that doesn’t accumulate.
- Romantic or playful inside moments that are not meant to be permanent.

## Risks & mitigations

| Risk | Mitigation |
|------|-------------|
| Harassment / abuse | Report button on viewing screen. Mute/block per contact. Rate limit. |
| Expectation mismatch | No “unread” badge – only daily count. |
| Product dilution | Keep as **optional mode**, not default. |
| Legal / compliance | Store nothing on server; client‑side only with expiring keys. |

## Phasing

- **Phase 1 & 2** – Not included.
- **Phase 3** – Prototype after fleeting warmth + reciprocation are live and well‑understood.
- **Phase 4** – Full launch only if user demand and safety mechanisms are proven.

## Interaction with other Flash modes

| Mode | Compatibility |
|------|---------------|
| Action flash | **No** – attachments break accountability. |
| Persistent warmth (8s ring) | **No** – attachments would extend session. |
| Fleeting warmth (1s poke) | **Yes** – shy media attached replaces the ghost window with the 2‑sec viewing. |
| Standalone “Secret” mode | **Alternative** – create a separate signal type outside warmth hierarchy. |

## Technical notes (for future implementation)

- Media encrypted client‑side with a one‑time key.
- Server never stores decrypted media; reference expires after 2 seconds from view.
- Video truncated to 2 seconds on device before sending.
- No caching in browser memory after playback.
