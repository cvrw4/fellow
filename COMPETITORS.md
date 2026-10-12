# Fellow competitors

Fellow’s strongest competitors fall into three groups: **meeting-lifecycle platforms**, **AI notetakers and conversation intelligence tools**, and **native workplace-suite assistants**.

Fellow’s differentiation is that it connects preparation, collaborative agendas, notes, action items, and follow-through, rather than focusing only on transcription.

This note supports the meeting-page redesign in [SPEC.md](SPEC.md). The page is where that differentiation has to be visible: prep, the live meeting, and follow-through in one place. Scale and pricing context is in [BUSINESS.md](BUSINESS.md).

---

## Landscape

| Competitor | Why it competes with Fellow | Strengths | Weaknesses |
| --- | --- | --- | --- |
| **Avoma** | Closest direct competitor for full meeting lifecycle management | Strong pre-meeting preparation, customizable templates, follow-up emails, meeting intelligence, and CRM automation. Particularly strong for sales and customer-facing teams. | More sales-centric and heavier to configure. Less natural for general team meetings, 1:1s, and cross-functional work. |
| **Otter.ai** | Competes on AI meeting notes, searchable transcripts, action items, and meeting knowledge | Mature transcription and playback, strong speaker identification, mobile and desktop capture, searchable history, and broad recording options including bot-free capture. | Transcript-centered. Task execution and structured meeting preparation are less central than in Fellow. |
| **Fireflies.ai** | Broad AI meeting capture and workflow automation | Wide platform coverage, real-time notes, action items, analytics, custom templates, CRM and ATS integrations, talk-time and sentiment analysis. | Feature-dense and operationally complex. Analytics emphasize recording and conversation data more than collaborative meeting design. |
| **Microsoft Teams + Copilot** | Native alternative for organizations standardized on Microsoft 365 | Embedded in Teams. Summarizes discussion, identifies speakers and action items, answers questions during and after meetings, and sits inside Microsoft’s ecosystem. | Strongest inside Teams and Microsoft 365. Less neutral across mixed stacks, and less focused on a dedicated cross-platform meeting workspace. |
| **Google Meet + Gemini** | Native alternative for Google Workspace customers | “Take notes for me” captures notes and action items, saves them to Docs and Drive, supports catch-up, and connects to Calendar and Meet. | Notes stay inside Google’s environment. Language, plan, and host permissions constrain usage. Collaborative agenda and accountability workflows are less differentiated. |
| **Zoom AI Companion** | Native alternative for Zoom-centric organizations | Low-friction summaries and AI assistance inside the video product, on top of Zoom’s installed base and meeting context. | Optimized around the meeting event and the Zoom ecosystem, rather than an independent system for agendas, recurring-meeting history, cross-platform records, and task completion. |
| **Notion AI / Slack AI / ClickUp AI** | Adjacent substitutes that turn meeting outputs into workspace knowledge or tasks | Strong downstream destinations: documentation, search, project management, team communication, and knowledge management. | Less specialized in the full meeting lifecycle. Users still need separate recording, transcription, agenda, or calendar workflows. |

Granola, called out in the design challenge, sits with the focused notetakers: a simple, single-player capture surface with high visual polish. It is an adoption and quality reference more than a lifecycle substitute.

---

## Who is the biggest threat?

### 1. Avoma — closest product substitute

Avoma is Fellow’s most direct strategic competitor. It frames itself as a meeting lifecycle assistant: preparation, recording, collaboration, and post-meeting intelligence. Sales-oriented automation — CRM updates, methodology-specific fields, and follow-up emails — makes it compelling for revenue teams.

Fellow’s advantage is broader organizational use: team meetings, 1:1s, recurring meetings, shared agendas, action-item tracking, and integrations across CRM, project management, HR, and communication tools. Avoma is the product to watch if Fellow strengthens customer-facing workflows while staying useful beyond sales.

### 2. Microsoft and Google — distribution threats

Microsoft and Google can make meeting assistance feel like a standard capability rather than a separate product. Teams Copilot answers questions and suggests action items during or after a meeting. Gemini saves notes directly into Google Docs and Drive.

Their weakness is strategic neutrality. Fellow stays valuable as the cross-platform coordination layer for companies that mix Zoom, Teams, Google Meet, Slack, Salesforce, Jira, Linear, Notion, and other tools. Fellow emphasizes more than 50 integrations and supports meeting records across major conferencing platforms.

### 3. Otter and Fireflies — capture and data competitors

Otter is strong when the primary need is capture, transcription, playback, and retrieval. Fireflies is strong when the goal is to turn many conversations into searchable organizational data, analytics, CRM records, and automated workflows.

Fellow’s opportunity is the layer between conversation and execution: what decision was made, who owns the next step, what context is needed, and whether it happened.

---

## Fellow’s current strengths

- **End-to-end structure.** Calendar events, collaborative agendas, notes, decisions, action items, and recurring-meeting history live together.
- **Execution orientation.** AI-generated action items can be assigned, given deadlines, tracked, and synced with Asana, Jira, Linear, ClickUp, and Microsoft To Do.
- **Cross-stack positioning.** Conferencing, communication, CRM, project management, HRIS, documentation, and automation.
- **Preparation as a product surface.** Agenda templates, attendee contributions, pre-meeting reminders, and AI agenda generation — not only post-meeting summaries.
- **Privacy and enterprise readiness.** Botless recording, zero-day data retention, SOC 2, HIPAA, and GDPR.

## Fellow’s current weaknesses

- **Crowded category.** Transcription, summaries, and action items are becoming built-in features of Teams, Google Meet, Zoom, Otter, and Fireflies.
- **Workflow friction.** An AI-suggested task is not yet a committed task. False positives, ambiguous ownership, wrong due dates, and duplicate tasks across connected systems all erode trust.
- **Integration dependency.** A wider integration surface makes permissions, identity mapping, field schemas, and sync behavior harder to keep consistent.
- **Adoption.** Fellow asks people to change how they prepare and follow up. Native assistants can appear inside tools employees already use.
- **Trust and consent.** Recording, inferring commitments, analyzing talk time, and updating CRMs raise organizational, legal, and interpersonal concerns. Controls and a transparent participant experience are part of the product.

---

## Future direction

Fellow should become an integrated meeting operating system, with the assistant useful before, during, and after every meeting, and with people still in control of decisions and commitments.

### Before the meeting

- Detect whether a meeting has a clear purpose, owner, and desired outcome.
- Review prior decisions, unresolved questions, and overdue action items.
- Draft an agenda from the meeting type, participants, project status, and previous notes.
- Recommend the right attendees and flag unnecessary invitees.
- Gather relevant documents, customer records, tickets, designs, and project updates.
- Suggest whether the meeting should be shortened, converted to async, or canceled.

### During the meeting

- Maintain a live decision log, not only a transcript.
- Distinguish facts, opinions, open questions, decisions, and tentative ideas.
- Detect commitments and ask for confirmation before they become tasks.
- Surface prior context when a known topic or project comes up.
- Track agenda progress and name unresolved issues before the meeting ends.
- Give the facilitator private prompts, such as who has not contributed or that the decision criterion is still undefined.

### Immediately afterward

- Produce role-specific recaps for attendees, executives, customers, and people who were absent.
- Convert confirmed decisions into a decision register.
- Create tasks only after owner, scope, and deadline are validated.
- Draft follow-up emails, project updates, CRM entries, and documentation.
- Link every output back to the relevant transcript moment.
- Ask participants to approve uncertain interpretations before they are distributed.

### Between meetings

This is the strongest moat:

- Track whether commitments were completed, blocked, reassigned, or abandoned.
- Prepare the next recurring meeting from unfinished work and new issues.
- Identify repeated meetings that produce few decisions or duplicate other forums.
- Detect cross-team dependencies and decision bottlenecks.
- Answer “Why was this decision made?” and “Which commitments from the last three reviews are still open?”
- Recommend an async update, an escalation, or a shorter meeting based on actual outcomes.

---

## Product thesis

Fellow is the **system of record for organizational decisions and commitments**. Transcripts are inputs. The durable product is a trustworthy layer of agendas, decisions, owners, context, and outcomes, connected to the rest of the company’s tools.

> Prepare better, participate fully, decide clearly, and follow through automatically.

Three capabilities defend that position:

1. **Decision intelligence.** What was decided, why, which alternatives were considered, and who approved it.
2. **Verified execution.** Confirmed owners and deadlines, synced tasks, and a record of whether commitments were completed.
3. **Cross-platform meeting memory.** Reliable context across Zoom, Teams, Meet, Slack, email, CRM, project management, and documentation.

That direction separates Fellow from transcript-first products and from the native assistants in Microsoft, Google, and Zoom.

### What this means for the meeting page

The redesign should make the lifecycle readable on one surface:

- **Before:** purpose, open commitments, and a prepared agenda are the first things on the page.
- **During:** the note is a decision log. Capture stays quiet. Commitments are confirmed, not silently created.
- **After:** recap, owners, and follow-through are the primary objects. The transcript is evidence, available on demand.
- **Across the series:** the previous meeting is context for this one, not a separate archive.

---

## Sources

1. [Secure AI Meeting Notetaker for Every Team | Fellow Features](https://fellow.ai/features)
2. [Basics of a Fellow Meeting Note](https://help.fellow.ai/en/articles/8619527-basics-of-a-fellow-meeting-note)
3. [What is a meeting lifecycle assistant, why do you need one?](https://www.avoma.com/blog/what-is-a-meeting-lifecycle-assistant)
4. [AI Meeting Assistant by Avoma](https://www.avoma.com/ai-meeting-assistant)
5. [Otter integrations](https://otter.ai/integrations)
6. [Otter features](https://otter.ai/features)
7. [Otter Meeting Agent](https://otter.ai/?languageid=1)
8. [Fireflies — Get more things done with your meetings](https://fireflies.ai/features)
9. [Fireflies product features](https://fireflies.ai/product/features)
10. [What is Fireflies.ai](https://guide.fireflies.ai/articles/1193528158-what-is-fireflies-ai)
11. [Catch up on meetings with Microsoft Copilot in Teams](https://support.microsoft.com/en-us/teams/copilot/catch-up-on-meetings-with-microsoft-365-copilot-in-teams)
12. [Use Copilot in Microsoft Teams meetings](https://support.microsoft.com/en-us/office/use-copilot-in-microsoft-teams-meetings-0bf9dd3c-96f7-44e2-8bb8-790bedf066b1)
13. [AI note taking in Google Meet with Gemini](https://workspace.google.com/solutions/ai/ai-note-taking/)
14. [“Take notes for me” in Google Meet — Android](https://support.google.com/meet/answer/14754931?hl=en&co=GENIE.Platform%3DAndroid)
15. [“Take notes for me” in Google Meet — Computer](https://support.google.com/meet/answer/14754931?hl=en&co=GENIE.Platform%3DDesktop)
16. [AI meeting notes and action items for team meetings | Fellow](https://fellow.ai/use-cases/team-meetings)
17. [Fellow integrations](https://fellow.ai/integrations)
18. [Welcome to Fellow](https://help.fellow.ai/en/articles/4645978-welcome-to-fellow)
19. [AI Meeting Action Items Generator | Fellow](https://fellow.ai/features/action-items)
20. [Fellow glossary](https://help.fellow.ai/en/articles/2477293-fellow-glossary)
21. [Fellow AI Meeting Notes](https://fellow.ai/features/ai-meeting-notes)
22. [Fellow AI features](https://help.fellow.ai/en/articles/8461666-fellow-ai-features)
23. [AI Meeting Notes for In-Person Meetings | Fellow](https://fellow.ai/blog/fellow-mobile-app/)
24. [Otter — AI Meeting Agent](https://get.otter.ai/)
25. [Otter pricing](https://otter.ai/pricing)
26. [Gemini can now take notes in Google Meet](https://blog.google/products-and-platforms/products/workspace/take-notes-for-me/)
27. [AI note-taking — Google Meet (UK)](https://workspace.google.com/intl/en_uk/solutions/ai/ai-note-taking/)
28. [AI note-taking — Google Meet (India)](https://workspace.google.com/intl/en_in/solutions/ai/ai-note-taking/)
29. [Let Google Meet AI take notes for my users](https://knowledge.workspace.google.com/admin/meet/let-google-meet-ai-take-notes-for-my-users)
30. [AI note taking — Google Meet (Canada)](https://workspace.google.com/intl/en_ca/solutions/ai/ai-note-taking/)
