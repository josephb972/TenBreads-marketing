# Schedules

All run as cloud scheduled tasks on branch `ccr-05992a65-4on2a1`. Each prompt is standalone: it starts cold, so it re-reads the repo files.

| Agent | When (UTC) | Connectors |
|---|---|---|
| prospector | Mon–Thu 13:07 | none |
| outreach-writer | Mon–Fri 14:23 | Gmail |
| reply-triage | Mon–Fri 15:11, 19:11 | Gmail |
| content-writer | Sun 16:19 | none |
| promo-builder | Wed 17:29 (until assets exist, then pause) | none |
| analyst | Fri 20:41 | Gmail |
| orchestrator (digest) | Mon–Fri 12:13 | none |

Times avoid :00/:30 to dodge traffic. Adjust to your timezone once known.

## Pausing
Disable any task via the scheduled-task list. Setting `Auto-send` or `Public posting` in config.md stays OFF until you decide otherwise.
