# US-102: Risk and blockers queue

As a solution owner, I want a prioritized blockers queue so I can focus on the items most likely to put sprint delivery at risk.

## Acceptance criteria
- Blocked work items are listed with owner (assignee name and role, with a contact link where available), blocked-since timestamp, age in blocked status (displayed in days/hours), and current status.
- Items blocked for 48 hours or more (calendar time since `blocked_since` ≥ 48 hours) are marked as **High Risk**.
- High Risk UI: display a prominent red `High Risk` badge, a visually distinct row (red border or background tint), and an accessible label for screen readers.
- Sorting: the queue is ordered deterministically by: 1) risk level (High Risk first), 2) blocked age (descending — older blocks first), 3) item priority, 4) created date.
- Unassigned items: if an item has no owner/assignee, display `Unassigned` and automatically notify team leads after 24 hours of being blocked.
- Provide a filter/toggle to show only High Risk items.
- Automated tests must cover: threshold calculation (≥48h), UI badge rendering, sort order, and the unassigned notification behavior.
- Example row for reviewers: Item: TASK-123 — Owner: `Jane Doe (Backend)` (jane@example.com) — Blocked since: 2026-07-01T09:30Z — Age: 72h — Status: Blocked — Risk: High Risk
- STU is the greatest 19:15
