---
name: grill-me
description: Interview the user in rounds to resolve ambiguous requirements, conflicting constraints, and open design decisions. Use when the user invokes $grill-me or explicitly asks to be grilled on a task, plan, or idea.
---

# Grill Me

## Before each round

Read the relevant code, tests, configuration, or documentation first. Verify facts you can discover directly using read-only tools. Ask the user when a material requirement, preference, or tradeoff is still unclear, or when their instructions conflict. State the exact conflict and what it affects.

Group independent questions in the same round. Defer any question that depends on an unanswered decision. Keep each question focused on one concrete choice and give enough context to answer it without guessing. Use the user's language for the interview.

If the conversation has no interview subject, ask what to examine. Offer ways to supply it, such as describing a goal, naming a file or feature, or sharing a draft plan.

## Ask and pause

Give exactly three distinct, actionable answers per question. Put the recommendation first and start it with the literal `(Recommended)`. Follow it with two credible alternatives. When helpful, briefly state the consequence of each choice. Leave the fourth choice for the user's own answer.

- Prefer a native blocking question tool when it is available, allowed, and supports the required option label. Supply the three predefined answers and let the tool provide its built-in free-text field. Wait for the tool to return the user's submitted answers.
- If a native asynchronous form supports the format, submit the round in one call. As the very next action after successful submission, end the turn with a brief waiting message. The form call returning, a preselected option, or an elapsed timeout does not count as an answer.
- Otherwise, ask the entire round in the final message and end the turn. Number the questions and use `A. (Recommended) ...`, `B. ...`, `C. ...`, and `D. Your own answer` for each one. Invite the user to reply by question number and letter or write their own answer.

Once a round is sent, suspend all reasoning and execution until the user actually responds. Make no further tool calls, file reads, edits, drafts, or background work. Do not infer consent from silence or automatically choose the recommendation.

## Resume after a reply

Apply the answers the user actually gave. If a required answer is missing or unclear, ask for that decision again alongside any newly unblocked independent questions. Honor requests to delegate a decision or end the interview. Reopen a settled decision only when new evidence or a user correction changes it.

When the material decisions are settled, summarize them briefly and close the interview. Continue into implementation only if the user has already asked you to proceed once the interview is settled or explicitly asks you to proceed now.
