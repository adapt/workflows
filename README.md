# Adapt Workflows

A curated, open catalog of real workflows you can run with [Adapt](https://adapt.com), the open platform for company agents.

Every workflow here is a self-contained skill (a `SKILL.md` plus any supporting files) that you can:

1. **Add to Adapt directly** by pointing the Skills page at this repo as a GitHub source (`adapt/workflows`, path `workflows/`), or
2. **Download as a zip** from [adapt.com/workflows](https://adapt.com/workflows) and upload it into Adapt, or drop it into any other tool that reads the `SKILL.md` format.

These are the same workflows our own team runs internally, generalized so any team can use them.

## Repository layout

```
workflows/
  <workflow-slug>/
    SKILL.md        # the skill itself (name + description frontmatter + instructions)
    catalog.json    # website metadata: department, summary, integrations, cadence
    ...             # any supporting files the skill needs
scripts/
  build.py          # packages each workflow into dist/<slug>.zip + dist/catalog.json
```

`SKILL.md` is the single source of truth for behavior. `catalog.json` only drives the
website listing. Downloadable zips are generated from source (`scripts/build.py`), never
committed, so the download always matches what you can read here.

## Available workflows

| Workflow | What it does | Department | Integrations |
| --- | --- | --- | --- |
| [Code Janitor](workflows/code-janitor) | Always-on agent that opens small, safe cleanup PRs behind your CI gates | Engineering | GitHub, Slack, Linear (optional) |
| [Code Review](workflows/code-review) | Senior-engineer PR review that hunts for real bugs and posts severity-tiered findings | Engineering | GitHub, Slack (optional) |
| [Bug Triage](workflows/triage-bugs) | Investigates inbound bug reports, attempts reproduction, then fixes, files, deduplicates or declines with evidence | Engineering | Slack, GitHub, Linear |
| [Docs & Changelog](workflows/public-docs) | Verifies shipped behavior, updates public docs and the changelog together, and opens a draft docs PR | Engineering | GitHub, Slack (optional) |
| [SEO Agent](workflows/seo-agent) | Recurring SEO reporting plus a daily rank-progress loop that finds and ships content gaps | Marketing | Google Search Console, Google Analytics, Ahrefs, Call transcripts, CMS, Slack |
| [Support Pattern Detection](workflows/support-pattern-detection) | Turns recent support tickets into an evidence-linked view of recurring problems, spikes and next actions | Customer Support | Zendesk, Intercom, Slack (optional), Linear (optional) |

Browse the same catalog with download links at [adapt.com/workflows](https://adapt.com/workflows). Product documentation lives at [adapt.com/docs](https://adapt.com/docs).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). In short: one folder per workflow, a valid
`SKILL.md` with `name` and `description`, a `catalog.json`, and no company-specific or
sensitive data (secrets, internal repo names, personal handles, customer names).
