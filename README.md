# RabbitHolify

RabbitHolify, formerly Deep Research Loop, turns any topic, URL, repository, person, paper, podcast, company, or concept into an interactive, source-backed research chain.

Each loop preserves findings, citations, verbatim excerpts, precise locators, contradictions, dead ends, and open branches. Continue with a single number, branch into a promising thread, synthesize across loops, export the chain, or stop with a final research report.

## Install

Copy this repository to your Codex skills directory:

```bash
git clone --branch v1.1.0 --depth 1 https://github.com/Alt3r3dP3rc3ption/RabbitHolify.git ~/.codex/skills/rabbitholify
```

Restart Codex, then invoke the skill:

```text
Use $rabbitholify to research:

TOPIC SEED: <topic or URL>
OPTIONAL CONTEXT: <what you already know>
OPTIONAL FOCUS: <the angle to prioritize>
```

Natural-language requests work too:

```text
Use $rabbitholify to investigate the architecture and failure modes of local-first software.
```

For traceable document research:

```text
Use $rabbitholify in verbatim evidence mode on these contracts, specifications,
and drawings. Give every excerpt a quote ID, reproduce it exactly, and cite the
file, revision, page or sheet, clause/detail, and a clickable source link.
```

## Loop controls

| Choice | Action |
|---:|---|
| 1 | Go deeper |
| 2 | Follow the highest-ranked branch |
| 3 | Synthesize completed loops |
| 4 | Start a new seed |
| 5 | Show the loop map |
| 6 | Export the research chain |
| 7 | Give a custom direction |
| 0 | Stop with a final synthesis |

## Design

- Source-backed: factual findings cite accessible evidence.
- Verbatim when requested: exact excerpts remain separate from analysis and carry source links, version identifiers, and page/clause/sheet-level locators.
- Local-first: authorized personal files can be quoted exactly without uploading them; third-party exports can use stable source IDs instead of exposing private paths.
- Stateful: later loops build on earlier findings without repeating them.
- Honest about limits: inaccessible sources, rejected evidence, contradictions, and bounded graph traversals stay visible.
- Self-terminating: choice `0` closes the chain cleanly.

## License

Apache-2.0
