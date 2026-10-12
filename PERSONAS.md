# Quick user personas

Working composites for the meeting-page redesign. They follow how [fellow.ai](https://fellow.ai/) describes its customers: a secure AI meeting assistant for organizations where privacy, security, and data governance matter most.

Industries in the site nav:

- **Financial services** — asset management, hedge funds, investment banking, private equity
- **Regulated industries** — healthcare and health tech, legal
- **Other** — agencies, fintech, software and IT

These are not interview findings. Each card is a plausible primary user of the meeting page, grounded in Fellow’s use-case pages. Compliance and IT often buy and constrain the product; the people below live in the meeting.

Related: [SPEC.md](SPEC.md) · [COMPETITORS.md](COMPETITORS.md) · [BUSINESS.md](BUSINESS.md)

---

## What they all need from the page

- A visible answer to “is this being recorded, who can see it, and can I stop it?”
- Pause that actually removes the off-the-record stretch, with participants notified.
- Capture without a bot on sensitive external calls. A bot in the room changes the conversation.
- The decision and the owner surviving after the recording is deleted.
- Ask Fellow answers limited to what this person is allowed to see.

Recording state, access, and retention belong on the meeting page. They are part of using the product, not an admin afterthought.

---

## Financial services

### 1. Aisha Rahman — private equity, senior associate

**Meetings:** LP calls, investment committee, diligence, quarterly portfolio reviews.  
**Job on the page:** Leave with a permissioned record of the decision, the commitment, and who owns the follow-up. Query a diligence call from last quarter without rereading it.  
**Will not accept:** A recap that travels outside the deal team, or a bot joining an LP or management call.  
**Page implication:** Series history and open commitments are the top of a recurring portco or LP meeting. Access (“deal team only”) is as visible as the title.

[Private equity](https://fellow.ai/use-cases/private-equity)

### 2. Jonah Ellison — hedge fund, research analyst

**Meetings:** Expert-network calls, broker calls, risk committee, desk portfolio reviews.  
**Job on the page:** Keep a supervised record of what an expert or broker actually said, with sensitive terms flagged, and keep another desk’s book out of his search.  
**Will not accept:** One shared library across the firm, or a transcript that still contains MNPI after review.  
**Page implication:** The note is a reviewable record. Redaction and “who this is walled from” sit next to the summary, not in settings.

[Hedge funds](https://fellow.ai/use-cases/hedge-funds)

### 3. Lena Voss — investment banking, associate

**Meetings:** Pitches, management presentations, diligence, deal-team syncs, commitment committee.  
**Job on the page:** Turn a long diligence day into findings the working group can use, still inside the information barrier.  
**Will not accept:** Notes visible to the public side, or a recording that starts because the wrong domain is on the invite.  
**Page implication:** The meeting shows which side of the wall it belongs to before anyone opens Ask Fellow. Recording can be blocked by participant, and that block is obvious.

[Investment banking](https://fellow.ai/use-cases/investment-banking)

### 4. Marcus Adeyemi — asset management, investor relations

**Meetings:** 10–20 investor touchpoints a week, investment committee, portfolio reviews.  
**Job on the page:** Walk out of a call with a recap in the firm’s note format and the commitment already pointed at the CRM. Catch an IC decision later even after the recording is gone.  
**Will not accept:** Typing through the call, or losing the decision when retention deletes the audio.  
**Page implication:** Follow-up is the primary after-meeting action. The summary persists as its own object when the recording does not.

[Asset management](https://fellow.ai/use-cases/asset-management)

---

## Regulated industries

### 5. Dr. Naomi Park — health tech, clinical operations lead

**Meetings:** Clinical huddles, ops syncs, board reviews, vendor calls that may include PHI.  
**Job on the page:** Accurate notes for the right people, with any slipped PHI gone for good.  
**Will not accept:** A transcript that retains patient details, or a recording the room did not know was running.  
**Page implication:** Pause and resume are first-class controls, and the page states that paused speech is absent from the note. Redaction is a direct action on the transcript.

[Healthcare and health tech](https://fellow.ai/use-cases/health-tech)

### 6. Elena Costa — law firm, litigation associate

**Meetings:** Client strategy, internal case reviews, expert calls, board advisory.  
**Job on the page:** A defensible record of decisions, owners, and topics, without putting privilege at risk.  
**Will not accept:** Ambiguous capture. Everyone in the room must know when recording stops and starts.  
**Page implication:** The note reads as a record — decisions, action items, topics — with the transcript as evidence underneath. Privilege and “off the record” are states of the meeting, not footnotes.

[Legal](https://fellow.ai/use-cases/legal)

---

## Other industries Fellow sells

### 7. Chris Dalton — fintech, product manager

**Meetings:** Product and engineering syncs, partnership calls, incident bridges, interviews.  
**Job on the page:** Decisions and owners land in Slack or the tracker the same day. Interview notes exist only as long as policy allows, with consent already logged.  
**Will not accept:** A consumer notetaker security will not approve, or a summary nobody reopens.  
**Page implication:** Open items from the last meeting are waiting at the top of the next one. Consent and retention are visible on external meetings, especially interviews.

[Fintech](https://fellow.ai/use-cases/fintech)

### 8. Sofia Nguyen — agency, account director

**Meetings:** Client status, creative reviews, onboarding a teammate onto an account.  
**Job on the page:** Client history organized by account, so someone who missed the call can act. Draft the follow-up without exposing another client’s work.  
**Will not accept:** A workspace where one client’s strategy is searchable by the whole agency.  
**Page implication:** The meeting’s home is the client channel. Ask Fellow is scoped to that account. Follow-up email is a primary action, as on a simple notetaker, with sharing still explicit.

[Agencies](https://fellow.ai/use-cases/agencies)

### 9. Rob Ibarra — software company, IT and security admin

**Meetings:** Security reviews, governance, vendor assessments. He also sets the rules everyone else lives under.  
**Job on the page:** Confirm that this meeting obeyed policy: who could record it, who can open the recap, how long it is kept. Stop shadow AI by making the approved tool the easy one.  
**Will not accept:** A polished page that hides recording, access, or retention, or a tool the company cannot govern.  
**Page implication:** Policy shows up as quiet status on the meeting — recording allowed, retention window, audience — so the daily user and the admin are looking at the same facts.

[Software and IT](https://fellow.ai/use-cases/it)

---

## Who to design for first

The meeting page has two jobs that have to succeed together.

| Priority | Persona | Why they lead |
| --- | --- | --- |
| Primary | Aisha, Lena, Elena | High-stakes, recurring, permissioned meetings. If the page is calm and precise here, it holds for everyone else. |
| Primary | Marcus, Chris | Highest meeting volume. Follow-through and “what’s still open” are the reason they stay. |
| Constraint | Naomi, Jonah, Rob | They define the floor: pause, redaction, walls, and visible policy. A simpler layout that hides these fails the buyer. |
| Reach | Sofia | Closest to the Granola expectation in the brief: client calls, fast follow-up, low tolerance for a noisy tool. |

The page should feel as quiet as a focused notes product, and still answer the regulated user’s first question: who can see this, and is it on the record?
