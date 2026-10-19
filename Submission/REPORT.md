CrewAI Build Report

Name: Kundan sai yaruru
Topic I used: How college students can use AI to study more effectively

1. What I changed

I modified the writer agent in crewai-kit/main.py. Originally, the Technical Writer was instructed to explain a topic to a smart reader outside the field. I changed its backstory to describe a friendly educational writer who explains difficult ideas to 10-year-old children. I added instructions to use simple words, short sentences, and familiar examples while avoiding unnecessary technical jargon.

I made this change because I wanted to see how an agent's instructions affect the content it produces. I kept the Research Analyst and Editor roles, the three tasks, and the sequential workflow the same. This allowed me to focus on the effect of changing the Writer's instructions rather than changing the entire system.

The modified Writer was designed to make the explainer easier for a younger audience to understand. I then ran the program again using the same topic so I could compare the results.

2. How CrewAI works

CrewAI lets developers organize AI work using agents, tasks, and a crew. An agent has a role, a goal, and a backstory that guide how it approaches its work. In my project, the Research Analyst gathers information, the Technical Writer creates an explainer, and the Editor improves the draft and identifies claims that need sources.

Each agent has a task describing what it should accomplish and an expected output describing the desired result. The three tasks are organized in a sequential process. This means the research task runs first, the writing task follows, and the editing task runs last. The output from earlier tasks provides context for later work.

My change worked by modifying the Writer agent's backstory. The new instructions encouraged the model to use simpler language and familiar examples. The crew's overall structure stayed the same, but the writing style changed because the Writer received different instructions.

This shows that an agent's configuration can influence its behavior without requiring a completely different workflow. However, the instructions guide the model rather than guaranteeing a particular result.

3. Evidence

I saved the original and modified reports in explainer_run1.md and explainer_run2.md. I also saved the corresponding terminal outputs in run1_original.txt and run2_changed.txt.

The program's terminal output showed the Research Analyst, Technical Writer, and Editor completing their tasks. In the modified version, the Writer was instructed to explain difficult ideas to a 10-year-old, using simple words and short sentences. I compared the reports to examine how the change affected the writing.

One problem I encountered was a Python SyntaxError while editing the Writer's code. I reviewed the code and corrected the string formatting in the agent definition. During execution, I also encountered an empty-response error from the language model. I retried the program, and a later run completed all three agent tasks successfully.

4. Choosing a framework

I would choose CrewAI for a project like this because its agent roles and task sequence are straightforward to understand. The workflow resembles a team in which one person researches, another writes, and a third edits. This made it relatively easy to assign responsibilities and change the Writer's instructions without redesigning the whole program.

The OpenAI Agents SDK, another framework discussed in class, could also support a multi-agent application. It would be a reasonable alternative if I wanted to build around its agent, tool, and handoff features. Depending on the implementation, I might need to define more of the coordination logic myself.

LangGraph is another alternative that is useful when a workflow needs explicit state management, conditional branching, cycles, or more detailed control over execution. Those capabilities could be helpful for a larger research system that repeats a task when sources are missing or asks for human approval before continuing. However, its graph-based workflow could require more setup for this simple three-step process.

For my project, CrewAI's role-based and sequential structure suited the research, writing, and editing stages. The best framework would ultimately depend on the project's complexity and the amount of control required.

5. Verification and AI use

I checked whether the program completed all three tasks and produced a final report. I reviewed the terminal output and saved reports to confirm that the workflow ran and that the Writer's instructions reflected the intended change.

However, successful execution does not prove that the generated facts are accurate. The starter kit does not provide web access for checking research claims, and the model may generate incorrect statistics, citations, or study names. I would need to locate and read reliable original sources before treating those claims as verified. The Editor's source flags are useful reminders, but they do not independently verify information.

I used AI assistance to understand and modify the Python code, troubleshoot errors, and organize this report. I checked the suggested code against my main.py file and used actual terminal output to confirm successful execution. The report describes the work I performed, and I will review it to ensure that its claims match my experience.