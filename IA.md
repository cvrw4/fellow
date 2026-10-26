# Information architecture

How someone finds a meeting, before they are on the meeting page in [OOUX.md](OOUX.md). The page is still one object, a **Meeting**. This note is about what that meeting sits under, and which view is allowed to show it.

Related: [JOURNEY.md](JOURNEY.md) · [PERSONAS.md](PERSONAS.md) · [SPEC.md](SPEC.md)

---

## The account

A user belongs to a **Team**. The Team is their company, their organization, or headquarters. The user's name sits under the Team.

The Team is on a plan.

| Plan | The Team |
| --- | --- |
| **Individual** | One person. The name still belongs to the Team. |
| **Enterprise** | The company. Every name on the account belongs to that Team. |

The workspace switcher is this Team. Acme Co is the Team. Aisha Rahman is a name under Acme Co.

The left panel is four destinations: **Home**, **Meetings**, **Calendar**, and **Atlas**. There is no chat list.

Meetings is who that Team meets. Helios is a company in that list. Acme Co is the account those meetings live in. An internal series, such as investment committee, is its own group. The list does not use the Team's name as that group.

---

## Decision

The full calendar is too much to see at once. Home takes that load off. It shows what is on the agenda today, and leaves the rest of the schedule for the calendar.

| Surface | Job | What it contains |
| --- | --- | --- |
| **Home** | Today's agenda | Things to do, follow ups, updates |
| **Meetings** | The work, by company | Meetings grouped under a client, a company, or a contact |
| **Calendar** | The whole schedule | The calendar view, and scheduling a meeting. Meetings in time, nothing else |
| **Atlas** | Questions and insights | One company or one meeting at a time |

A meeting still belongs under a **relationship**: a client, a company, or a contact. That grouping is inside **Meetings**. It is not a fifth item in the left panel, and it is not a chat. Home is the day.

The calendar does not own the meeting. It places the same meetings in time, and it is where a meeting is scheduled. Notes, follow ups, and Atlas do not move onto the calendar. If they did, the calendar would become a second home.

---

## Why the meeting sits under the relationship

The current meeting page already knows a meeting has a series, an audience, and open work that must not leak into the next unrelated call. [JOURNEY.md](JOURNEY.md) runs that rule twice in one day: Helios diligence and the Northbridge LP call share a Tuesday and share nothing else.

A calendar grouped by day puts those two meetings on the same list because they share a clock. Meetings grouped by relationship keeps them apart because they share a party. The second grouping is the one the product is for.

| Persona | Where the meeting belongs | What must stay separate |
| --- | --- | --- |
| Aisha, private equity | The company: Helios, Northbridge | A diligence finding on an LP call |
| Marcus, investor relations | The investor | Another LP’s commitment |
| Sofia, agency | The client account | Another client’s strategy |
| Elena, litigation | The client or the matter | Another matter’s record |
| Jonah, hedge fund | The expert or the broker, inside his wall | Another desk’s book |

People on the invite stay **Person** on the meeting, as in the object model. They do not each become a parent. A meeting with six attendees is one meeting, under the party the work is about. Putting it under every attendee would make Meetings a directory and would copy the note into rooms that cannot see it.

When there is no external party, the recurring series is the row: investment committee, a 1:1, a product sync. The list does not invent a company to satisfy the grouping.

One meeting has one home. If two external parties are on the invite, the home is the party the note and the follow-up belong to. The other people remain attendees.

---

## The left panel

The left panel is Home, Meetings, Calendar, and Atlas. That is the whole navigation.

```
Home                    Meetings                Calendar                Atlas
(today)                 (by company)            (the schedule)          (one scope)

Things to do            Client, company,        Week, and wider         Questions
Follow ups              or contact              Schedule a meeting      Insights
Updates                 Opens the note          Meetings only           This company
                                                                    or this meeting
```

**Home** is the first place. It is today's agenda, not the week, and not the full calendar.

**Meetings** is where a relationship is found. A company, a client, or a contact groups the meetings that belong to it. Opening one opens the note. It is not a conversation list.

**Calendar** replaces home with the schedule. Selecting a meeting opens the Meeting. It does not open a second agenda. Scheduling a meeting happens here.

**Atlas** is questions and insights. Each one belongs to a company or to a meeting. A question about Helios does not answer from Northbridge.

**A meeting**, once open, is where the note is written. Atlas, opened from here, goes deeper on this meeting. The room stays quiet. The schedule is not sitting beside the note.

The rail also has destinations: Library, Action Items, **Private notes**, and More. Destinations are not Places. Home, Meetings, Calendar, and Atlas stay the four Places. Private notes is the home for notes that span companies, the way Action Items is the home for commitments. Opening it from a meeting starts on that meeting, then lets the person widen to the company or to all notes. The meeting itself still has a Private toggle, so writing one does not require leaving the room. Same object as in [OOUX.md](OOUX.md). Two doors.

---

## Meetings

Meetings is the library of relationships. It is a list of companies, clients, and contacts, and the meetings under them.

**A row shows:** the party’s name, when you next meet them or when something last changed, and whether something is unread or still open.

**A row does not show:** the transcript, the notepad, or every action item. Those live on the Meeting, or as a short line on home.

**Under a company:**

| Under the company | Belongs here because |
| --- | --- |
| Meetings with this party | The meeting belongs to this relationship |
| Series inside the party | Helios diligence and a Helios management interview are one company and two series |
| Open commitments for this party | They become the next meeting’s talking points, and only for this company |
| Atlas, when opened from here | Scoped to this relationship and to what this person may see |

Search still finds a meeting by title. The result opens in Meetings, under the company it belongs to, not as a flat calendar result.

Unread, recording, and “will be recorded” are states of a meeting. The row can carry one of those states so the list is enough to see that Helios is live. The row does not grow a legend of icons. One status is enough until the meeting is open.

---

## Home

Home is the daily agenda. It is what Aisha has at 8:40, before she opens either meeting. It is the first item in the left panel. It exists so she does not have to read the full calendar to know what today asks of her.

| Block | What it is | What it is not |
| --- | --- | --- |
| **Today** | What is on the agenda today: which meetings, which relationships | The week, or the full calendar |
| **Things to do** | Open commitments that are due, overdue, or waiting on the next session | A second Action Items product. The global list stays one step away |
| **Follow ups** | What is owed from a recent meeting, named with that relationship | The note itself |
| **Updates** | What changed since she last looked: a note, a commitment, a reply | Every summary on the calendar |

Each line names its relationship. “Pull the margin comments” is a Helios line. “Send the portfolio update” is a Northbridge line. Home may show both, because both are hers today. It does not merge them into one note.

Opening a line opens the Meeting, under its company. Home is not where the note is written. Atlas is its own item in the left panel.

A quiet day is a short day. It does not fill itself with the rest of the calendar to look occupied.

---

## Meeting

The meeting is the quiet environment. The schedule is gone. What remains is the note, and Atlas when someone wants more of this meeting's context: the prior decision, the open commitment, the moment in the recording.

Atlas opened here stays on this meeting. A question about Helios does not answer from Northbridge.

## Calendar

The calendar holds the whole schedule. It is the calendar view, and it is where a meeting is scheduled. It shows meetings and nothing else.

**On the calendar:** title, when, relationship, response (accepted, declined, not accepted, cancelled), recording state, unread. Days can be busy or empty. The current time can mark now. A person can schedule a meeting from here.

**Off the calendar:** today's things to do, follow ups, updates, the notepad, series recaps, and Atlas. Those stay on Home, on the meeting, or in Atlas. Putting them here would put the full calendar back in charge of the day.

The calendar can switch day, week, and a wider range. That day is a list of meetings in order. It is not home. Home is today's agenda. A calendar day is the schedule.

Grouping on the calendar is by time. Relationship is a label on the row so Tuesday’s two calls are visibly Helios and Northbridge. It is not a second grouping axis. If someone wants every Helios meeting, they open Helios in Meetings.

## Atlas

Atlas has its own place in the left panel. It is not a chat list, and it is not only a field on the meeting.

**On it:** questions, and insights. Each one is for one company or one meeting. Helios stays with Helios. A meeting’s question stays with that meeting.

**Opening one** keeps that company or that meeting in scope. Atlas can also be opened from a meeting, for a deeper pass on that meeting alone. The left panel is where Atlas lives. The meeting is where one question goes deeper.

---

## What each job uses

The five jobs from the object model, and where they start. The meeting page still finishes them.

| Job | Starts on | Then |
| --- | --- | --- |
| Walk in ready | **Home**, for what is mine today. **Meetings**, for what this company still has open | The Meeting, with prior commitments already the talking points |
| Stay in the conversation | The Meeting | Meetings, only to see that this one is recording. Private notes, only to write a thought that must not travel |
| Know what is on the record | The Meeting | The company’s name is the audience hint; the page still states who can see it. A Private note is off the record on purpose |
| Leave with owners | The Meeting | The new commitment shows on Home, labeled with this relationship, and on the next meeting with this company only |
| Ask without leaving | The Meeting, or Atlas | Never across companies. A question asked from Helios cannot answer from Northbridge |

---

## What this leaves where it was

- **Team** is the account. The user's name belongs to it. The Team is their company, organization, or headquarters, on an Individual or Enterprise plan. A company in Meetings is the other party.
- **Meeting** stays the page. Client, company, and contact are how meetings are grouped, not a replacement for the meeting object.
- **Series** stays a relationship between meetings. Under a company it keeps diligence with diligence. It is the group only when there is no external party.
- **Library**, the global **Action Items** list, and **Private notes** stay other views of the same objects, one step away, out of scope as screens. Private notes is a destination, not a fifth Place.
- **Person** stays an attendee, an owner, or an audience. A contact who is the party the work is about is the row. A contact who was simply invited is not.
