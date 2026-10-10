---
layout: post
title: "How to Use Microsoft Copilot in Excel: Formulas, Data Analysis, and Charts"
description: "Learn how to use Microsoft Copilot in Excel to generate formulas, clean data, analyze trends, build PivotTables and charts, and verify AI-generated results."
date: 2026-10-11 04:45:00 +0300
categories:
  - guides
tags:
  - Microsoft Copilot
  - Excel AI
  - spreadsheet analysis
  - Excel formulas
  - data visualization
image: "/assets/images/microsoft-copilot-excel-workbook-insights.svg"
author: "Articles About AI Editorial Team"
---

Microsoft Copilot in Excel can help turn a plain-language request into a formula, a summary, a PivotTable, a chart, or a set of workbook edits. Instead of remembering every function or building each view manually, you can describe the result you need and review the suggested work inside Excel. That makes Copilot useful for sales reports, budgets, inventory lists, survey results, project trackers, and other structured data.

It is not a substitute for understanding the numbers. An AI-generated formula can encode the wrong assumption, a chart can emphasize an unhelpful comparison, and a summary can overlook an exception. The reliable approach is to treat Copilot as an assistant that accelerates spreadsheet work while you remain responsible for the data, the logic, and the final decision.

This guide explains how to get started, which tasks Copilot can help with, how to write effective prompts, and how to check its output before sharing a workbook. Microsoft's feature set, account requirements, and interface can change, so the official [Get started with Copilot in Excel guide](https://support.microsoft.com/en-us/excel/copilot/get-started-with-copilot-in-excel) should be your reference for current availability.

## What can Copilot do in Excel?

Copilot is integrated with Excel workflows rather than being only a separate chatbot. Depending on your account, application, and enabled features, it can help generate or explain formulas, summarize a dataset, identify patterns, create charts and PivotTables, clean or format data, and make changes to a workbook from natural-language instructions. Some experiences can also work across sheets or draw on supported files stored in Microsoft 365 locations.

Typical tasks include:

- **Formula help:** Ask for a calculation, lookup, conditional result, or explanation of an existing formula.
- **Data exploration:** Ask which categories are largest, how a metric changes over time, or where unusual values appear.
- **Summaries:** Turn a table of sales, expenses, feedback, or project status into a concise set of findings.
- **Visualization:** Create a chart or PivotTable that makes a comparison or trend easier to inspect.
- **Workbook editing:** Request changes to cell ranges, formatting, tables, worksheets, and other supported workbook elements.
- **Data preparation:** Find inconsistencies, standardize entries, or identify possible duplicates before analysis.

Not every capability appears in every Excel version or subscription. Availability may depend on your Microsoft 365 plan, organizational settings, platform, rollout status, and whether the workbook is stored in a supported location. If Copilot is missing, check your license and your organization's settings before assuming the feature is broken.

## Prepare your workbook before asking questions

Copilot works best when the underlying data is organized. AI cannot reliably infer every business rule from a poorly structured worksheet, and vague column names make it harder to interpret the information correctly.

Before you begin, make the data easy to read:

1. **Use one header row.** Give each column a clear, unique name, such as Order Date, Region, Product, Units, Revenue, and Cost.
2. **Keep each row to one record.** Avoid mixing subtotals, explanatory paragraphs, and blank spacer rows into the middle of the data table.
3. **Use consistent formats.** Dates should be real date values, currency should be consistently represented, and numeric fields should not contain a mixture of numbers and text.
4. **Remove or resolve obvious structural problems.** Check merged cells, duplicate headers, incomplete records, and accidental blank columns.
5. **Convert the range to an Excel table when appropriate.** Select a cell in the data and use Insert > Table, or the relevant table command in your version of Excel. Tables give data a clear structure and expand more predictably as records are added.
6. **Keep a recoverable original.** Save a copy or use version history before allowing AI-assisted edits to an important workbook.

Microsoft's [Analyze Data in Excel guidance](https://support.microsoft.com/en-us/excel/analyze-data-in-excel) similarly recommends clean, tabular data with clear headers. Preparation is not busywork: it reduces ambiguity and makes both the AI's interpretation and your verification easier.

## How to open Copilot in Excel

The exact interface depends on the Excel version and your account. In supported Microsoft 365 experiences, open the workbook and look for the Copilot control on the Home ribbon or in the workbook interface. Follow the sign-in and licensing prompts if they appear. If the control is absent, consult Microsoft's current [Copilot in Excel setup guide](https://support.microsoft.com/en-us/excel/copilot/get-started-with-copilot-in-excel) and verify that your plan and administrator settings support the feature.

Some editing experiences require a workbook saved to OneDrive or SharePoint with AutoSave enabled. This is especially important for workflows that need Copilot to make or coordinate changes to a workbook. Do not assume that every feature works with every local file, account type, or deployment channel.

Once Copilot is available, start with a narrow task and inspect the proposed result. For consequential work, avoid asking it to make many unrelated changes in one instruction. A sequence of smaller requests makes it easier to identify a wrong assumption and undo a problematic edit.

## Generate and understand Excel formulas

Formula generation is one of the most practical uses for Copilot. You can describe the calculation in everyday language and ask for a formula that fits your column layout. For example:

> Add a column called Gross Margin that calculates (Revenue - Cost) / Revenue for each row. Return a blank when Revenue is zero or missing, and explain the formula before applying it.

This prompt does more than ask for a formula. It names the output column, states the calculation, defines an edge case, and asks for an explanation. Those details reduce the chance that the assistant will make an unstated assumption.

Other useful formula requests include:

- “Calculate the percentage change between this month's revenue and last month's revenue, and handle a zero starting value explicitly.”
- “Create a column that labels each order as On Time or Late using the promised date and delivery date.”
- “Use XLOOKUP to retrieve the current unit price from the Products table by product ID. Flag IDs that have no match.”
- “Explain the formula in cell G12 in plain English, including what each reference points to.”
- “Check whether this formula uses relative or absolute references correctly when filled down the column.”

Always test generated formulas against a few rows where you can calculate the expected answer independently. Include boundary cases: a blank value, zero, a negative number if valid, a missing lookup key, and a date near the reporting boundary. Inspect the formula itself, not just the displayed result. A formula can return a plausible number while implementing the wrong business definition.

Also be careful with percentages. A margin calculated as (revenue minus cost) divided by revenue is not the same as markup calculated as profit divided by cost. If the distinction matters, state the definition in your prompt.

## Analyze a dataset and find meaningful patterns

Copilot can help you explore a table without requiring you to build every summary manually. Ask a specific question, identify the columns that matter, and request a format that will help you inspect the answer.

For a sales table, for example:

> Analyze the Orders table for the period January through June. Compare revenue by region and product category, identify the three largest month-over-month declines, and show the results in a summary table. State which columns and date range you used, and do not infer a cause that the data does not establish.

For customer feedback:

> Group the comments in the Feedback column into recurring themes. Add a new column with a short theme label for each row, then summarize the most frequent themes. Treat the labels as suggestions for review, and do not invent customer comments.

For inventory:

> Identify products whose stock quantity is below the reorder threshold. Show product ID, current stock, threshold, and the difference. Do not change the source data.

These prompts define the question, the relevant fields, the output, and an important limit. That is usually more useful than “Analyze this data” because the assistant has a clearer standard for success.

For additional examples, Microsoft maintains a [Copilot data-insights guide](https://support.microsoft.com/en-au/excel/copilot/data-insights-with-copilot-in-excel). It covers natural-language questions, trends, outliers, formula columns, and lookups. Remember that a detected correlation or trend does not automatically explain why it occurred. If revenue dropped in March, the spreadsheet may show where the drop happened; it may not contain enough evidence to identify the cause.

## Create charts and PivotTables

Charts and PivotTables help turn a large table into a view that people can understand quickly. Copilot can help create them from a plain-language request, but the request should specify the comparison you want to make.

Examples:

> Create a line chart showing monthly revenue from January to December. Use Month on the horizontal axis, Revenue on the vertical axis, and a separate series for each region. Keep the underlying data unchanged.

> Create a PivotTable with product category in rows, quarter in columns, and total revenue as the values. Add a grand total and sort categories from highest to lowest total revenue.

> Compare actual spend with budget by department in a clustered column chart. Use the same currency scale for both series and label the chart clearly.

After the chart appears, check the axes, units, date range, category order, and aggregation. A chart showing average revenue can tell a different story from one showing total revenue. A truncated axis can exaggerate a small difference. A PivotTable can also group dates or aggregate values in a way that does not match your reporting rules.

Microsoft's [visualize data with Copilot in Excel guide](https://support.microsoft.com/en-us/excel/copilot/visualize-your-data-with-copilot-in-excel) describes supported chart, PivotTable, sorting, filtering, and highlighting workflows. Use it for current interface guidance and then review the result in your own workbook.

## Clean and standardize messy data

Data cleaning is a strong use case when a spreadsheet contains inconsistent labels, formatting, or text. For example, a Region column might include “North,” “north,” and “N.”, while a customer list may contain extra spaces or inconsistent date formats.

You can ask Copilot to identify potential problems and propose a cleanup plan:

> Inspect the Region and Product columns for inconsistent spellings, capitalization, and trailing spaces. List the distinct variants and recommend a normalized value for each. Do not overwrite the original columns until I review the mapping.

For duplicate records:

> Find rows that may represent duplicate orders using Order ID as the primary key. Show exact duplicates separately from possible duplicates where the IDs differ but customer, date, and amount match. Do not delete anything.

This distinction matters. Two rows that look similar may be legitimate separate transactions. Conversely, two records with different IDs may represent a data-entry problem. Ask for a review list first, define the fields used for matching, and preserve the original data until you approve the changes.

For text-heavy sheets such as survey results or support tickets, Copilot may help summarize themes or label rows. Treat those labels as AI-generated classifications, not ground truth. Check a sample from each theme and review ambiguous or sensitive comments manually.

## Use a repeatable prompt structure

For recurring spreadsheet work, use a prompt pattern that makes the task testable. A reliable structure is:

- **Goal:** What decision or output do you need?
- **Data:** Which table, columns, worksheet, and date range should be used?
- **Method:** What calculation, grouping, comparison, or rule should be applied?
- **Output:** Do you need a formula, summary table, chart, PivotTable, or proposed edit?
- **Constraints:** What must remain unchanged, and what assumptions must be stated?
- **Verification:** What should Copilot explain or show so you can check the result?

A reusable example:

> Goal: prepare a monthly operations review. Data: use the Orders table and the Order Date, Region, Units, Revenue, and Cost columns for the latest complete quarter. Method: calculate total revenue, total cost, and gross margin by region; compare each region with the previous quarter. Output: a summary table and one chart. Constraints: exclude incomplete orders, state how missing values were handled, and do not infer causes from correlations. Verification: show the formulas and source columns used, and list any assumptions that could change the result.

Do not treat this template as a magic phrase. Its value is that it states what counts as a correct answer. Tailor it to your actual data, and remove instructions that are irrelevant to the task.

## Verify the result before sharing it

A fluent explanation is not evidence that a spreadsheet calculation is correct. Use a consistent review process:

1. **Confirm the scope.** Did Copilot use the intended worksheet, columns, filters, and reporting period?
2. **Inspect formulas and transformations.** Check cell references, lookup keys, aggregation functions, rounding, and error handling.
3. **Recalculate a small sample independently.** Choose records with known expected results, including edge cases.
4. **Reconcile totals.** Compare key totals before and after a transformation. If rows were filtered or excluded, document why.
5. **Review charts.** Check units, axis scales, labels, series, and whether totals or averages are displayed.
6. **Separate observations from explanations.** “Revenue declined 12%” may be supported by the data; “the campaign caused the decline” requires additional evidence.
7. **Review edits before accepting them.** Use Excel's undo, version history, or a saved copy if the changes are not correct.
8. **Protect sensitive information.** Follow your organization's rules for sharing data with Microsoft 365 services and avoid placing confidential information in a workbook unless the applicable policy permits it.

For high-impact financial, compliance, staffing, or operational decisions, have a qualified person review the workbook logic and source data. AI assistance can speed up analysis, but responsibility for the final figures remains with the people who use and publish them.

## Common Copilot in Excel problems

### Copilot is missing

Check your Microsoft 365 subscription, signed-in account, application version, and organization settings. Feature availability can differ across personal and work accounts, platforms, and rollout stages. Microsoft's setup guide is the best starting point.

### Copilot gives a generic or irrelevant answer

Narrow the task and name the table and columns. Specify a date range, aggregation method, and desired output. If the result is still wrong, break the request into smaller steps and inspect each one.

### It cannot interpret the worksheet

Check for multiple header rows, merged cells, inconsistent data types, blank labels, or data stored as text. Convert the relevant range into a clean table and try again. Complex layouts may need to be reshaped before analysis.

### The formula looks correct but the total is wrong

Verify the formula definition, row range, filters, and treatment of blanks or zero values. Test individual records and compare the total with an independent calculation. In particular, clarify whether you need margin, markup, average, weighted average, count, or distinct count.

### It changes more than expected

Make a copy before broad edits. Ask for a proposed change or a review list before applying it, where the interface supports that workflow. Keep prompts limited to one coherent task and inspect the workbook after each change.

### You are looking for the old COPILOT worksheet function

Do not build a new workflow around outdated instructions for the experimental =COPILOT() function. Microsoft's Excel team announced that the function would no longer be available starting September 14, 2026, directing users to the Copilot side pane for supported AI-assisted tasks. See the official [Microsoft 365 Insider Blog announcement](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/bring-ai-to-your-formulas-with-the-copilot-function-in-excel/4443487/replies/4446148) and check current Microsoft documentation before relying on older tutorials.

## Copilot in Excel versus asking an AI chatbot

A spreadsheet-native assistant is useful when you want to work with supported workbook structures and keep formulas, tables, and charts editable in Excel. A general AI chatbot can be useful for brainstorming an analysis plan, explaining a formula, or discussing a dataset you are permitted to share. The right choice depends on the task, data sensitivity, available integrations, and the need to edit the workbook directly.

If you are analyzing a document rather than a spreadsheet, our guide to [uploading files to ChatGPT and analyzing them](/how-to-upload-files-to-chatgpt-and-analyze-them/) explains a different workflow. The tools are not interchangeable in every situation: choose the one that fits the file type and the controls available to you, and verify the results regardless of which assistant you use.

## Final thoughts

Microsoft Copilot in Excel is most useful when you give it a clearly defined spreadsheet task, provide well-structured data, and ask for an output you can inspect. It can help draft formulas, explore trends, create PivotTables and charts, and propose cleanup steps. Its value comes from reducing repetitive work and making analysis easier to start—not from guaranteeing that every result is correct.

Begin with a low-risk task, specify the columns and rules, and review the result against the source data. For recurring reports, save a tested prompt and a short verification checklist. That approach makes the workflow more repeatable while keeping the important decisions—definitions, assumptions, and final approval—in human hands.

## Official sources

- [Microsoft Support: Get started with Copilot in Excel](https://support.microsoft.com/en-us/excel/copilot/get-started-with-copilot-in-excel)
- [Microsoft Support: Get data insights with Copilot in Excel](https://support.microsoft.com/en-au/excel/copilot/data-insights-with-copilot-in-excel)
- [Microsoft Support: Visualize your data with Copilot in Excel](https://support.microsoft.com/en-us/excel/copilot/visualize-your-data-with-copilot-in-excel)
- [Microsoft Support: Analyze Data in Excel](https://support.microsoft.com/en-us/excel/analyze-data-in-excel)
- [Microsoft 365 Insider Blog: COPILOT function availability update](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/bring-ai-to-your-formulas-with-the-copilot-function-in-excel/4443487/replies/4446148)
