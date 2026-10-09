---
author: Articles About AI Editorial Team
categories:
- news
date: "2026-10-10 00:23:00 +0300"
description: Anthropic launched Claude Haiku 5.5 on October 7 with lower API prices, adjustable effort, and beta computer and browser tools. Here is what developers need to know.
layout: post
tags:
- Anthropic
- Claude Haiku 5.5
- AI models
- API pricing
- AI agents
- Claude Platform
title: "Claude Haiku 5.5 Launch: Pricing, Benchmarks, Availability, and Developer Changes"
---

Anthropic introduced Claude Haiku 5.5 on October 7, 2026, positioning it as its fastest, cheapest, and most capable small model to date. The release targets high-volume work where latency and per-task cost matter: summaries, context compaction, classification, database queries, customer support, browser tasks, and the smaller steps that support a larger coding or business agent. Anthropic says Haiku 5.5 costs around 75% less to run on average than Haiku 4.5, although the exact saving depends on prompt length and the tokens a task consumes.

The launch is broader than a new model identifier. Anthropic also cut the price of cached input reads for Claude Sonnet 5.5 by 50%, introduced a monthly API-credit benefit for eligible Claude Max and Team subscribers, and announced beta support for computer use and browser use in its Python and TypeScript SDKs. Haiku 5.5 is available now on Anthropic’s platform and through Amazon Web Services, Google Cloud, and Microsoft Azure, according to the company. Its API model ID is `claude-haiku-5-5`.

## What Anthropic released

Claude Haiku 5.5 is the newest model in Anthropic’s small-model family. The company describes it as designed for frequent, cost-sensitive requests rather than as a universal replacement for larger models. It is intended to handle narrow tasks quickly and economically, including extracting information, summarizing content, classifying records, compressing conversation history, and performing short steps inside a larger agent workflow.

That positioning reflects a common design pattern in production AI systems. A complex application does not necessarily need its most capable model for every step. A lead agent may plan a task or make a difficult decision, while a smaller model handles repeated lookups, labels documents, summarizes intermediate results, or checks structured records. If the smaller model is sufficiently accurate, assigning it those subtasks can reduce response time and operating cost.

Anthropic says Haiku 5.5 pairs well with Claude Opus 5.5 and Claude Sonnet 5.5 as a subagent on coding work. A subagent is a specialized worker delegated a bounded part of a larger task. For example, a primary coding agent could ask Haiku to inspect a set of files, identify relevant functions, summarize test failures, or retrieve a value from a long document. The main agent can then use that result in its broader plan. The benefit depends on the reliability of the subtask and the cost of checking its output.

The release also adds an adjustable effort setting to the Haiku family for the first time, according to Anthropic. This gives developers a way to trade off reasoning effort against cost and latency rather than treating every request as if it required the same depth of processing.

## Pricing: the main change for high-volume applications

For prompts up to 100,000 tokens, Anthropic lists Haiku 5.5 input pricing at $0.10 per million tokens and output pricing at $0.50 per million tokens. For prompts over 100,000 tokens, the listed rates are $0.50 per million input tokens and $2.50 per million output tokens.

Cache reads cost $0.01 per million tokens for prompts up to 100,000 tokens and $0.05 for prompts over that threshold. Cache writes cost $0.125 and $0.625 per million tokens, respectively. For comparison, the launch page lists Haiku 4.5 at $1 per million input tokens and $5 per million output tokens, with cache reads at $0.10 and cache writes at $1.25 per million tokens. These are launch-page rates; developers should check current official pricing before deployment.

Anthropic says Haiku 5.5 costs around 75% less to run on average than Haiku 4.5. Its footnote explains that the new model is priced 90% lower for requests up to 100,000 tokens and 50% lower for longer prompts. The calculation also accounts for changes in token use: Haiku 5.5 has an updated tokenizer and can use slightly more tokens to complete a task. Teams should measure the total token count and success rate on their own prompts rather than assume that token-level savings translate directly into identical task-level savings.

Prompt length matters. Anthropic says roughly 90% of requests to its previous Haiku model fell within the up-to-100,000-token category. Applications that regularly exceed 100,000 input tokens face a different price tier and should evaluate whether sending the full context is necessary. Retrieval, summarization, or staged processing may reduce input, although these approaches introduce their own accuracy and orchestration trade-offs.

A useful cost comparison should include failed attempts, retries, output length, cache behavior, and human review. A model that costs less per request may not be cheaper overall if it makes more mistakes or requires repeated calls. Conversely, a small model that reliably completes a narrowly defined step may unlock workflows that were too expensive to run at scale with a larger model.

## Sonnet 5.5 cache reads are now cheaper

The Haiku launch includes a separate price reduction for Claude Sonnet 5.5. Anthropic says cache reads now cost $0.10 per million tokens, down from $0.20, a 50% reduction. The company estimates that this makes Sonnet 5.5 around 20% cheaper on most agentic tasks because cached input can account for a substantial share of token consumption.

Prompt caching lets an application reuse eligible portions of a prompt instead of paying the full input price every time those portions are sent again. It can be useful when an agent repeatedly works with the same instructions, tool definitions, or stable background material. The actual benefit depends on how the application structures requests and how much content qualifies for a cache hit.

The change does not mean every Sonnet request becomes 20% cheaper. Workloads with little cache reuse may see a smaller benefit. Developers should inspect cache-read and cache-write usage in their own billing data and compare cost per successful task before and after the pricing change. Haiku may be right for high-volume, bounded subtasks, while Sonnet remains preferable when a task needs stronger reasoning or more complex coding behavior.

## What the benchmarks say

Anthropic publishes comparisons across knowledge work, computer use, multidisciplinary reasoning, and agentic coding. On its page, Haiku 5.5 scores 1,620 on GDPval-AA v2.1 and 1,578 on AA-Briefcase v1.1, compared with 735 and 614 for Haiku 4.5 in the same table. On the offline subset of OSWorld 2.1, Anthropic reports 72.4% for Haiku 5.5 versus 15.7% for Haiku 4.5. On Humanity’s Last Exam, the reported score is 45.9% without tools and 57.4% with tools, compared with 10.2% and 18.7% for Haiku 4.5.

The page also reports 39.2% on Terminal-Bench 4.0 and 46.4% on FrontierCode 1.1 for Haiku 5.5. Anthropic provides a system card describing its evaluation process. Benchmark scores are not guarantees for a customer’s application: results depend on the test set, scoring rules, tools, prompts, settings, and evaluation harness. A model can do well on a general benchmark yet struggle with a company’s terminology, unusual data formats, or edge cases.

Anthropic explicitly says its larger models remain better choices for complex agentic coding tasks like those measured by Terminal-Bench 4.0. Haiku’s value proposition is strongest when the job is bounded enough for a smaller model to complete reliably, and frequent enough that reduced latency and cost matter. Developers should compare models on a representative private test set, not choose based on a single headline score.


## Adjustable effort gives developers another control

Haiku 5.5 is Anthropic’s first Haiku-class model with an adjustable effort setting. In practical terms, the setting lets a developer choose how much effort the model should apply to a request, balancing the potential value of deeper reasoning against response time and token cost. A simple classification task may not justify the same effort as diagnosing a subtle software failure or resolving conflicting evidence.

This control should be used deliberately. Lower effort can be appropriate when the task is repetitive, the expected answer is constrained, and mistakes are easy to detect. Higher effort may be warranted when the input is ambiguous or when the answer influences a consequential decision. The right setting cannot be determined by model name alone; it should be tested against measured quality and cost.

For a production application, evaluate several effort settings against the same task set. Record correctness, latency, token use, and the frequency of errors that matter to the business. A bounded output format can also help. If the application needs a label, a few fields, or a short summary, specify that output clearly and validate the result before using it. Structured validation will not eliminate model errors, but it can prevent malformed output from silently flowing into a database or downstream tool.

## Computer use and browser use in beta

Anthropic says it is updating its Claude Python and TypeScript SDKs to add support for computer use and browser use in beta. The company identifies Haiku 5.5 as a good fit for these tasks because of its combination of speed, capability, and price. These tools extend the ways a model can interact with software, but beta support should be treated as an integration that requires testing rather than a guarantee of reliable autonomous operation.

Computer use and browser use can support workflows that involve reading information on screen, navigating web pages, or interacting with a software interface. Such workflows are sensitive to unexpected page layouts, changing application state, authentication steps, timeouts, and ambiguous controls. A model can misunderstand what is visible or take an action that is not appropriate for the current state. Developers should build safeguards around actions that change data, send messages, make purchases, or affect user accounts.

A robust implementation should separate observation from authorization. The model can propose an action, while the surrounding application checks whether it is permitted and whether the relevant state still matches expectations. Sensitive operations should require suitable confirmation or human oversight. Logging tool calls and results makes it easier to investigate failures. Since SDK support is beta, developers should review the current official documentation for exact interfaces and limitations, and test error handling, permissions, and recovery behavior before exposing a workflow to real users.

## Availability across platforms

Anthropic says Claude Haiku 5.5 is available now on all platforms, including Amazon Web Services, Google Cloud, and Microsoft Azure. On the Claude Platform, developers can use the model ID `claude-haiku-5-5`. The availability statement is broader than a limited research preview, but developers should still verify the model’s status, regional availability, account permissions, and deployment details with the provider they use.

Organizations using a cloud marketplace or managed model service may have separate configuration, billing, quota, and access-control requirements. A model being listed on a provider platform does not guarantee that every account has immediate access in every region. Check the provider’s model catalog and service documentation before planning a migration or promising a delivery date to customers.

Before switching production traffic, record the model identifier and configuration used for evaluation. Run a canary or limited pilot, compare the new model with the existing baseline, and retain a rollback path. This is particularly important for agents, where a small change in behavior can affect a long chain of actions. The tokenizer change also means cost and output-length baselines should be measured again.

## API credits for Max and Team subscribers

Anthropic announced a monthly API-credit benefit for Claude Max and Team subscribers, intended to help them experiment with tools, applications, and agents built on the Claude Platform. According to the launch page, Max 5x subscribers receive $100 in credits per month, Max 20x subscribers receive $200, and Team subscribers receive up to $500 pooled across their users. The credits can be used with any of Anthropic’s models.

Anthropic said the benefit would roll out during the week of the announcement. Eligible subscribers should check the company’s official help information and account interface for current terms, activation details, and restrictions. The credits are intended to support API experimentation; they should not be assumed to cover unlimited production usage or replace a budget.

For a developer evaluating Haiku 5.5, the benefit may make it easier to build a proof of concept, test prompts, and compare model configurations without immediately committing a separate budget. A proof of concept should still track usage. If the application becomes popular or starts running long agent sessions, production costs may differ substantially from the initial experiment. Teams should understand who can consume pooled credits, how usage is reported, and what happens when the monthly amount is exhausted.

## Safety and capability boundaries

Anthropic reports improvements in Haiku 5.5’s alignment evaluations relative to Haiku 4.5, including fewer observed instances of misaligned behavior and a lower willingness to cooperate with misuse. The company also says Haiku 5.5 has more restrictive cybersecurity safeguards than Haiku 4.5, although they are somewhat less restrictive than those applied to Sonnet 5.5. In cybersecurity, the model permits a wider range of defensive tasks than Sonnet 5.5 but still blocks penetration testing and other techniques considered more likely to be used by attackers.

Anthropic says its biology safeguards match those used for Sonnet 5, Sonnet 5.5, and Opus 5: research biology questions are allowed, while requests judged likely to cause harm are restricted. Organizations undertaking broader biology or cybersecurity work can review the company’s verification programs. These are policy and product descriptions from Anthropic, not a substitute for an organization’s own risk assessment.

A model’s safeguards do not eliminate the need for application-level controls. Teams should restrict tools to the actions required for a task, protect credentials, validate model-generated commands, and prevent untrusted content from overriding trusted instructions. Where an agent can modify files, communicate externally, or affect production systems, the application should enforce permissions independently of the model’s judgment. High-impact deployments should supplement the system card with threat modeling, adversarial testing, monitoring, and incident-response procedures.

## A practical evaluation plan

Teams considering Haiku 5.5 should begin by identifying tasks that dominate their AI bill or create unacceptable delays. Good candidates include high-volume summaries, classification, document lookups, context compaction, and short subagent steps. Do not begin by replacing every model in a system. Start with one bounded workload whose success can be measured objectively.

Build a test set from real examples, including routine inputs, ambiguous cases, malformed data, and cases where the correct response is to abstain or request more information. Define acceptable output before running the comparison. Test Haiku 5.5 alongside Haiku 4.5 and the larger model currently used for the task, keeping prompts, tools, and scoring rules consistent wherever possible.

Measure total cost per successful task rather than price per million tokens alone. Include input and output tokens, cache reads and writes, retries, latency, and human corrections. If adjustable effort is available for the workload, compare settings systematically. For an agent workflow, evaluate the entire sequence and inspect tool actions, not just the final answer.

Then run a limited production pilot with monitoring and a rollback plan. Record the model identifier, configuration, and evaluation date so that later comparisons remain meaningful. For computer-use or browser-use features, test permission boundaries and failure recovery separately before allowing consequential actions. Re-evaluate the model when prompts, tools, or provider versions change.

## Who should consider Claude Haiku 5.5?

Haiku 5.5 is particularly relevant to teams running many small AI requests, building multi-agent systems, or trying to reduce the cost of routine model work. Its lower listed token prices may make certain workloads more economical, and its adjustable effort setting gives developers another way to balance quality against latency and expense. The announced beta computer and browser support may also interest developers building interactive agents.

It is less compelling as an automatic replacement for a larger model on tasks that demand deep reasoning across many steps. Anthropic itself positions Sonnet 5.5 and Opus 5.5 as better options for complex agentic coding. The correct comparison should include both model quality and the cost of supervision, retries, and correction.

The model is available through multiple platforms, which may help teams evaluate it within existing cloud arrangements. Yet platform access, quotas, regional options, and billing can vary, so each organization should confirm the exact conditions for its deployment. The release is a reason to run a controlled benchmark—not a reason to skip one.

## The bottom line

Claude Haiku 5.5 is a significant update to Anthropic’s small-model offering because it combines improved reported capability with much lower token prices and a clearer role in multi-model agent systems. The October 7 release also lowers Sonnet 5.5 cache-read prices, adds API credits for eligible Max and Team subscribers, and brings computer-use and browser-use support into beta in the Python and TypeScript SDKs.

The strongest use case is not necessarily to make Haiku the only model in an application. It is to assign the model the high-volume, well-defined tasks it can perform reliably, while reserving larger models for work that genuinely needs them. Teams that test accuracy, latency, token use, and human review on representative tasks will be best placed to determine whether the new model improves economics without sacrificing quality.

## Official sources

- Anthropic, “Claude Haiku 5.5” (October 7, 2026): https://www.anthropic.com/claude-haiku-5-5
- Anthropic Newsroom: https://www.anthropic.com/news
- Claude Platform documentation: https://platform.claude.com/docs
- Anthropic Help Center: https://support.claude.com/
