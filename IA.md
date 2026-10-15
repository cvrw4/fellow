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

The chat list below is who that Team meets. Helios is a relationship row. Acme Co is the account those rows live in. An internal series, such as investment committee, is its own row. The list does not use the Team's name as that row.

---

## Decision

The full calendar is too much to see at once. Home takes that load off. It shows what is on the agenda today, and leaves the rest of the schedule for the calendar.

| Surface | Job | What it contains |
| --- | --- | --- |
| **Home** | Today's agenda | Things to do, follow ups, recent chats with Atlas, updates |
| **Meeting** | The quiet note | The note for this meeting, and a deeper look at its context with Atlas |
| **Calendar** | The whole schedule | The calendar view, and scheduling a meeting. Meetings in time, nothing else |
| **Atlas** | Chats and insights | Atlas's own view. Chats, and insights for one company or one meeting |

A meeting still belongs under a **relationship**: a client, a company, or a contact. That relationship is the row in a chat list. The meeting is an item inside the row, the way a message sits inside a thread. Home is not that list. Home is the day.

The calendar does not own the meeting. It places the same meetings in time, and it is where a meeting is scheduled. Notes, follow ups, and Atlas chats do not move onto the calendar to make it more useful. If they did, the calendar would become a second home.

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

## The surfaces

Home is the daily agenda. A meeting is the quiet room. The calendar is the whole schedule. Atlas is its own view.

```
Home                    Meeting                 Calendar                Atlas
(today)                 (this note)             (the schedule)          (chats and insights)

Things to do            The note                Week, and wider         Chats
Follow ups              Deeper context          Schedule a meeting      Per company
Recent Atlas chats      with Atlas              Meetings only           Per meeting
Updates
```

**Home** is the first place. It is today's agenda, not the week, and not the full calendar.

**A meeting** is where the note is written. Atlas, opened from here, goes deeper on this meeting. The room stays quiet. The schedule is not sitting beside the note.

**Calendar** replaces home with the schedule. Selecting a meeting opens the Meeting. It does not open a second agenda. Scheduling a meeting happens here.

**Atlas** lists chats and insights. Each one belongs to a company or to a meeting. Opening a chat does not mix two relationships.

The chat list is still how a relationship is found. **Today** is pinned at the top of that list, and it opens home. It is not a relationship. Everything under it is a relationship row: name, the next meeting or the last activity, and a count of what is still open. Opening the row opens that thread.

---

## Chat list

The list is the library of relationships, in the shape of a conversation list.

**A row shows:** the party’s name, when you next meet them or when the thread last changed, and whether something is unread or still open.

**A row does not show:** the transcript, the notepad, or every action item. Those live on the Meeting, or as a short line on home.

**Inside the thread:**

| In the thread | Belongs here because |
| --- | --- |
| Meetings with this party | The meeting’s home is this relationship |
| Series inside the party | Helios diligence and a Helios management interview are one company and two series |
| Open commitments for this party | They become the next meeting’s talking points, and only inside this thread |
| Atlas, when opened from here | Scoped to this relationship and to what this person may see. The Atlas home lists these chats; it does not widen them |

Search still finds a meeting by title. The result lands in the thread it belongs to, not in a flat calendar result.

Unread, recording, and “will be recorded” are states of a meeting inside the thread. The row can carry one of those states so the list is enough to see that Helios is live. The row does not grow a legend of icons. One status is enough until the thread is open.

---

## Home

Home is the daily agenda. It is what Aisha has at 8:40, before she opens either meeting. It is reached from **Today** at the top of the list. It exists so she does not have to read the full calendar to know what today asks of her.

| Block | What it is | What it is not |
| --- | --- | --- |
| **Today** | What is on the agenda today: which meetings, which relationships | The week, or the full calendar |
| **Things to do** | Open commitments that are due, overdue, or waiting on the next session | A second Action Items product. The global list stays one step away |
| **Follow ups** | What is owed from a recent meeting, named with that relationship | The note itself |
| **Recent chats with Atlas** | The latest Atlas conversations, each one still tied to its company or its meeting | A new chat that spans two relationships |
| **Updates** | What changed since she last looked: a note, a commitment, a reply | Every summary on the calendar |

Each line names its relationship. “Pull the margin comments” is a Helios line. “Send the portfolio update” is a Northbridge line. Home may show both, because both are hers today. It does not merge them into one note.

Opening a line opens the Meeting, inside its thread, or the Atlas chat it came from. Home is not where the note is written.

A quiet day is a short day. It does not fill itself with the rest of the calendar to look occupied.

---

## Meeting

The meeting is the quiet environment. The schedule is gone. What remains is the note, and Atlas when someone wants more of this meeting's context: the prior decision, the open commitment, the moment in the recording.

Atlas opened here stays on this meeting. A question about Helios does not answer from Northbridge.

## Calendar

The calendar holds the whole schedule. It is the calendar view, and it is where a meeting is scheduled. It shows meetings and nothing else.

**On the calendar:** title, when, relationship, response (accepted, declined, not accepted, cancelled), recording state, unread. Days can be busy or empty. The current time can mark now. A person can schedule a meeting from here.

**Off the calendar:** today's things to do, follow ups, updates, the notepad, series recaps, and Atlas. Those stay on home, on the meeting, or in Atlas. Putting them here would put the full calendar back in charge of the day.

The calendar can switch day, week, and a wider range. That day is a list of meetings in order. It is not home. Home is today's agenda. A calendar day is the schedule.

Grouping on the calendar is by time. Relationship is a label on the row so Tuesday’s two calls are visibly Helios and Northbridge. It is not a second grouping axis. If someone wants every Helios meeting, they open the Helios thread.

## Atlas

Atlas has a homepage of its own. It is not only a field on the meeting.

**On it:** chats, and insights. Each chat and each insight is for one company or one meeting. Helios insights stay with Helios. A meeting insight stays with that meeting.

**Opening one** continues that chat, with the company or the meeting already in scope. Recent chats also appear on home, as a way back. The full list lives here.

Atlas can still be opened from a meeting, for a deeper pass on that meeting alone. The homepage is the place the chats are kept. The meeting is the place one of them goes deeper.

---

## What each job uses

The five jobs from the object model, and where they start. The meeting page still finishes them.

| Job | Starts on | Then |
| --- | --- | --- |
| Walk in ready | **Day**, for what is mine today. **Thread**, for what this party still has open | The Meeting, with prior commitments already the talking points |
| Stay in the conversation | The Meeting | The list only to see that this thread is the one recording |
| Know what is on the record | The Meeting | The thread’s name is the audience hint; the page still states who can see it |
| Leave with owners | The Meeting | The new commitment shows on home, labeled with this relationship, and on the next meeting in this thread only |
| Ask without leaving | The Meeting, the thread, or the Atlas home | Never across threads. A question asked from Helios cannot answer from Northbridge |

---

## What this leaves where it was

- **Team** is the account. The user's name belongs to it. The Team is their company, organization, or headquarters, on an Individual or Enterprise plan. A company in the chat list is the other party.
- **Meeting** stays the page. Client, company, and contact are how meetings are grouped, not a replacement for the meeting object.
- **Series** stays a relationship between meetings. Inside a thread it keeps diligence with diligence. It is the row only when there is no external party.
- **Library** and the global **Action Items** list stay other views of the same objects, one step away, out of scope as screens.
- **Person** stays an attendee, an owner, or an audience. A contact who is the party the work is about is the row. A contact who was simply invited is not.
