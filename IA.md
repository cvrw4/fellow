# Information architecture

How someone finds a meeting, before they are on the meeting page in [OOUX.md](OOUX.md). The page is still one object, a **Meeting**. This note is about what that meeting sits under, and which view is allowed to show it.

Related: [JOURNEY.md](JOURNEY.md) · [PERSONAS.md](PERSONAS.md) · [SPEC.md](SPEC.md)

---

## Decision

A meeting belongs under a **relationship**: a client, a company, or a contact. That relationship is the row in a chat list. The meeting is an item inside the row, the way a message sits inside a thread.

The calendar does not own the meeting. It only places the same meetings in time, and it comes after the list. Time is a view. The relationship is the home.

Two time surfaces stay separate:

| Surface | Job | What it contains |
| --- | --- | --- |
| **Day** | What to do now | Today, the next meeting, things to do, notes |
| **Calendar** | When meetings happen | Meetings only |

The day is operational. The calendar is a schedule. Notes and commitments do not move onto the calendar to make it more useful. If they did, the calendar would become a second meeting page, and the chat list would stop being the place work is grouped.

---

## Why the meeting sits under the relationship

The current meeting page already knows a meeting has a series, an audience, and open work that must not leak into the next unrelated call. [JOURNEY.md](JOURNEY.md) runs that rule twice in one day: Helios diligence and the Northbridge LP call share a Tuesday and share nothing else.

A calendar grouped by day puts those two meetings on the same list because they share a clock. A chat list grouped by relationship puts them in different threads because they share a party. The second grouping is the one the product is for.

| Persona | The row they need | What must not share a thread |
| --- | --- | --- |
| Aisha, private equity | The company: Helios, Northbridge | A diligence finding on an LP call |
| Marcus, investor relations | The investor | Another LP’s commitment |
| Sofia, agency | The client account | Another client’s strategy |
| Elena, litigation | The client or the matter | Another matter’s record |
| Jonah, hedge fund | The expert or the broker, inside his wall | Another desk’s book |

People on the invite stay **Person** on the meeting, as in the object model. They do not each become a parent. A meeting with six attendees is one thread, under the party the work is about. Putting it under every attendee would make the list a directory and would copy the note into rooms that cannot see it.

When there is no external party, the recurring series is the row: investment committee, a 1:1, a product sync. The list does not invent a company to satisfy the grouping.

One meeting has one home. If two external parties are on the invite, the home is the party the note and the follow-up belong to. The other people remain attendees.

---

## The three surfaces

Navigation order follows the decision: relationship first, then the day, then the calendar.

```
Chat list                         Day                         Calendar
(relationships)                   (now)                       (meetings in time)

Today                          →  Tue 13
Helios Capital                    Next: Helios diligence 10:00
Northbridge                       Things to do
Daniel Cho                        Notes
Investment committee
                                  opens a Meeting  →          week / month
                                                              meetings only
```

**Today** is pinned at the top of the chat list. It opens the day. It is not a relationship.

Everything under it is a relationship row: name, the next meeting or the last activity, and a count of what is still open. Opening the row opens that thread: the meetings with that client, company, or contact, newest relevant first, series kept together inside the thread.

**Calendar** is a destination after the list, not the list itself. Opening it replaces the day with a schedule. Selecting a meeting there still opens the Meeting page. It does not open a second copy of the agenda.

---

## Chat list

The list is the library of relationships, in the shape of a conversation list.

**A row shows:** the party’s name, when you next meet them or when the thread last changed, and whether something is unread or still open.

**A row does not show:** the transcript, the notepad, or every action item. Those live on the Meeting, or as a short line on the day.

**Inside the thread:**

| In the thread | Belongs here because |
| --- | --- |
| Meetings with this party | The meeting’s home is this relationship |
| Series inside the party | Helios diligence and a Helios management interview are one company and two series |
| Open commitments for this party | They become the next meeting’s talking points, and only inside this thread |
| Ask Fellow, when opened from here | Scoped to this relationship and to what this person may see |

Search still finds a meeting by title. The result lands in the thread it belongs to, not in a flat calendar result.

Unread, recording, and “will be recorded” are states of a meeting inside the thread. The row can carry one of those states so the list is enough to see that Helios is live. The row does not grow a legend of icons. One status is enough until the thread is open.

---

## Day

The day is what Aisha has at 8:40, before she opens either meeting. It is the operational home, reached from **Today** at the top of the list.

| Block | What it is | What it is not |
| --- | --- | --- |
| **Today** | The date, and the shape of the day: how many meetings, which relationships | A week grid |
| **Next meeting** | The single meeting that is about to happen, named with its relationship | The whole agenda |
| **Things to do** | Open commitments that are due, overdue, or waiting on the next session | A second Action Items product. The global list stays one step away, as in the object model |
| **Notes** | Notes that changed, or that the next meeting will need | The notepad of every meeting on the day |

Each line on the day names its relationship. “Pull the margin comments” is a Helios line. “Send the portfolio update” is a Northbridge line. The day may show both, because both are hers today. It may not present them as one agenda.

Opening a line opens the Meeting, inside its thread. The day does not become the place the note is written. Writing still happens on the meeting page.

A quiet day is a short day: the next meeting, and little or nothing under things to do. It does not fill itself with calendar chrome to look occupied.

---

## Calendar

The calendar is the full schedule. It shows meetings and nothing else.

**On the calendar:** title, when, relationship, response (accepted, declined, not accepted, cancelled), recording state, unread. Days can be busy or empty. The current time can mark now.

**Off the calendar:** talking points, action items, the notepad, series recaps, Ask Fellow, and “things to do.” Those stayed on the day or on the meeting. Putting them here would rebuild the dense agenda column the meeting page is trying to leave behind.

The calendar can switch day, week, and a wider range. The day view is not the calendar’s day mode. The day view is a different surface with a different job. A calendar day is a list of meetings in order. The day view is next, tasks, and notes.

Grouping on the calendar is by time. Relationship is a label on the row so Tuesday’s two calls are visibly Helios and Northbridge. It is not a second grouping axis. If someone wants every Helios meeting, they open the Helios thread.

---

## What each job uses

The five jobs from the object model, and where they start. The meeting page still finishes them.

| Job | Starts on | Then |
| --- | --- | --- |
| Walk in ready | **Day**, for what is mine today. **Thread**, for what this party still has open | The Meeting, with prior commitments already the talking points |
| Stay in the conversation | The Meeting | The list only to see that this thread is the one recording |
| Know what is on the record | The Meeting | The thread’s name is the audience hint; the page still states who can see it |
| Leave with owners | The Meeting | The new commitment shows on the day, labeled with this relationship, and on the next meeting in this thread only |
| Ask without leaving | The Meeting, or the thread | Never across threads. A question asked from Helios cannot answer from Northbridge |

---

## What this leaves where it was

- **Meeting** stays the page. Client, company, and contact are how meetings are grouped, not a replacement for the meeting object.
- **Series** stays a relationship between meetings. Inside a thread it keeps diligence with diligence. It is the row only when there is no external party.
- **Library** and the global **Action Items** list stay other views of the same objects, one step away, out of scope as screens.
- **Person** stays an attendee, an owner, or an audience. A contact who is the party the work is about is the row. A contact who was simply invited is not.
