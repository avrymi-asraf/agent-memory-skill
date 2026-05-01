---
name: continuous-improvement
description: Explains the project-local agent system: agents, skills, memory, MCP servers, AGENTS.md, and OpenCode/GitHub Copilot file responsibilities. Use when setting up, reviewing, or changing the local agent system.
---

<continuous-improvement>
after you finish your work and validate that it is correct and works, you need to look what you can learn from this work and update the relevant data.
the relevent document are:
Your memory, located in .opencode/agents/<AGENT_NAME>.memory
The project skills, located in .opencode/skills/<SKILL_NAME>/SKILL.md
the AGENTS.md file, located in AGENTS.md
When you did something important you need to update your memory (in the log section). if you think that there is a knowledge that can be useful update the other files: your structured memory, the relevent skills, and the AGENTS.md file.
</continuous-improvement>
<Significant-conclusions>
you have to pay attention what is the relevent information that you can learn from your work, and update the relevant data. this is important to make sure that the project is improving and learning from the work that is being done.
</Significant-conclusions>
<levels-of-conclusions>
some of the conclusions are relevent in general how works with some of the tools, this it the generales conclusion. then if there is a skill deal with this tool you can update the skill it self.  pay attention to that most of the update in the skill shold be in the "anti-patterns-and-common-mistakes" section. only if there is a mistake in the one section of the skills update the skill self.
if it somthing that connect only to the project, you can need to add it in the your memory.
</levels-of-conclusions>
<integrated-data>
only the logs in your memory need to update as is. all others, skills, structured memory, and AGENTS.md file, you need to integrated the new knowledge in the existing data. you need to make sure that the data is clear and simple, and that it is easy to understand and use. and that it still in the same structure.
</integrated-data>
<new-skills>
in some cases, when you think that there is something that is very important and need to create a new skill. you can call the manager agent to create this skill.
it's very important missing that needs a different agent session. remember to use the manage-skill skill to create the new skill.
</new-skills>