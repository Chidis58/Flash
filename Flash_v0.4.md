# Flash ⚡ v0.4

> **Note:** This specification is the absolute and definitive record of the Flash protocol. It supersedes and renders obsolete all previous documentation, including "Nod", "Flash v0.1", "Flash v0.2", and "Flash v0.3".

**Flash** is an ambient communication layer designed for zero‑latency coordination. It is a "Short‑Pulse" protocol that behaves like a phone call but carries the lightweight intent of a message. It is designed specifically for high‑speed environments where looking at a screen to read a long chat is impossible.

---

## 🧠 Core Philosophy (The Six Principles)

These principles guide every engineering decision.

1. **The flash is the message** – A flash carries zero content. Its meaning is borrowed entirely from the pre‑established relationship (or from the provisional meaning library). The signal itself is the communication.
2. **Zero social debt** – ⚡ (got it) or ❌ (decline) closes the transaction. No lingering obligation, no unread guilt. The session ends and everyone moves on.
3. **Peripheral awareness** – You perceive the state, you don't check it. Colour, rhythm, and light over banners and text. The environment is the interface.
4. **Consent is mutual** – No relationship can be imposed unilaterally. Both parties agree to the core meaning and authority direction. However, **provisional mode** allows immediate interaction with implicit consent.
5. **The record is the referee** – Both sides hold an identical immutable copy of every session. Neither party can rewrite history or dispute a timestamp.
6. **Protocol over escape hatch** – No early fallback to calls or messaging. Trust the protocol, train the users. The system enforces its own discipline.

---

## ⚡ The Core Logic: The "Flash Call"

A Flash is not a notification; it is a **Life Event** on the device.

1. **The 8‑Second Ring:** When a Flash is sent, the receiver’s device enters a "Ringing" state for exactly 8 seconds.
2. **Context‑First Display:** Unlike a standard call, the **Reason (Meaning)** for the Flash is visible immediately. The user sees the sender's identity and the intent (e.g., "I'm Outside" or "Order Ready") at the same time.
3. **The Behaviour:** It functions like a WhatsApp pop‑up message but with the urgency and audio/haptic priority of a phone call. 8 seconds is the optimal window for the brain to perceive, read the context, and act.
4. **Auto‑Settle:** If no action is taken during the 8 seconds, the "Call" settles into a quiet, breathing **Ambient Orb** on the screen.
5. **Haptic Breath:** Every 2 minutes while a session is active (waiting for reply), the device emits a faint, gentle haptic pulse. This keeps the session present in peripheral awareness without demanding attention.

---

## 🤝 Provisional Flashing (Zero‑Friction Onboarding)

To solve the "Dual Consent" hurdle, Flash v0.4 introduces **Provisional Mode**.

- **Skip the Setup:** You do not need a pre‑negotiated relationship to send a Flash. You can Flash any contact immediately.
- **The Provisional Handshake:** The first Flash arrives with a "Provisional" tag. The receiver can reply with ⚡ (Got it) or ❌ (Decline) immediately.
- **Implicit Consent:** By responding to a Provisional Flash, the relationship is automatically created with sensible defaults (using templates – see below). There are no "Invite" or "Setup" screens – only action.
- **One‑Tap Acceptance from Lock Screen:** The receiver never needs to open the app to accept. The flash itself *is* the acceptance. Tapping the right soldier during the 8‑second ring instantly creates the relationship.

### Social Graph Auto‑Setup

If two people are already connected in the device’s contacts, or on linked platforms (WhatsApp, LinkedIn, etc.), Flash can:
- Pre‑fill a relationship template based on the context (e.g., “Colleague” for work contacts).
- Show a banner inside the other app: *“You and Bello are on Flash. Tap to start flashing.”*
- No search, no invite link – just one tap to activate.

---

## 📋 Smart Templates & Meaning Library

To remove all setup friction, Flash uses **context templates** and a **fixed meaning library**.

### Templates (pre‑configured defaults)

| Template | Signal Type | Default Expiry | Reply Window | Max Flashes/Day | DND Override |
|----------|-------------|----------------|--------------|-----------------|--------------|
| **Colleague** | Action | 4 hours | 15 min | 3 | Off |
| **Client** | Action | 2 hours | 10 min | 5 | Flash 3+ |
| **Friend** | Warmth | None | Optional | 3 (soft limit) | Never |
| **Family** | Action (soft) | 24 hours | 30 min | 5 | Flash 3+ |

The sender picks a template when flashing someone for the first time. The receiver sees the template name during the 8‑second ring.

### Global Meaning Library (no typing)

All meanings are pre‑defined, curated phrases. The sender picks one from a list. The receiver sees that exact phrase during the flash.

**Action meanings (command direction – superior → executor):**
- Come here
- I’m outside
- Ready when you are
- Urgent – call me
- Check this
- Order ready
- Come fix my hair (example)

**Warmth meanings (either direction, same meaning):**
- Thinking of you
- Home safe
- Just because
- I’m here if you need

> No custom text entry. Ever. This is what makes Flash instant.

---

## 🔄 Asymmetric Reverse Flash (Executor → Superior)

The relationship is **not one‑way**. The executor (the person who receives commands) can flash back, but **their flash is always a question or request, never a command**.

- **Superior → Executor:** “Come to my office.” (command)
- **Executor → Superior:** “Can I come to your office now?” (question)
- **Superior replies:** ⚡ (yes / got it) or ❌ (no / decline)

This is enforced by the UI: when the executor initiates a flash, the meaning picker shows only question‑phrased options (e.g., “Can I come?”, “Shall I proceed?”, “Is now okay?”). The receiver of that question (the superior) sees the same binary soldiers: ⚡ = yes/granted, ❌ = no/not now.

**Why this matters:** It preserves hierarchy without silencing the lower‑rank. The executor can still signal, but always with deference.

---

## 🕹️ Interaction: The Binary Soldiers

Flash uses spatial muscle memory. The response icons are always in the same place, whether the device is ringing or in the "Orb" state.

| State | Left Soldier (Negative) | Right Soldier (Positive) |
|-------|-------------------------|--------------------------|
| **Active Flash (Ringing)** | ❌ (Ground / End) | ⚡ (Return Pulse / Got it) |
| **Passive Orb (Settled)** | ❌ (Clear / Close) | ✔️ (Confirm / Acknowledge) |

**The Context Rule:** Because the context (the meaning) is displayed during the 8‑second ring, hitting the **Right Soldier** is a high‑confidence "Got it" to that specific intent.

**Melt Transition:** Tapping a soldier causes it to bloom outward then collapse as the Orb transitions to its final state – green bloom for positive, red bloom for negative.

**In‑pocket gestures:**
- Single back‑tap = ⚡ / ✔️ (positive reply)
- Double back‑tap = ❌ (negative reply)
- Uses native iOS back‑tap API and Android squeeze gesture.

---

## 🖼️ The Ambient Orb

Once a Flash is acknowledged or settles, it lives as an **Orb** – a submerged Profile Picture (DP) inside a glowing halo.

### Orb Colour States

| Orb Colour | State | Animation |
|------------|-------|------------|
| Gray (idle) | No active session | Static, low opacity |
| Gray (queued) | Offline / pending | Slow breath (3s) |
| Amber | Waiting for reply | Amber glow (2.2s) |
| Red | Flash 3 (urgent) | Pulse (1.1s) |
| Crimson | Flash 4 (critical) | Rapid strobe (0.65s) |
| Green | Got it / acknowledged | Flash & bloom |
| Purple / Pink / Teal | Warmth signal | Soft breath (2.8‑3.2s) |

### Submerged DP (four layers)

1. **Dynamic glow** – changes colour per state, knows nothing about identity.
2. **Frosted glass** – backdrop blur creates submerged quality.
3. **Identity ring** – thin border inheriting state colour.
4. **Quiet DP** – static, never animates, only opacity/saturation shifts.

> *The face never moves – only its presence shifts from sleeping to vivid.*  
> The brain registers identity and urgency in the same peripheral glance, under one second.

---

## 📱 Zero‑Banner Phone UI

- No slide‑down notifications.
- Always‑on Display (AOD) shows blurred Orb glow in session colour.
- Edge glow on lock screen visible from across a room.
- Dynamic Island carries live session dot (iOS).
- In‑pocket response via back‑tap (no screen needed).

---

## 🔁 Session Lifecycle (Action Signal)

| Flash | Colour | Haptic | Behaviour |
|-------|--------|--------|------------|
| **1 – normal** | Amber | Single short burst | 8s full‑screen, no DND override |
| **2 – noticed** | Deepening amber | Longer | Receiver sees this is a follow‑up |
| **3 – urgent** | Red | Double pulse | DP shakes. DND override if enabled. |
| **4 – critical** | Crimson | Triple pulse + white jolt | Session seals regardless of reply. Sender locked. Cooldown begins. |

**Session close conditions:**  
⚡/✔️ tap · ❌ tap · Signal expiry · Flash 4 no reply (critical seal) · Sender cancels before delivery.

**New session after critical:** Cooldown enforced by system. Next session opens neutral – amber, no carry‑over.

---

## 🌸 Warmth Signal – Full Specification

Warmth is a separate signal class for peer‑to‑peer, low‑pressure connection.

| Property | Warmth Value |
|----------|--------------|
| Hierarchy | Peer – neither side leads |
| Reply expected | Never required |
| Ringing phase | 8 seconds, soft purple/pink/teal glow |
| Left soldier | ··· (later – no rejection language) |
| Right soldier (ring) | ⚡ (felt it) |
| Right soldier (orb) | ✔️ (acknowledged) |
| Melt outcome | Soft purple fade (◎) |
| Escalation | One flash only – never re‑flashed |
| Session | Sessionless – lands and fades |
| History | Count only – no timestamps |
| Orb palette | Purple, pink, teal, blue (soft only) |
| DND override | Never |
| Daily limit | Configurable (default 3 per relationship) |

Warmth pings do **not** log timestamps. Only the fact that a warmth ping was sent and whether it was acknowledged (count) is recorded. This preserves the feeling of zero social debt.

---

## 📊 Offline & Unreachable States

| State | Condition | Sender sees | Expiry timer |
|-------|-----------|-------------|---------------|
| Queued | No data, phone on | “Flash queued” (faint tick) | Paused until delivery |
| Held | Phone off / no coverage | Hollow tick + held timestamp | Paused until delivery |
| DND active | Receiver in focus mode | DND icon + estimated window end | Running – flash waits |
| Expired | Context window closed | Expiry notice – session void | Triggered expiry |
| No reply | Delivered, reply window elapsed | “No reply” – re‑flash option | Running normally |

> Expiry timer always starts from **delivery time**, never send time. A queued flash is never penalised for the receiver’s offline period.

---

## 📜 History & Transparency (The Immutable Record)

Both parties hold an identical copy of every session.

### What is logged (Action signals)
- Timestamp of each flash (to the second)
- Gap between flashes (displayed in italic)
- Outcome (got it / decline / expired / critical seal)
- Reply timestamp (if any)

### What is logged (Warmth signals)
- Only count of flashes sent and acknowledged per day. No timestamps.

### History UI
- **Timeline tab:** Grouped by month. Colour bar on left. Tap to expand full flash‑by‑flash breakdown.
- **Stats tab:** Got it / declined / expired / critical totals. Response rate bar chart by month.
- **Meanings tab:** Current active meanings with effective dates. Full change history (previous wording + date). Neither party can dispute what the flash meant at any point.
- **Received tab:** Flashes sent to the user as receiver. Their reply record. Protects against false accusations.

### Ping‑back count (private to sender)
- Count of sessions where the receiver never replied and the sender marked as “ignored”.
- Visible only to the sender against that specific relationship.
- Informational, not punitive. Tells the sender: *this person has a pattern.*

---

## 🏷️ Contextual Badges

Badges add **context** (where, when) without adding **content** (new meaning). They sharpen the predefined message.

### Allowed badges (configured per relationship at setup)
- Location pin (GPS or selected place)
- ETA (5 / 10 / 30 minutes)
- Floor or room number
- Urgency flag (low / medium / high – maps to escalation)
- Time slot (e.g., “4pm”, “lunch”)

### Never allowed (would become messaging)
- Video, document, image, voice note, free text, link, emoji.

**Interaction:** Long‑press the flash button before sending → badge tray opens. One tap to attach. One badge per flash maximum. Badge appears alongside the predefined message on the receiver’s full‑screen takeover.

---

## ✏️ Post‑Acceptance Editing (How Relationships Evolve)

Relationships are not static. Settings can change over time.

### Rules for editing
- **Core meaning** (the flash’s phrase) – requires mutual agreement. If one side changes it, the other must accept. Notification: *“Amaka changed the meaning of your flash to ‘Come fix my hair’. Accept or decline.”*
- **Template type** (e.g., Colleague → Friend) – requires mutual agreement, because it changes signal class (action vs warmth) and all associated rules.
- **Personal settings** (reply window, expiry, DND override) – can be changed by either side without approval, but the other side receives a notification: *“Bello changed the reply window to 5 minutes.”* The change takes effect immediately.
- **Badge types** – can be added/removed by either side without approval (they only affect future flashes).

### How to edit
- From the relationship history view → “Settings” tab.
- Inline edit pills on any field.
- Changes that require mutual agreement show a “Propose change” button. The other side sees a notification and can accept/decline.

---

## 🗺️ The Roadmap (Absolute)

### Phase 1: The Core Protocol (ship now)
- High‑priority 8‑second "Flash Call" engine.
- Context‑visibility layer (Meaning + Identity).
- Provisional Flashing + Social Graph Auto‑Setup.
- Smart Templates (Colleague, Client, Friend, Family).
- Global Meaning Library.
- Binary Soldier UI & Melt transitions.
- Ambient Orb (all states, including warmth).
- Zero‑banner UI + edge glow.
- Back‑tap gestures + haptic breath.
- Asymmetric reverse flash (executor → superior question).
- Bilateral immutable history (timeline, stats, meanings, received).
- Contextual badges (allowed list + interaction).
- Post‑acceptance editing rules.
- Warmth signal full specification.

### Phase 2: OS Surface Layer
- Dynamic Island integration (iOS).
- Always‑on Display (AOD) persistent Orb.
- Apple Watch / Android Wear complications.
- Haptic Signature Library (professional vs. casual).

### Phase 3: Enterprise & B2B
- Multi‑Flash dashboards for operational centres (Clinics, Warehouses, Logistics).
- API for automated system‑to‑human Flashing.
- Relationship analytics (response rates, escalation patterns).

---

## 🚫 Discontinued Features (from v0.2 and earlier)

- **Physical Hardware (The Orb):** Discontinued. Flash lives entirely on existing mobile and wearable hardware to ensure immediate global adoptability.
- **Manual Negotiation:** Discontinued in favour of Provisional Flashing.
- **Custom Meaning Typing:** Replaced by Global Meaning Library.
- **Blank‑slate Setup:** Replaced by Smart Templates.

---

## ✨ Summary: What Makes Flash Different

- **No typing** – meanings come from a library.
- **No setup friction** – provisional mode + templates + social graph auto‑setup.
- **8‑second ringing call** – urgent but not intrusive.
- **Binary Soldiers** – icons only, spatial memory.
- **Ambient by design** – AOD, edge glow, Dynamic Island, haptic breath.
- **Provisional consent** – reply creates the relationship.
- **Asymmetric reverse flash** – executor can ask, never command.
- **Escalation by colour** – amber → red → crimson.
- **Full transparency** – bilateral immutable history.

> *“Communication shouldn't be a conversation when it only needs to be a Flash.”*

**Version:** v0.4  
**Status:** Ready for engineering handoff  
**Supersedes:** Nod v0.1, Flash v0.1, Flash v0.2, Flash v0.3, Readme
