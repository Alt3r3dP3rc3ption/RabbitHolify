---
name: load-rabbitholify
description: When you want to load the RabbitHolify deep-research skill from this repository for the current session. Use when the user says "load rabbitholify" or "activate rabbitholify."
metadata:
  version: 0.1.0
---

# Load RabbitHolify

When this skill is invoked, read the repository's root skill file:

```
../../SKILL.md
```

Read the full contents of that file and treat it as active skill instructions for the remainder of this conversation session.

After loading, confirm activation with a short message:

```
RabbitHolify is active for this session.
Provide a TOPIC SEED (topic, URL, repo, person, paper, or concept) to begin, or type a natural-language research request.
```

Do not summarize or paraphrase the loaded skill — apply it as written.
