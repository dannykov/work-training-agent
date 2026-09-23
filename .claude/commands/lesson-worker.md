---
description: Start a lesson-worker subagent to complete one lesson of a work training.
argument-hint: "<lesson-url>"
---

Start a `lesson-worker` subagent with the Agent tool (`subagent_type: "lesson-worker"`) and assign it this lesson: $ARGUMENTS

If no lesson URL was given, ask the user for one before starting the agent.

Act as its parent, as `CLAUDE.md` describes under "Lesson-worker subagents":

- Before starting the agent, add or update this lesson's row in the lesson status CSV (`status` = `in progress`).
- Pass the agent the lesson URL, the root URL (the lesson URL's origin unless the user said otherwise), and any known answers for this lesson from earlier raw data.
- Audit it while it runs. When it reports `STATUS: COMPLETED` or `STATUS: STUCK`, check the lesson's status on the site, terminate the agent, close its tab, and update its CSV row to `completed` or `not completed`.
- Tell the user the final status, the path to the lesson's `RAW-DATA.md`, and anything they need to do.
