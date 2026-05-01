# Agents, Skills, and Memory

In this system, for now, everything is local to the project in opencode and VS Code. Only `agents` and `skills` are symlinked to the dotfiles repo.

## 1. Agents

Agents are the specific personas or roles assigned to complete tasks. They define the personality, perspective, and working style needed for the job. They also define specific MCPs to use, the model, and possibly emphasize certain skills.

For example, a **Developer** agent would be designed specifically to write, review, and reason about code.

The main purpose of subagents is to manage the LLM context. Even when there is not much difference between the agents, having different agents with different memories is important for managing context.

The basic agents are:

**Manager** - Runs long tasks. This agent should use the other agents, manage the context of the subagents, and follow the larger mission.

**Researcher** - Focuses on research on the internet. This agent uses MCPs for internet search and deep research, and knows the LLM wiki and Karpathy resources. This should be a good model.

**Plan** - Writes plans, focuses on code standards, the big picture of the code flow, and code review. This agent plans the code and the tests, and knows how to deploy.

**Build** - Writes the code and focuses on creating from the plan. This agent follows code principles and handles every small piece of writing.

**Operator** - Runs things, runs tests, deploys, and performs actions. This agent focuses on knowing how to use tools. Every tool-running task is handled by this agent.

**Reviewer** - Performs code review.

## 2. Skills

Skills are split into two types: system skills, which define this system, how it works, and how to maintain it; and project skills, which are also important and cover everything about the project.

Skills represent the model’s knowledge base and practical expertise. For an AI system to provide real value, its skills should contain broad, high-quality units of information.

A well-designed skill should, on one hand, explain the system so the model clearly understands what exists here. It should also support **cognitive flexibility**. It should give the model enough context to move freely between foundational explanation, technical reasoning, and practical execution.

Rather than forcing the model into rigid step-by-step instructions, a skill should provide the background, concepts, patterns, and examples needed for the model to reason, deduce, and connect ideas on its own.

In other words, skills should not only tell the model what to do. They should give the model enough understanding to decide how best to do it.

Basic skills:

* manage-skill
* manage-mcp
* scripts
* code-principles
* internet-search
* wiki-llm
* agent-system - Explains how this system should look, with specifications for every file.
* project-skills

## 3. Intro and Communication: `Agents.md`

`Agents.md` serves as the central collaboration space for all agents.

It is the introduction to the project. It should contain what the project is, how it is built, how to use it, and so on.

It also needs to contain the current status, stage, and some TODO items that agents update as the project progresses.

It should continuously track the project’s status, explain how the project operates, map the code flow, and act as the single source of truth for coordination between agents.

This file should help agents understand what has been done, what is currently happening, and how the different parts of the system connect.

## 4. Memory File

A memory file is a file named `<agent-name>.memory` inside the agent folders.

### Memory

Memory is divided into two main categories:

#### Short-Term Memory

Short-term memory acts as the active working space. It keeps track of recent actions, current decisions, open questions, and the present status of the project.

#### Long-Term Memory

Long-term memory stores important technical details that need to persist over time. This is reserved for information that does not naturally belong inside a general skill and is not part of an agent’s core personality.

## 5. Continuous Improvement

The agent system must contain a strong self-improvement system.

This will appear in several places:

* The `agent.memory` file, which contains short-term and long-term memory.
* The project skills, which are updated continuously.
* The skills that contain common mistakes and errors.
* The agent file.

1. Because agents do not usually update memory and the system, this point must be emphasized in several places again and again to make sure they do it.
2. It is very important to integrate new memory into the existing memory. What often happens is that agents treat the current conversation as the most important thing, and we end up with half a page of unnecessary memory.
3. TODO

## Principles When Working with Agents

### 1. Distributed Ideas and Multiple Views

Ideas should not live in only one place Your job is to convert the existing project into the existing template in this file.
On the one hand - you have to rebuild the entire project, it should contain only templates for a new folder containing the basic skills and basic agents.
On the other hand, base it as much as possible on the ideas you see in the existing repo. Everything you are going to implement, look - has it been implemented already? Is this idea already there somewhere - if so, use it.
Add the existing mcp.
Remember - in the end, this file will only contain the file that explains the idea and the template for opencode and github copilot.
Remember that everything with us is at the project level, all the skills and agent settings are only at the project level.
After you have done the entire project - delete the old project, verify the new formor appear from only one perspective.

Important concepts should be represented across different locations, using different views, depending on how they are used. For example, the same idea may appear as a high-level explanation in a skill, as a project-specific note in memory, as an implementation detail in `Agents.md`, or as an operational instruction inside a tool.

This makes the system more flexible, easier to navigate, and better suited for agents working from different roles or contexts.

### 2. Leave Space for Thinking

Agents are smart. Sometimes they need an exact recipe for what to do, but it is more important to teach them ideas about the system. They will complete the details themselves and therefore be able to do more.
