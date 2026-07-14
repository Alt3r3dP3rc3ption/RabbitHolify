---
name: rabbitholify
description: Run an interactive, stateful deep-research chain for any topic, URL, repository, person, paper, podcast, company, or concept. Use when the user wants iterative source-backed investigation, research branches, GitHub graph analysis, cross-loop synthesis, a research map, an export, or a clean final synthesis controlled by a numbered menu.
---

# RabbitHolify

Investigate a seed in successive, non-repeating loops. Preserve research state in the conversation, use current primary sources where possible, expose contradictions and dead ends, and let the user steer each next loop with one digit.

## Start

Accept a natural-language request or these optional fields:

```text
TOPIC SEED: <topic, URL, repo, person, paper, podcast, company, or concept>
OPTIONAL CONTEXT: <facts not to re-research>
OPTIONAL FOCUS: <priority angle>
```

If the seed is clear, begin immediately. Ask only when no usable seed exists. Browse whenever current or source-backed information is required. Treat user-provided context as a lead unless the user explicitly marks it as an assumption.

## Maintain State

Track internally across the conversation:

- original seed and current focus
- cycle and loop numbers
- established findings; do not re-research them without a verification reason
- accepted, rejected, and inaccessible sources with the claims or reason attached
- contradictions, dead ends, completed branches, and open branch targets
- source counts and loop summaries

Start every research response with:

```text
[Cycle N | Loop M | Topic: <topic> | Depth: <current depth>]
Known: <what prior loops established>
This loop adds: <new scope>
```

For the first loop, omit `Known` or state that research is starting cold.

## Research Rules

1. Prefer primary and authoritative sources. Use independent corroboration for important contested or consequential claims when available.
2. Cite factual claims near the claim using the host platform's supported link or citation format. Never invent citations or claim access that did not occur.
3. Distinguish reported fact, source interpretation, and your inference.
4. Record material source conflicts, assess provenance, recency, expertise, and directness, then give a justified conclusion or leave the issue unresolved.
5. Advance beyond prior loops. Revisit a finding only to verify, contradict, or deepen it.
6. Report meaningful dead ends and failed retrievals because they prevent duplicate work.
7. Bound scope by relevance, available access, and the user's question. Do not claim exhaustive coverage of the web, all repositories, all contributors, all issues, or all stargazers unless tools actually establish it.
8. Respect access controls, privacy, copyright, rate limits, and tool constraints. Summarize protected or lengthy text instead of reproducing it.

## Choose the Loop

### Territory Loop

Use for a new seed. Cover the relevant subset of:

1. Territory: definitions, origins, authoritative voices, and disagreements.
2. Decomposition: components or dimensions with concrete examples.
3. People: key practitioners, affiliations, contributions, and public work.
4. Code: important repositories, activity, architecture, maintainers, dependencies, and forks.
5. Content: primary papers, articles, talks, podcasts, and other substantive material.
6. Failure modes: critiques, incidents, post-mortems, limitations, and dissent.
7. Open questions: specific gaps in evidence, tooling, or understanding.

Prioritize sections relevant to the seed; do not pad thin sections.

### Deepening or Branch Loop

Use after choice `1`, `2`, or a custom direction. Give one concise baseline paragraph, then add new evidence about:

- the people and collaborations behind the thread
- code, architecture, decisions, issues, and forks
- primary sources behind earlier claims
- contradictions and competing approaches
- what the deeper understanding enables

For choice `2`, follow the highest-ranked open branch unless the user names another.

### GitHub Graph Loop

Use when the focus is a repository, organization, contributor, or fork network. Inspect the most relevant accessible nodes and report:

- repository purpose verified against key files, not only taglines
- activity signals and important contributors with commit/PR/issue evidence
- architecture and agent-instruction files, summarized with file paths and commit SHAs when available
- material upstream dependencies and downstream forks
- design decisions revealed by PRs, issues, discussions, and releases
- relevant public connections between people and projects

Do not reproduce whole instruction files or enumerate huge graphs. State sampling or access limits and identify the next nodes worth walking.

### Synthesis Loop

Use for choice `3`. Introduce no new research. Derive only from completed loops:

- cross-loop insights supported by at least two loops
- recurring technical, social, or propagation patterns
- a concise person-to-contribution evidence table when useful
- consensus, dissent, and genuinely unsettled questions
- contradiction and dead-end registers
- a unified source ledger
- the strongest next-cycle seed, preloaded with known facts, starting sources, and unanswered questions

### Map, Export, and Stop

- `5` Map: show completed loops, open branches, dead ends, current position, and source counts.
- `6` Export: compile a standalone structured report with findings, methods, limitations, contradictions, open questions, and the unified ledger.
- `0` Stop: produce a final synthesis with chain statistics, up to ten most important new findings, up to five unresolved questions, concrete next actions, and final source counts. End the chain without showing the continuation menu.

## End Each Active Loop

Finish every research, synthesis, map, or export response with these sections.

### Source Ledger

- `ACCEPTED`: source, link/identifier, and exact claim supported.
- `REJECTED`: source and concrete reason, only for sources actually assessed.
- `INACCESSIBLE`: source, attempted access method, and result.

Do not inflate the rejected or inaccessible lists merely to fill them.

### Branch Targets

Rank 5-10 specific unexplored threads by expected value and explain each in one line. Use fewer only when fewer honest branches exist.

### Menu

Render exactly:

```text
---
## CONTINUE? Choose your next move:

[1] Go deeper - drill further into what was just covered
[2] Branch - follow the highest-ranked open Branch Target
[3] Synthesize - connect findings across completed loops without new research
[4] New seed - begin a fresh cycle while retaining prior context
[5] Show loop map - display completed loops, open branches, and source counts
[6] Export - compile the chain into one structured report
[7] Custom - follow the direction I type
[0] STOP - exit with a final synthesis and complete source ledger

Type a number or 0 to stop.
---
```

Interpret a bare digit as the corresponding action while this skill is active. For `4`, request the new seed only if the user did not include it. For `7`, request the direction only if it was not included.
