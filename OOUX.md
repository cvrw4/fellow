# OOUX model — desktop meeting page

A short object model for the meeting page in [SPEC.md](SPEC.md). The page is one object, a **Meeting**, with a few nested objects. Jobs to be done come from what a person does to those objects, and from how the objects depend on each other.

Related: [PERSONAS.md](PERSONAS.md) · [BUSINESS.md](BUSINESS.md) · [COMPETITORS.md](COMPETITORS.md)

---

## Pillars

The chain “user → meeting → transcription → notes → to-do lists” mixes roles, objects, and collections. On this page the objects are:

| Pillar | What it is | What it is not |
| --- | --- | --- |
| **Meeting** | The page. A scheduled conversation with a purpose, a time, an audience, and a record. | A transcript, a note, or a calendar row. The calendar only points at it. |
| **Person** | Someone who attends, owns work, or is allowed to see the record. Includes the current user. | A “user” object the page is about. The page is about the meeting. |
| **Talking point** | One thing the room intended to discuss. | A note, and not an action item. |
| **Note** | What was written or generated: the notepad, and the AI note once it exists. Decisions live here until they are their own object. | The transcript. |
| **Action item** | One commitment: owner, scope, deadline, status. | A to-do list. The list is just the action items on this meeting. |
| **Transcript** | The evidence of what was said, tied to time and speaker. | The product. It can be deleted while the note and the commitments remain. |

**Recording** is a state of the Meeting, not its own pillar. It has actions (start, pause, resume, stop), and it is what produces the Transcript. **Series** is a relationship between Meetings, not a seventh object. **Ask Fellow** is an action on the Meeting that reads the other objects. It does not own content of its own.

A decision is the durable part of the Note: what was decided, why, and who approved it. The page should treat it as a block inside the Note that survives after the Transcript is gone. Making Decision its own pillar is a later product move, called out in [BUSINESS.md](BUSINESS.md). This model keeps it inside Note so the page does not grow a new section.

---

## Meeting

The container. Opening a meeting is opening this object.

**Attributes that matter on the page:** title, when, series, video link, recording state, who can see it, favorite, unread changes, response (accepted, declined, not accepted, cancelled).

**Actions**

| Action | Touches |
| --- | --- |
| Open, favorite, share, copy link | Person (audience) |
| Join the call | Video provider, outside the note |
| Start, pause, resume, or stop recording | Transcript. Pause removes that stretch from the Transcript and the Note. |
| See who can view the recap | Person |
| Ask Fellow, scoped to this meeting | Talking point, Note, Action item, prior Meeting, Transcript |
| Jump to the previous meeting in the series | Meeting |

**Relationships:** has many Talking points, one working Note, many Action items, zero or one Transcript, many People, and zero or more prior Meetings in the same series.

---

## Person

**Attributes:** name, avatar, role in this meeting (attendee, owner, absent), whether they can see the record.

**Actions on this page:** see who is here, assign an Action item to someone, share or restrict the Meeting, mention someone in Ask Fellow.

**Relationships:** attends a Meeting, owns Action items, authors parts of the Note, is named in the Transcript. Access is a relationship between a Person and a Meeting, not a setting buried elsewhere.

---

## Talking point

**Attributes:** text, author, done or not, order.

**Actions:** add, edit, reorder, check off, turn into an Action item.

**Relationships:** belongs to one Meeting. Often comes from the prior Meeting’s open Action items or unanswered questions. Checking one off does not create a commitment. That is a separate action.

---

## Note

**Attributes:** body (notepad), AI note once generated, decisions inside it, link back to a moment in the Transcript. The AI note on this page is three parts of the same meeting: a summary, the human-level note, and nothing that belongs to another meeting.

**Actions:** write, generate from the Transcript, edit, copy, draft a follow-up (email or update). Generating reads the Transcript and should not invent Action items that nobody confirms.

**Relationships:** belongs to one Meeting. Cites the Transcript while the Transcript exists. Outlives the Transcript under retention. Feeds the next Meeting in the series.

---

## Action item

**Attributes:** title, owner (Person), deadline, status (suggested, confirmed, done, blocked), source meeting.

**Actions:** add by hand, accept or dismiss a suggestion, assign, set a deadline, complete, carry into the next Meeting.

**Relationships:** belongs to one Meeting, is owned by one Person, may cite a Transcript moment, and reappears on the next Meeting in the series if it is still open. Pushing it to Jira, Linear, Asana, or a similar tool is a consequence of confirming it, not a separate object on this page.

A suggested item is not a commitment. Confirming it is the action that matters.

---

## Transcript

**Attributes:** text, speakers, timestamps, redactions.

**Actions:** open, search, jump to a moment, redact, follow a citation from the Note or an Action item.

**Relationships:** produced by recording the Meeting, names People, supports the Note and Action items as evidence. Optional on the page. Required only when someone is checking a claim or removing sensitive content.

---

## How the objects connect

```
Person ──attends / can see──▶ Meeting ──in series──▶ Meeting
                                │
                                ├── has ▶ Talking point ──may become──▶ Action item
                                ├── has ▶ Note ──cites──▶ Transcript
                                ├── has ▶ Action item ──owned by──▶ Person
                                └── recording produces ▶ Transcript
```

The only loop that makes Fellow different from a notetaker: an open **Action item** and the **Note** from the last **Meeting** become the **Talking points** of the next one. The Transcript is an input to that loop, then drops out when policy deletes it.

---

## What this page has to carry

Everything else can be one step away. These are the actions the desktop meeting view itself has to offer, because the relationship breaks if the person has to leave.

| Moment | On the page | One step away |
| --- | --- | --- |
| Before | Prior Meeting’s open Action items and last decisions, as Talking points. Who can see this. Whether it will be recorded. | Full Transcript of last time. Library. |
| During | Write the Note. Check a Talking point. Capture a confirmed Action item. Pause recording. | Transcript playback. Ask Fellow history. |
| After | Read the Note, confirm Action items, draft the follow-up, see the audience. | Transcript, redaction, the global Action Items destination. |

Search, notifications, the Library, and the standalone Action Items page stay in the chrome. They are other views of the same objects, and they are out of scope as screens.

---

## JTBD

Narrowed to this page. Each job names the objects it uses, so a layout that hides one of them fails the job.

### 1. Walk in ready

When I open a recurring meeting, I want the unfinished commitments and the last decision in front of me, so I can start from the work rather than from a blank agenda.

Objects: Meeting, prior Meeting, Action item, Note, Talking point.  
The page fails if series context is a card I have to go find, or if suggested tasks and confirmed ones look the same.

### 2. Stay in the conversation

When the meeting is happening, I want one place to write and a way to mark what we actually agreed, so I can participate without managing three equal sections and a side panel.

Objects: Note, Talking point, Action item, Meeting (recording state).  
Talking points and action items are actions on the note, not peer layouts. Ask Fellow is a mode of the Meeting, summoned when needed.

### 3. Know what is on the record

When a conversation is sensitive, I want to see whether we are recording, who will be able to read the result, and how to stop capture, so I can keep using the tool in a room that cannot tolerate a surprise.

Objects: Meeting, Person, Transcript.  
Pause, audience, and recording state sit on the Meeting. They are not admin-only. This is the floor in [PERSONAS.md](PERSONAS.md).

### 4. Leave with owners

When the meeting ends, I want each next step confirmed with a person and a deadline, and the decision kept even if the audio is deleted, so the meeting changes what happens next.

Objects: Action item, Person, Note, Transcript.  
The Transcript supports the claim. The Note and the confirmed Action item are what remain. Follow-up (email, CRM, doc) is a single action on the Note, not a new object.

### 5. Ask without leaving

When I am missing context, I want to ask about this meeting and its series and get an answer I am allowed to see, so I do not hunt the Transcript or open another tool.

Objects: Meeting, and whatever the question needs (Note, Action item, prior Meeting, Transcript).  
The answer is scoped to this Meeting and this Person’s access. A general chat is a different product.

---

## What the model leaves out on purpose

- Configuring org-wide retention, SSO, and information barriers. The page shows the result of those policies on this Meeting.
- The Library and the global Action Items list. Same objects, different views, other pages.
- Decision as a standalone object, scheduling, and CRM write-back as their own screens. They show up here only as a block in the Note, a video link, and a confirmed Action item.
