# Flash ⚡ v0.3

> **Note:** This specification is the absolute and definitive record of the Flash protocol. It supersedes and renders obsolete all previous documentation, including "Nod" and "Flash v0.1/v0.2."

**Flash** is an ambient communication layer designed for zero‑latency coordination. It is a "Short‑Pulse" protocol that behaves like a phone call but carries the lightweight intent of a message. It is designed specifically for high‑speed environments where looking at a screen to read a long chat is impossible.

---

## ⚡ The Core Logic: The "Flash Call"

A Flash is not a notification; it is a **Life Event** on the device.

1. **The 8‑Second Ring:** When a Flash is sent, the receiver’s device enters a "Ringing" state for exactly 8 seconds.
2. **Context‑First Display:** Unlike a standard call, the **Reason (Meaning)** for the Flash is visible immediately. The user sees the sender's identity and the intent (e.g., "I'm Outside" or "Order Ready") at the same time.
3. **The Behaviour:** It functions like a WhatsApp pop‑up message but with the urgency and audio/haptic priority of a phone call. 8 seconds is the optimal window for the brain to perceive, read the context, and act.
4. **Auto‑Settle:** If no action is taken during the 8 seconds, the "Call" settles into a quiet, breathing **Ambient Orb** on the screen.

---

## 🤝 Provisional Flashing (Zero‑Friction Onboarding)

To solve the "Dual Consent" hurdle, Flash v0.3 introduces **Provisional Mode**.

- **Skip the Setup:** You do not need a pre‑negotiated relationship to send a Flash. You can Flash any contact immediately.
- **The Provisional Handshake:** The first Flash arrives with a "Provisional" tag. The receiver can reply with ⚡ (Got it) or ❌ (Decline) immediately.
- **Implicit Consent:** By responding to a Provisional Flash, the relationship is automatically created with sensible defaults (using templates – see below). There are no "Invite" or "Setup" screens – only action.
- **One‑Tap Acceptance from Lock Screen:** The receiver never needs to open the app to accept. The flash itself *is* the acceptance. Tapping the right soldier during the 8‑second ring instantly creates the relationship.

---

## 📋 Smart Templates & Meaning Library

To remove all setup friction, Flash uses **context templates** and a **fixed meaning library**.

### Templates (pre‑configured defaults)

| Template | Signal Type | Default Expiry | Reply Window | Max Pings/Day | DND Override |
|----------|-------------|----------------|--------------|---------------|--------------|
| **Colleague** | Action | 4 hours | 15 min | 3 | Off |
| **Client** | Action | 2 hours | 10 min | 5 | Ping 3+ |
| **Friend** | Warmth | None | Optional | 3 (soft limit) | Never |
| **Family** | Action (soft) | 24 hours | 30 min | 5 | Ping 3+ |

The sender picks a template when flashing someone for the first time. The receiver sees the template name during the 8‑second ring.

### Global Meaning Library (no typing)

All meanings are pre‑defined, curated phrases. The sender picks one from a list. The receiver sees that exact phrase during the flash.

**Action meanings:**
- Come here
- I’m outside
- Ready when you are
- Urgent – call me
- Check this
- Order ready
- Come fix my hair (example for hairdresser context)

**Warmth meanings:**
- Thinking of you
- Home safe
- Just because
- I’m here if you need

> No custom text entry. Ever. This is what makes Flash instant.

---

## 🕹️ Interaction: The Binary Soldiers

Flash uses spatial muscle memory. The response icons are always in the same place, whether the device is ringing or in the "Orb" state.

| State | Left Soldier (Negative) | Right Soldier (Positive) |
|-------|-------------------------|--------------------------|
| **Active Flash (Ringing)** | ❌ (Ground / End) | ⚡ (Return Pulse / Got it) |
| **Passive Orb (Settled)** | ❌ (Clear / Close) | ✔️ (Confirm / Acknowledge) |

**The Context Rule:** Because the context (the meaning) is displayed during the 8‑second ring, hitting the **Right Soldier** is a high‑confidence "Got it" to that specific intent.

**Melt Transition:** Tapping a soldier causes it to bloom outward then collapse as the Orb transitions to its final state – green bloom for positive, red bloom for negative.

---

## 🖼️ The Ambient Orb

Once a Flash is acknowledged or settles, it lives as an **Orb** – a submerged Profile Picture (DP) inside a glowing halo.

| Orb Colour | State | Animation |
|------------|-------|-----------|
| Gray (idle) | No active session | Static, low opacity |
| Gray (queued) | Offline / pending | Slow breath (3s) |
| Amber | Waiting for reply | Amber glow (2.2s) |
| Red | Ping 3 (urgent) | Pulse (1.1s) |
| Crimson | Ping 4 (critical) | Rapid strobe (0.65s) |
| Green | Got it / acknowledged | Flash & bloom |
| Purple/Pink/Teal | Warmth signal | Soft breath (2.8‑3.2s) |

**Submerged DP (four layers):**
1. Dynamic glow – changes colour per state, knows nothing about identity.
2. Frosted glass – backdrop blur creates submerged quality.
3. Identity ring – thin border inheriting state colour.
4. Quiet DP – static, never animates, only opacity/saturation shifts.

> *The face never moves – only its presence shifts from sleeping to vivid.*  
> The brain registers identity and urgency in the same peripheral glance, under one second.

---

## 📱 Zero‑Banner Phone UI

- No slide‑down notifications.
- Always‑on Display (AOD) shows blurred Orb glow in session colour.
- Edge glow on lock screen visible from across a room.
- Dynamic Island carries live session dot (iOS).
- In‑pocket response: single back‑tap = ⚡/✔️, double back‑tap = ❌ (native iOS/Android gestures).

---

## 🔄 Session Lifecycle (Action Signal)

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

## 🗺️ The Roadmap (Absolute)

### Phase 1: The Core Protocol (ship now)
- High‑priority 8‑second "Flash Call" engine.
- Context‑visibility layer (Meaning + Identity).
- Provisional Flashing logic.
- Smart Templates (Colleague, Client, Friend, Family).
- Global Meaning Library.
- Binary Soldier UI & "Melt" transitions.
- Ambient Orb (all states).
- Zero‑banner UI + edge glow.
- Back‑tap gestures for in‑pocket response.
- Bilateral immutable history.

### Phase 2: OS Surface Layer
- Dynamic Island integration (iOS).
- Always‑On Display (AOD) persistent Orb.
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
- **No setup friction** – provisional mode + templates.
- **8‑second ringing call** – urgent but not intrusive.
- **Binary Soldiers** – icons only, spatial memory.
- **Ambient by design** – AOD, edge glow, Dynamic Island.
- **Provisional consent** – reply creates the relationship.
- **Escalation by colour** – amber → red → crimson.

> *“Communication shouldn't be a conversation when it only needs to be a Flash.”*

**Version:** v0.3  
**Status:** Ready for engineering handoff  
**Supersedes:** Nod v0.1, Flash v0.1, Flash v0.2
