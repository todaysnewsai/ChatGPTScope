---
image: "https://articlesaboutai.com/assets/images/codex-steering-controls.svg"
layout: post
title: "OpenAI Speeds Up Codex Steering in ChatGPT Desktop: How Follow-Up Controls Work"
description: "OpenAI is rolling out faster steering for Codex in the ChatGPT desktop app. Learn how steering and queued follow-ups differ, where to change the setting, and how to guide a coding task mid-run."
date: 2026-10-09 17:23:00 +0000
categories:
  - news
tags:
  - OpenAI
  - Codex
  - ChatGPT desktop
  - coding agent
  - product update
author: "ChatGPTScope Editorial Team"
---

OpenAI is rolling out faster steering for Codex in the ChatGPT desktop app, according to the company’s ChatGPT release notes dated October 8, 2026. The update targets a common problem in agent-assisted coding: a developer starts a task, notices that the agent is following the wrong approach, and needs to correct it before more work is done. OpenAI says that when a user sends a follow-up to steer a running task, Codex can respond to the change sooner.

The announcement is small in scope, but it addresses an important part of working with a coding agent. A developer’s instructions are rarely perfect on the first attempt. Requirements become clearer after inspecting a proposed solution, a missing constraint surfaces during implementation, or a better approach becomes apparent only after the task has started. A useful workflow needs a way to make those corrections without treating every new instruction as an entirely separate job.

OpenAI’s release note points users to a setting called **Follow-up behavior** in the ChatGPT desktop app. That setting determines whether a follow-up message steers the current run or waits for the next run. The company’s Codex help article also documents the distinction in the command-line interface: press Enter to steer while Codex is working, or press Tab to queue a message for later.

This guide explains what OpenAI has confirmed, how steering differs from queuing, where the controls are located, and how to use them in realistic coding workflows. It also separates the confirmed product change from practical recommendations about when a developer might prefer one behavior over the other.

## What OpenAI announced

On October 8, 2026, OpenAI added a release-note entry titled “Faster steering in Codex.” The company says it is rolling out faster steering in Codex within the ChatGPT desktop app. When a user sends a follow-up intended to steer an active task, Codex can respond to that change sooner.

OpenAI describes steering as a way to correct an approach, provide missing information, or change the direction of work while Codex is still working. The release note says users can choose whether follow-up messages affect the current run or wait for the next one through **Settings → General → Follow-up behavior**.

The official documentation does not provide a numerical speed improvement, a benchmark, or a guarantee that every correction will be applied immediately. It also says availability varies during the rollout. The confirmed claim is therefore specific: OpenAI is rolling out faster steering for Codex in the ChatGPT desktop app, not promising a fixed response time for every task or account.

For the primary announcement, see OpenAI’s [ChatGPT release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes). For the instructions on steering, queuing, and Codex access, consult [Using Codex with your ChatGPT plan](https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan).

## What “steering” means in Codex

Codex is OpenAI’s coding agent for helping people write, review, and ship code. In an agentic coding workflow, a task may involve several connected steps: understanding a repository, inspecting files, planning an implementation, making edits, and checking the result. The user may not know every detail that needs to be specified until the work is underway.

Steering lets the user send a follow-up message while Codex is working and have that message added to the current run. According to OpenAI’s help article, it is intended for correcting the current approach, adding information, or changing the direction of the task.

Imagine asking Codex to add a search box to a website. After it begins, you realize that the project already has a search component in another directory. A steering message could point Codex to that existing component and ask it to reuse the project’s established pattern rather than building a separate one. The correction becomes part of the work already in progress.

Or suppose Codex starts implementing a feature and you notice that a requirement was omitted from the original prompt: the change must preserve compatibility with an older browser. Steering can communicate that missing constraint while the task is active. The point is not that Codex will always interpret the correction perfectly; it is that the user has a documented way to influence the current run rather than waiting by default for a later task.

The distinction matters because coding tasks are iterative. A first instruction often establishes the goal, while later messages refine scope, implementation choices, or acceptance criteria. Steering gives those later messages a role in the current run.

## Steering versus queuing: the important difference

OpenAI documents two ways to handle a follow-up while Codex is working:

- **Steer:** Add the message to the current run.
- **Queue:** Save the message for the next run, after the current work finishes.

The choice is about timing and intent. Steering is appropriate when the active task should take the new information into account. Queuing is appropriate when the current run should finish before the next instruction is handled.

Consider a task to update a project’s settings page. If you notice that Codex is using the wrong configuration file, you may want to steer the current run so that it can correct course. If the current task is nearly finished and you want Codex to write tests afterward, you may prefer to queue that second request so it becomes the next run rather than changing the active task’s scope.

Neither option is universally better. Steering is useful for corrections that affect the work underway. Queuing is useful for a deliberate sequence of tasks. The risk in choosing poorly is mostly workflow-related: an urgent correction might arrive too late if it is queued, while a new request may complicate an active task if it is sent as a steering instruction when it would be cleaner to handle it separately.

The official description does not say that steering cancels the current task, rolls back edits, or guarantees that all prior work will be discarded. Users should not assume any of those behaviors. Read the controls as a way to direct when a follow-up is applied, then review the resulting changes as you normally would.

## How to change the default in the ChatGPT desktop app

OpenAI says the desktop app provides a default setting for follow-up behavior. To change it:

1. Open the ChatGPT desktop app.
2. Open **Settings**.
3. Select **General**.
4. Find **Follow-up behavior**.
5. Choose whether follow-up messages should steer the current run or wait for the next run.

The precise interface can change as the desktop app evolves, so if the option is not visible, consult OpenAI’s current help article or check whether your app is up to date. The release note and help article identify the setting path, but they do not promise that the faster-steering rollout will be available to every user at the same time.

Queued messages are shown above the composer, according to OpenAI. From there, users can edit, reorder, send, or delete them. That provides a useful review point: before a queued instruction is sent, a user can adjust its wording or change the order of planned follow-up work.

The default is worth choosing based on how you normally work. If you frequently discover important requirements mid-task, steering may be a convenient default. If you usually break work into a sequence—implement a feature, then write tests, then update documentation—queuing may better match that routine. These are workflow recommendations, not official claims that one setting improves code quality in every situation.

## How steering and queuing work in Codex CLI

OpenAI’s Codex help article also documents keyboard controls for the command-line interface. While Codex is working, press **Enter** to steer the active task or **Tab** to queue a follow-up for later.

That is an interface-specific detail worth keeping separate from the desktop app’s settings. The October 8 announcement specifically describes faster steering in Codex in the ChatGPT desktop app. The documentation also explains steering and queuing in Codex CLI, but it does not state that the same speed improvement is being rolled out to every Codex client.

For developers who move between a graphical desktop environment and a terminal, the underlying distinction remains useful: a steering message belongs to the current run, while a queued message is intended for the next run. The key gesture differs by client, so users should check the documentation for the interface they are actually using rather than assuming that every keyboard shortcut is shared across products.

OpenAI lists several Codex access points, including the ChatGPT desktop app, Codex CLI, an IDE extension, and Codex on the web. The available client and capabilities may depend on the user’s setup and workspace. The official [Codex page for developers](https://developers.openai.com/codex/) provides additional technical information.

## Practical example: correcting a coding task mid-run

Suppose you ask Codex to add a CSV export button to an analytics dashboard. The initial request says what the button should do but does not mention the project’s existing download utility. Codex begins examining the code and starts proposing an implementation.

You then notice a relevant helper already exists. A useful steering message would be direct and specific: “Before continuing, inspect the existing export utility and use it if it supports this format. Keep the current dashboard styling and avoid adding a second download implementation.”

This message adds information that changes how the current task should proceed. After Codex responds, inspect the proposed or completed changes to confirm that it actually used the existing helper and preserved the styling. Steering improves the opportunity to correct the direction; it does not remove the need to review the code.

Now imagine a different situation. The export button is complete, and you want Codex to add automated tests and update the README as a separate follow-up. If you do not want those additional tasks to change the current run, queue them for the next run. You can review and reorder queued messages before sending them, according to OpenAI’s documentation.

This example illustrates a useful habit: state both the correction and the acceptance condition. “Use the existing helper” is a direction; “avoid duplicating download logic and preserve the existing styling” clarifies what a satisfactory result should retain. Clear follow-ups reduce ambiguity, even though they cannot guarantee that an agent will make the right change.

## What makes a good steering message?

A steering message should focus on the part of the task that needs to change. It does not usually need to repeat the entire original prompt. A compact message can identify the problem, provide the missing constraint, and describe the intended direction.

For example:

- **Correct an assumption:** “This project uses pnpm, not npm. Follow the existing lockfile and scripts.”
- **Add a requirement:** “The endpoint must preserve the existing response format because current clients depend on it.”
- **Narrow the scope:** “Change only the authentication component; leave the unrelated UI refactor for later.”
- **Point to relevant context:** “Inspect the existing validation helper before adding a new one.”
- **Clarify the expected result:** “Include a regression test for the reported failure and explain how you verified it.”

These are suggested examples, not built-in command syntax. They are effective as instructions because they state the correction explicitly and make the desired outcome easier to review.

Avoid sending several conflicting directions in rapid succession. If the requirements have changed substantially, pause to clarify the desired end state in one message where practical. If the new work is unrelated to the current task, queuing it may be more orderly than expanding the active request. The best choice depends on whether the new information changes the current task or defines a later task.

## Why faster steering matters for coding workflows

The value of faster steering is not simply that a message might appear sooner. It is that a coding agent works within a changing set of requirements. In a real project, the user’s understanding of the problem improves as files are inspected and implementation choices become visible. A workflow that makes corrections easier can reduce the friction between initial intent and the work being produced.

For example, a developer may discover that a function has callers elsewhere in the repository, that a design pattern must be preserved, or that a test environment has a limitation. If the user can communicate that discovery while the agent is active, the agent has an opportunity to account for it before the task moves further in the wrong direction.

That is a practical implication of the feature, not a measured claim about time saved or fewer bugs. OpenAI’s release note does not quantify the improvement, publish a benchmark, or state that faster steering increases code correctness. The defensible conclusion is narrower: OpenAI is making steering in the desktop app respond sooner during a rollout, and steering is intended to help users correct or redirect a running task.

The benefit will vary by task. A short request that finishes immediately may offer little opportunity for steering. A longer task with multiple steps may create more occasions for a user to add context or change direction. That is a reasonable workflow inference, not a guarantee that every long-running task will respond better.

## Faster steering does not replace code review

A follow-up mechanism is a control for directing the agent, not a substitute for inspecting its work. Even a clear correction can be misunderstood or applied incompletely. A change that appears to solve the immediate issue may introduce a regression elsewhere, and a successful-looking response does not prove that tests passed.

After steering Codex, review the resulting diff. Check whether the changed files match the requested scope, whether existing conventions were preserved, and whether relevant tests or validation steps were run. If the agent says that it verified the change, inspect the reported commands and results when the task warrants it. For sensitive code, security-related work, or changes that affect production behavior, follow the project’s normal review and approval process.

Queued instructions also deserve review. A message saved for a future run may become stale if the current work changes the project. Before sending it, confirm that it still describes the intended next step. OpenAI’s support for editing, reordering, sending, or deleting queued messages makes that review possible in the desktop interface.

The practical principle is straightforward: steering helps communicate intent during execution; review establishes whether the final work actually meets that intent.

## What teams should consider

For individual developers, a default follow-up behavior is mainly a convenience. For teams, it can affect how people supervise agent-assisted work. A team that prefers narrow, sequential tasks may want developers to queue follow-ups that represent new work. A team that expects frequent clarification may favor steering when requirements change within an active task.

These are process choices rather than product rules. OpenAI’s release note does not prescribe a team policy or state that administrators must choose a single behavior for every project. Teams should base their approach on their own review practices, the complexity of their codebase, and the level of risk associated with changes.

A lightweight team convention can help: use steering for corrections that affect the current task; queue distinct follow-on work; and review diffs and test results before merging. This convention keeps the active task focused while still allowing the developer to respond to new information. Teams can adjust it when a task is exploratory or when a single change naturally requires several connected steps.

Managed workspaces may have their own permissions and configuration. OpenAI’s Codex documentation notes that workspace settings can affect access and available behavior. If a setting is missing or a feature behaves differently in an organization’s environment, users should check the applicable workspace controls rather than assume that every account has an identical setup.

## Availability and what remains unconfirmed

OpenAI says faster steering is rolling out in Codex on desktop and that availability varies during the rollout. That means the feature may not appear for all users at once. The official documentation does not provide a complete schedule for every plan, region, operating system, or account, so it would be inaccurate to promise a specific arrival date to an individual user.

The company’s Codex help article says Codex is included across ChatGPT plans, including Free and Go, although usage limits vary by plan. That general statement should not be confused with confirmation that every Codex feature or every stage of the faster-steering rollout is available to every subscriber. Feature availability and plan access are separate questions.

OpenAI has not published a specific percentage or number of milliseconds for the speed improvement in the release note. It also has not claimed in that note that steering guarantees interruption-free execution, automatically reverses earlier edits, or prevents coding mistakes. Those capabilities should not be inferred from the word “faster.”

The most reliable way to check current behavior is to consult the [official ChatGPT release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) and [Using Codex with your ChatGPT plan](https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan). OpenAI may update those pages as rollout details change.

## A simple workflow to try

If faster steering is available in your ChatGPT desktop app, try it on a small, low-risk coding task before relying on it for a large refactor. Start with a clear instruction and a defined acceptance condition. While Codex is working, decide whether a new message corrects the current task or describes a separate next step.

If it corrects the current task, use steering. Keep the follow-up focused: explain the missing constraint or the wrong assumption and say what should change. If it is a distinct next task, queue it. Review any queued messages before sending them, especially if the current run may change the code they refer to.

When the task finishes, inspect the diff and the verification results. If the correction was not applied as intended, give a more precise follow-up and review the next result. This method combines the convenience of mid-run guidance with the discipline of normal software engineering.

## The bottom line

OpenAI’s October 8, 2026 release note announces a rollout of faster steering in Codex in the ChatGPT desktop app. Steering lets users add a follow-up to the current run to correct an approach, add missing information, or change direction. Queuing saves a message for the next run after the current work finishes. The desktop app exposes a default under **Settings → General → Follow-up behavior**, while OpenAI documents Enter for steering and Tab for queuing in Codex CLI.

The update is useful because real coding work often changes as it progresses. Faster steering can make it easier to communicate a correction while a task is active, but OpenAI has not published a numerical speed benchmark or promised that every correction will be applied perfectly. Availability is still rolling out.

For developers, the most useful takeaway is to treat steering and queuing as two different workflow tools. Use steering when new information should affect the work underway; queue a follow-up when it belongs to the next run. Then review the code and tests as usual. Better communication can improve the process, but sound engineering judgment remains essential.

## Official OpenAI sources

- [ChatGPT release notes — “Faster steering in Codex,” October 8, 2026](https://help.openai.com/en/articles/6825453-chatgpt-release-notes)
- [Using Codex with your ChatGPT plan — steering and queuing instructions](https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan)
- [Codex for developers — official documentation](https://developers.openai.com/codex/)

*ChatGPTScope is an independent publication and is not affiliated with or endorsed by OpenAI. This article describes the official documentation checked on October 9, 2026; rollout status and product behavior may change.*

## Related Articles

- [GPT-6 and Intelligent UI: What the ChatGPT Update Changes](https://articlesaboutai.com/news/2026/10/09/gpt-6-intelligent-ui-chatgpt-update/)
- [How to Write Better ChatGPT Prompts](https://articlesaboutai.com/guides/2026/10/09/how-to-write-better-chatgpt-prompts/)
