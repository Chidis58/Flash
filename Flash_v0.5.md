# Flash ⚡ v0.5

> **Note:** This specification is the absolute and definitive record of the Flash protocol. It supersedes and renders obsolete all previous documentation, including "README", "Nod", "Flash v0.1", "Flash v0.2", "Flash v0.3", and "Flash v0.4". No intermediate versions exist outside this document – v0.5 is the clean canonical record based on v0.2 and all subsequent feedback from Gemini, Claude, and Grok.

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

To solve the "Dual Consent" hurdle, Flash v0.5 introduces **Provisional Mode**.

- **Skip the Setup:** You do not need a pre‑negotiated relationship to send a Flash. You can Flash any contact immediately.
- **The Provisional Handshake:** The first Flash arrives with a "Provisional" tag. The receiver can reply with ⚡ (Got it) or ❌ (Decline) immediately.
- **Implicit Consent:** By responding to a Provisional Flash, the relationship is automatically created with sensible defaults (using templates – see below). There are no "Invite" or "Setup" screens – only action.
- **One‑Tap Acceptance from Lock Screen:** The receiver never needs to open the app to accept. The flash itself *is* the acceptance. Tapping the right soldier during the 8‑second ring instantly creates the relationship.

### Web‑Based Provisional Flashing (No App Required)

If the receiver does **not** have Flash installed:
- The flash is delivered as a rich SMS or WhatsApp message with a temporary web link.
- The web page shows the sender’s name, the meaning, and the two soldiers (⚡ / ❌).
- The receiver can reply via the web page – no installation required.
- After replying, the web page prompts: *“Install Flash for one‑tap replies next time.”* with a direct app store link.
- **Security:** The web link expires **24 hours** after the flash is sent. After expiry, the receiver sees: *“This flash link has expired. Ask [sender] to send another.”* The page is stateless – no personal data is ever stored.

### Flash‑as‑a‑WhatsApp‑Bot (Habit Inertia Mitigation)

To overcome the “everyone is already on WhatsApp” barrier:
- The first provisional flash can be sent **from within WhatsApp** using the Flash bot.
- Sender types `/flash @Bello Come here` in WhatsApp chat with the bot.
- Bot sends a rich message to Bello (with the soldiers).
- Bello replies via WhatsApp web view.
- **After the first successful reply**, the bot suggests installing the app: *“Install Flash for one‑tap replies and ambient Orb.”*
- The bot is a **door, not a home** – users are funnelled to the app after a single interaction.

### Social Graph Auto‑Setup (Privacy Guardrailed)

- Auto‑setup is **opt‑in** at the system level (user enables “Discover contacts on Flash”).
- For each suggested contact, Flash shows a **pre‑filled template proposal** with an **“Invite”** button – not an automatic relationship.
- User must explicitly tap “Invite” to send the provisional flash. Nothing is created automatically.

---

## 📋 Smart Templates & Meaning Library

To remove all setup friction, Flash uses **context templates** and a **fixed meaning library**.

### Templates (pre‑configured defaults)

| Template | Signal Type | Symmetry | Default Expiry | Reply Window | Max Flashes/Day | DND Override |
|----------|-------------|----------|----------------|--------------|-----------------|--------------|
| **Peer Request** | Action | Symmetric (request/offer) | 4 hours | 15 min | 5 (configurable) | Off |
| **Hierarchical** | Action | Asymmetric (command / question) | 2 hours | 10 min | 5 | Flash 3+ |
| **Client** | Action | Asymmetric | 2 hours | 10 min | 5 | Flash 3+ |
| **Friend** | Warmth | Symmetric | None | Optional | 3 (soft limit) | Never |
| **Family** | Action (soft) | Asymmetric | 24 hours | 30 min | 5 | Flash 4 only |

- **Peer Request (formerly Symmetric Action):** Any team member can flash a **request** (e.g., “Can you help with X?”). The receiver replies ⚡ = “yes, on it” or ❌ = “can’t right now”. No command meanings in the library for this template.
- **Hierarchical / Client / Family:** Asymmetric rules – superior → executor command; executor → superior question.
- **Family DND override:** Set to **Flash 4 only** – a critical, last‑resort override, not a routine escalation.

**Advanced Setup (for professional templates):**  
For Hierarchical and Client templates, the sender can choose **“Full setup”** instead of provisional. This opens the original 5‑step negotiation flow (hidden behind an “Advanced” button). Casual users never see it.

### Global Meaning Library (no typing for first 7 days + 5 flashes)

All meanings are pre‑defined, curated phrases. The sender picks one from a list. The receiver sees that exact phrase during the flash.

**Action meanings (command / request direction):**
- Come here
- I’m outside
- Ready when you are
- Urgent – please respond
- Check this
- Order ready
- Come fix my hair (example)

**Warmth meanings (expanded library – 10 phrases):**
- Thinking of you
- Home safe
- Just because
- I’m here if you need
- Miss you
- Good night
- Proud of you
- How are you holding up?
- Thinking of our trip
- You’ve got this

> Warmth library is fixed – no custom meanings ever. This preserves low pressure.

### Custom Meanings (for Peer Request, Hierarchical, Client, Family)

To address the “rigidity” concern, Flash allows **custom meanings** after a relationship is established, **only for Action templates** (Peer Request, Hierarchical, Client, Family). Warmth remains library‑only.

- **Threshold:** 7 days of active relationship **AND** at least 5 flashes total (both directions). Whichever comes later.
- **Professional templates (Hierarchical, Client):** Custom meanings are **never allowed** – only library. This preserves clarity in high‑stakes environments.
- **Proposal:** Sender taps “Propose custom meaning” → types up to 30 characters → sends to the other party.
- **Acceptance:** The other party sees the proposal and can **Accept** or **Decline**.
- **If accepted:** The custom meaning replaces the library meaning for all future flashes (until changed again).
- **If declined:** The library meaning remains. The proposer can try again after 7 days.
- **History:** All custom meaning changes are logged in the Meanings tab (previous wording + date).

---

## 🔄 Asymmetric Reverse Flash (Executor → Superior)

For **Asymmetric Action** templates (Hierarchical, Client, Family), the relationship is **not one‑way**. The executor (the person who receives commands) can flash back, but **their flash is always a question or request, never a command**.

- **Superior → Executor:** “Come to my office.” (command)
- **Executor → Superior:** “Can I come to your office now?” (question)
- **Superior replies:** ⚡ (yes / got it) or ❌ (no / decline)

This is enforced by the UI: when the executor initiates a flash, the meaning picker shows only question‑phrased options (e.g., “Can I come?”, “Shall I proceed?”, “Is now okay?”).

**For Peer Request templates:** Both sides send requests (not commands). Reverse flash is also a request.

---

## 🕹️ Interaction: The Binary Soldiers

Flash uses spatial muscle memory. The response icons are always in the same place, whether the device is ringing or in the "Orb" state.

| State | Left Soldier (Negative) | Right Soldier (Positive) |
|-------|-------------------------|--------------------------|
| **Active Flash (Ringing)** | ❌ (Ground / End) | ⚡ (Return Pulse / Got it) |
| **Passive Orb (Settled)** | ❌ (Clear / Close) | ✔️ (Confirm / Acknowledge) |

**The Context Rule:** Because the context (the meaning) is displayed during the 8‑second ring, hitting the **Right Soldier** is a high‑confidence "Got it" to that specific intent.

**Melt Transition:** Tapping a soldier causes it to bloom outward then collapse as the Orb transitions to its final state – green bloom for positive, red bloom for negative.

**Progressive Disclosure (Learning Curve Mitigation):**
- **First flash sent** – one‑time overlay explaining soldiers (❌ left, ⚡ right).
- **First incoming flash** – similar overlay.
- **First time the orb appears** – brief tooltip: “This amber glow means they’re waiting. Tap to reply.”
- **No upfront tutorial** – learn by doing, with contextual hints.
- **Settings screen** has a “How Flash works” animation (skippable).

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
| Custom meanings | Not allowed (library only – expanded to 10 phrases) |

Warmth pings do **not** log timestamps. Only the fact that a warmth ping was sent and whether it was acknowledged (count) is recorded.

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

### Ping‑Back Count (Private to Sender, Opt‑In, Grace Period)

The ping‑back count tracks how many sessions were **ignored** (delivered but no reply, and sender believes it was intentional).

**Rules:**
- **Off by default** for personal templates (Friend, Family, Peer Request). User must manually enable in relationship settings.
- **On by default** for professional templates (Hierarchical, Client). Either party can disable it.
- **Grace period:** A session is only marked as “ignored” after **three consecutive no‑reply sessions** (configurable per relationship). A single missed reply does not increment the count – only a pattern.
- The count is visible **only to the sender** against that specific relationship.
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
- **Template type** (e.g., Peer Request → Hierarchical) – requires mutual agreement, because it changes symmetry rules.
- **Personal settings** (reply window, expiry, DND override, max flashes/day) – can be changed by either side without approval, but the other side receives a notification: *“Bello changed the reply window to 5 minutes.”* The change takes effect immediately.
- **Badge types** – can be added/removed by either side without approval (they only affect future flashes).

### How to edit
- From the relationship history view → “Settings” tab.
- Inline edit pills on any field.
- Changes that require mutual agreement show a “Propose change” button. The other side sees a notification and can accept/decline.

---

## 👥 Group Flashes (Network Effects Mitigation)

To accelerate adoption in tight‑knit groups:

- **Family group flash:** One parent sets up a “Family” group. All members get the same meaning library (e.g., “Home safe”, “Dinner ready”). Any member can flash the whole group with one tap.
- **Workplace team flash:** Manager creates a team, pre‑assigns templates. New hires are auto‑added.

### Session Behaviour for Group Flashes

- A group flash creates **one shared session** for the entire group, not individual sessions.
- The sender sees a **live roll‑up** of replies:
  - ⚡ count (got it)
  - ❌ count (decline)
  - Pending count (no reply yet)
- **Escalation applies per‑person** – the sender can re‑ping the whole group, but individuals who have already replied are not re‑flashed.
- The session closes when:
  - All members have replied (⚡ or ❌), **or**
  - The expiry window passes (global per‑session timer).
- Critical lock (Flash 4) applies per‑person – a member who ignores four group flashes is individually locked from receiving further flashes in that session, but the group session continues for others.

### Viral Invite Mechanic

- After 5 flashes with a contact, both get a notification: *“You’ve flashed 5 times. Invite a friend to Flash and get a free week of [premium feature].”*

---

## 🗣️ Voice PTT Differentiation (Competition Mitigation)

Flash does not compete directly with voice walkie‑talkie apps (Zello, Voxer). Instead, it complements them:

- **Marketing differentiation:** “Flash is silent. No one else hears your coordination.”
- **Optional voice‑to‑flash (Phase 2):** “Hey Siri, flash Bello ‘I’m outside’.” – voice triggers a flash, but the output is still silent.
- **Hybrid positioning:** In a noisy warehouse, use PTT for urgent voice, Flash for non‑urgent status (e.g., “Bay 3 ready”).

---

## 🗺️ The Roadmap (Absolute)

### Phase 1: The Core Protocol (ship now)
- High‑priority 8‑second "Flash Call" engine.
- Context‑visibility layer (Meaning + Identity).
- Provisional Flashing + Social Graph Auto‑Setup + Web‑based provisional flashing (24h expiry).
- Flash‑as‑a‑WhatsApp‑bot (first flash inside WhatsApp, then prompt install).
- Smart Templates (Peer Request, Hierarchical, Client, Friend, Family).
- Global Meaning Library (expanded warmth: 10 phrases) + custom meanings after 7 days + 5 flashes (Action only, not for professional).
- Binary Soldier UI & Melt transitions.
- Progressive disclosure (contextual tooltips, no upfront tutorial).
- Ambient Orb (all states, including warmth).
- Zero‑banner UI + edge glow.
- Back‑tap gestures + haptic breath.
- Asymmetric reverse flash (for Hierarchical) + Peer Request symmetric.
- Bilateral immutable history (timeline, stats, meanings, received).
- Contextual badges (allowed list + interaction).
- Post‑acceptance editing rules.
- Warmth signal full specification.
- Ping‑back count (opt‑in, grace period).
- Group flashes (family, team) with explicit session behaviour.
- Viral invites.

### Phase 2: OS Surface Layer
- Dynamic Island integration (iOS).
- Always‑on Display (AOD) persistent Orb.
- Apple Watch / Android Wear complications.
- Haptic Signature Library (professional vs. casual).
- Voice‑to‑flash (Siri / Google Assistant).

### Phase 3: Enterprise & B2B
- Multi‑Flash dashboards for operational centres (Clinics, Warehouses, Logistics).
- API for automated system‑to‑human Flashing.
- Relationship analytics (response rates, escalation patterns).

---

## 🚫 Discontinued Features (from v0.2 and earlier)

- **Physical Hardware (The Orb):** Discontinued. Flash lives entirely on existing mobile and wearable hardware.
- **Manual Negotiation as default:** Replaced by Provisional Mode; preserved as optional “Advanced setup” for professional templates.
- **Blank‑slate Setup:** Replaced by Smart Templates.
- **“Urgent – call me” meaning:** Removed; replaced with “Urgent – please respond”.

---

## ⚠️ Strategic Note on Competition

Apple or Google could theoretically copy the ambient orb + Dynamic Island visual in an OS update. However, Flash’s moats are:
- **Cross‑platform** – Apple will never build an Android‑compatible orb.
- **Protocol, not feature** – The entire lifecycle (escalation, templates, provisional mode, bilateral history) is complex. A copied orb is just a visual – it doesn’t include the behavioural rules.
- **B2B enterprise** – Phase 3 (dashboards, API) is much harder for OS vendors to justify building.
- **Voice PTT differentiation** – Flash is silent, discreet, and leaves a record.

**Therefore:** Prioritise Phase 2 (OS integrations) and Phase 3 (enterprise) aggressively. The consumer app is the wedge, not the castle.

---

## ✨ Summary: What Makes Flash Different

- **No typing for first 7 days + 5 flashes** – library only; customisation earned through time and use (Action only).
- **No setup friction** – provisional mode + templates + social graph auto‑setup + web‑based replies + WhatsApp bot.
- **8‑second ringing call** – urgent but not intrusive.
- **Binary Soldiers** – icons only, spatial memory.
- **Ambient by design** – AOD, edge glow, Dynamic Island, haptic breath.
- **Provisional consent** – reply creates the relationship.
- **Two action modes** – Peer Request (symmetric) and Hierarchical (asymmetric).
- **Asymmetric reverse flash** – executor can ask, never command.
- **Escalation by colour** – amber → red → crimson.
- **Full transparency** – bilateral immutable history.
- **Ping‑back count** – opt‑in, grace period, private to sender.
- **Warmth with expanded library (10 phrases)** – low pressure, no customisation.
- **Group flashes** – one shared session, live roll‑up, per‑person escalation.

> *“Communication shouldn't be a conversation when it only needs to be a Flash.”*

**Version:** v0.5 (final)  
**Status:** Ready for engineering handoff  
**Supersedes:** All previous versions (README, Nod v0.1, Flash v0.1, v0.2, v0.3, v0.4)
```

---
 Siri, flash Bello ‘I’m outside’.” – vo
