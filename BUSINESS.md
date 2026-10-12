# Fellow business

Public numbers for [Fellow.ai](https://fellow.ai/), and what they imply for the product. Fellow is an Ottawa company, founded in 2017, that moved from meeting-productivity software toward enterprise AI meeting intelligence. Disclosed figures are thin. They are enough to see the shape: a few thousand customers, revenue in the tens of millions, and a management target of $100 million by 2028.

This note sits beside [COMPETITORS.md](COMPETITORS.md) and [PERSONAS.md](PERSONAS.md). It is here so the meeting-page work in [SPEC.md](SPEC.md) follows the growth path Fellow can actually win, rather than the one Otter and Fireflies already took.

Figures below are company-reported or third-party estimates. “Users,” “organizations,” “customers,” and “ARR” are not the same unit.

---

## Snapshot

| Metric | Public figure | What it means |
| --- | --- | --- |
| Founded | 2017 | Long enough to have workflow, integrations, and enterprise relationships. |
| Headquarters | Ottawa | |
| Customers | 5,000+ | A real base. “Teams” is not the same as paying enterprise accounts. |
| Revenue | “Double-digit millions” | Current ARR is not disclosed. Recurrence, growth, and margin are unknown. |
| AI revenue | About $10 million | Management said AI revenue went from zero to $10 million after the pivot. |
| Funding | Nearly $30 million | Reported as a $6.5 million seed and a $24 million Series A. |
| 2028 target | $100 million | A management goal, not a result. |
| Price | Free to $25 / user / month | Annual billing. Team $7, Business $15, Enterprise $25. Enterprise starts at 10 users. |
| Integrations | 50+ | Conferencing, CRM, projects, docs, and chat. |

### List-price contract size

| Account | Approx. annual value |
| --- | --- |
| 10-seat Team | $840 |
| 50-seat Business | $9,000 |
| 100-seat Enterprise | $30,000 |
| 1,000-seat Enterprise | $300,000 |

These ignore discounts, free seats, and custom contracts. The spread is the point. Five thousand small Team accounts and a few hundred Enterprise accounts are completely different businesses. HubSpot reportedly onboarded 9,000 employees, which shows the ceiling of one deployment. Public information does not say how many of those seats are paid or what the contract is worth.

At the published Enterprise price of $25 per user per month, $100 million is about 333,000 paid seats:

\[
\frac{100{,}000{,}000}{25 \times 12} \approx 333{,}333
\]

Fellow does not have to get there only on Enterprise list price. Higher contracts, Business seats, usage, and a few very large deployments all count. It does have to get there by expanding inside organizations. It will not get there by matching Otter’s user count.

---

## How the others grew

The category is large and fragmented. Standalone meeting-assistant software is on the order of a few billion dollars, with published forecasts in the range of 18–26% annual growth depending on how the market is defined. The top 10 companies are reported at about a quarter of category revenue. Share rankings are not trustworthy: Microsoft, Google, and Zoom bundle the feature into suites they already sell, and vendors count users, meetings, and revenue differently.

What is reliable is the growth pattern.

| Company | Public scale | How it grew | Product that scale rewarded |
| --- | --- | --- | --- |
| **Microsoft, Google, Zoom** | Meeting AI sits inside much larger suites. Seats are not disclosed as a meeting product. | Distribution. The assistant is already where the meeting happens, often inside a contract the company already pays. | Single-meeting summary and action items, inside one ecosystem. |
| **Otter.ai** | More than $100 million ARR and more than 25 million users, reported March 2025. | Individual and team adoption. Capture first, pay later. Broad use: sales, interviews, class, personal notes. | Transcription, playback, speaker ID, searchable memory. |
| **Fireflies.ai** | More than 20 million users across 500,000 organizations, and a reported $1 billion valuation in 2025. Revenue is not verified. | Lightweight, cross-platform notetaker. Many organizations, low setup. | Recording, templates, conversation analytics, CRM and ATS push. |
| **Fellow** | 5,000+ customers. About $10 million of AI revenue after the pivot, inside a larger “double-digit millions” business. | Fewer customers, more structure. Enterprise workflow rather than consumer capture. | Agenda, shared notes, decisions, assigned action items, series history, 50+ integrations, botless recording and compliance controls. |
| **Avoma** | Private metrics are scarce. | Specialist, especially revenue teams. | Scheduling, notes, follow-up, CRM updates. |

Otter and Fireflies won **volume**. The suites are winning **default placement**. Fellow’s disclosed scale is an order of magnitude smaller on users, and its revenue is still an order of magnitude short of Otter. That gap is not a reason to copy their product. Their product is what got commoditized. Transcripts, summaries, and suggested action items are now baseline in Teams, Meet, Zoom, Otter, and Fireflies.

The money that is still distinct sits where a meeting changes revenue, compliance, or execution: sales, financial services, healthcare, legal, customer teams, and internal operations. Those buyers pay for a record they can govern and for work that actually gets done. That matches the industries on Fellow’s own site, and the people in [PERSONAS.md](PERSONAS.md).

---

## Product-defining features

These are the features that justify a different company than Otter or Fireflies. If the meeting page reads as a nicer notetaker, Fellow is competing on the axis those companies already won, at a fraction of their distribution.

| Feature | Why it defines Fellow | What the larger products grew without |
| --- | --- | --- |
| **Shared preparation** | Agenda, templates, attendee contributions, and open items from last time are the product before anyone speaks. | Otter and Fireflies grew on the recording. The suites grew on the summary after the call. |
| **The series, not the file** | A recurring meeting is a thread: prior decisions, unfinished commitments, and this week’s purpose. | Capture products grew one recording at a time. History is an archive, not the next agenda. |
| **Confirmed commitments** | An action item has an owner and a deadline, and it can land in Asana, Jira, Linear, ClickUp, or Microsoft To Do. Suggested tasks stay suggestions until someone confirms them. | Commodity notetakers extract tasks. They do not have to be right, because the transcript is the product. |
| **Decision memory** | What was decided, why, and who can still see it after the audio is deleted. | Searchable transcript grew Otter. It does not survive a retention policy, and it is not a decision. |
| **Botless, governed capture** | No bot in the room. Pause actually drops the off-record stretch. Retention, access, SOC 2, HIPAA, and GDPR are visible on the meeting. | Consumer notetakers grew on convenience. A bot, or a hidden recorder, blocks the buyers in [PERSONAS.md](PERSONAS.md). |
| **Cross-stack memory** | The same meeting works across Zoom, Meet, and Teams, and pushes into CRM, projects, docs, and chat. | Microsoft, Google, and Zoom grew by being the suite. They are weakest when the company mixes tools. |

Ask Fellow belongs on this list only when it is scoped: this meeting, this series, this account, this person’s permissions. A general chatbot is what every suite now ships.

---

## Directions

Fellow’s path from roughly ten million dollars of AI revenue toward $100 million is **more seats inside fewer, more serious customers**, plus a higher value per seat than a $7 notetaker. The product direction follows from that, and from where the larger companies are already strong.

1. **Own the path from meeting to done work.** Preparation, decision, confirmed commitment, completion. That is the line Otter does not need and Copilot does not own across a mixed stack.
2. **Design for the whole organization, not the power user.** A 9,000-person rollout only sticks if the page is calm enough for someone who did not ask for a meeting tool. Granola’s polish, in [SPEC.md](SPEC.md), is the adoption bar those extra seats feel first.
3. **Make the expensive workflows obvious.** Investor calls, diligence, clinical huddles, client strategy, and revenue meetings are where a $25 seat is easy to defend. The page should show the decision, the owner, the audience, and the retention window before it shows the transcript.
4. **Stop adding capture surface.** Speaker labels, sentiment, and another summary style are how Fireflies got broad and how the suites made the category cheap. They do not move Fellow toward 333,000 serious seats.
5. **Treat retention as a feature.** The next meeting should open on what the last one left unfinished. That is net retention: the same account uses more of the product because the work is still there. Free-tier notes do not do this.
6. **Keep a person on the commitment.** False owners and duplicate tasks are how an enterprise deployment quietly dies. Confirm before writing to Jira or the CRM.

The business case gets stronger when customers can point to faster decisions, finished commitments, and fewer meetings that should have been an update. It stays weak if the proof is only “we spent less time on notes.”

---

## What this means for the meeting page

The redesign is a business choice as well as a visual one.

- **Before the meeting,** purpose and open commitments lead. That is the feature the volume players never grew on.
- **During,** the note is the decision log. Recording state is quiet and unmistakable. New tasks are confirmed.
- **After,** the recap, the owners, and the follow-through are the objects. The transcript is evidence, and it can disappear without taking the decision with it.
- **On every meeting,** audience and retention are visible. That is what lets security approve the tool a 1,000-seat account will actually roll out.
- **Density stays low.** Enterprise expansion loses to Granola, and to “just use Copilot,” if the page looks like the feature list.

Capabilities stay. They wait until the moment they are the job. That is the same judgment as in [SPEC.md](SPEC.md), and it is also how a smaller meeting product earns a larger contract.

---

## Sources

1. [Fellow surpasses 5,000 customers after rebooting for the AI era | BetaKit](https://betakit.com/fellow-surpasses-5000-customers-after-rebooting-for-the-ai-era/)
2. [Fellow pricing](https://fellow.ai/pricing)
3. [Fellow — Investors & Founders | Fundraising Fox](https://fundraisingfox.com/companies/fellow)
4. [Fellow enterprise](https://fellow.ai/enterprise)
5. [Fellow integrations](https://fellow.ai/integrations)
6. [Secure AI Meeting Notetaker for Every Team | Fellow](https://fellow.ai/features)
7. [AI Meeting Assistant Market Size & Share Report, 2026-2033 | Grand View Research](https://www.grandviewresearch.com/industry-analysis/ai-meeting-assistant-market-report)
8. [AI-Powered Meeting Assistants Market | The Business Research Company](https://www.thebusinessresearchcompany.com/report/artificial-intelligence-ai-powered-meeting-assistants-global-market-report)
9. [Otter revenue, funding & growth rate | Sacra](https://sacra.com/c/otter/)
10. [Catch up on meetings with Microsoft Copilot in Teams](https://support.microsoft.com/en-us/teams/copilot/catch-up-on-meetings-with-microsoft-365-copilot-in-teams)
11. [AI note taking in Google Meet with Gemini](https://workspace.google.com/solutions/ai/ai-note-taking/)
