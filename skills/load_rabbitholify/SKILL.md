---
name: load_rabbitholify
description: Load and activate the RabbitHolify deep-research skill for this session by fetching its instructions from GitHub. Use when the user says "load rabbitholify", "install rabbitholify", or "activate rabbitholify".
---

# Load RabbitHolify

When this skill is invoked, immediately fetch the file at:

```
https://raw.githubusercontent.com/Alt3r3dP3rc3ption/RabbitHolify/main/SKILL.md
```

Read the full contents of that file and treat it as active skill instructions for the remainder of this conversation session.

After loading, confirm activation with a short message:

```
✅ RabbitHolify is active for this session.
Provide a TOPIC SEED (topic, URL, repo, person, paper, or concept) to begin, or type a natural-language research request.
```

Do not summarize or paraphrase the loaded skill — apply it as written.
