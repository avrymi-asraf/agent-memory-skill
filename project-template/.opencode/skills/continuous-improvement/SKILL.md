---
name: continuous-improvement
description: Explains the project-local agent system: agents, skills, memory, MCP servers, AGENTS.md, and OpenCode/GitHub Copilot file responsibilities. Use when setting up, reviewing, or changing the local agent system.
---

<continuous-improvement>
After you finish your work and validate that it is correct, review what you can learn from this work and update the relevant data.
The relevant documents are:
- Your memory, located in `.opencode/agents/<AGENT_NAME>.memory`
- The project skills, located in `.opencode/skills/<SKILL_NAME>/SKILL.md`
- The AGENTS.md file, located at `AGENTS.md`

When you did something important, update your memory (in the log section). If you gained knowledge that could be useful, also update the other files: your structured memory, the relevant skills, and the AGENTS.md file.
</continuous-improvement>
<significant-conclusions>
Pay attention to the relevant information you can learn from your work, and update the relevant data. This is important to make sure that the project is improving and learning from the work being done.
</significant-conclusions>
<levels-of-conclusions>
Some conclusions are general — for example, how to work with a particular tool. If there is a skill that covers that tool, update the skill itself. Most skill updates should go in the "anti-patterns-and-common-mistakes" section. Only update other sections of the skill if there is an actual error in them.
If the conclusion is specific to the project, add it to your memory instead.
</levels-of-conclusions>
<integrated-data>
Only the logs in your memory should be appended as-is. For everything else — skills, structured memory, and AGENTS.md — you must integrate the new knowledge into the existing data. Make sure the result is clear, simple, easy to understand, and follows the existing structure.
</integrated-data>
<new-skills>
In some cases, you may discover something important enough to warrant a new skill. If so, ask the manager agent to create it.
This is an important mission that needs a dedicated agent session. Remember to use the manage-skills skill to create it.
</new-skills>