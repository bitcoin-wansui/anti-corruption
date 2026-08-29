# Public Integrity Investigator

[中文 README](./README.zh-CN.md)

A public-information OSINT workflow and reusable Agent Skill for researching public officials, public-sector projects, procurement, companies, land, state-owned platforms, disciplinary records, and evidence-backed integrity-risk signals.

The project is built around one rule: **investigate relationships and transactions without turning suspicion into accusation.**

## Install

### 1. Install with `npx skills`

Install the Skill from this repository:

```bash
npx skills add bitcoin-wansui/anti-corruption --skill public-integrity-investigator
```

Install it globally / at user level:

```bash
npx skills add bitcoin-wansui/anti-corruption --skill public-integrity-investigator -g
```

You can also install directly from the Skill directory URL:

```bash
npx skills add https://github.com/bitcoin-wansui/anti-corruption/tree/main/skills/public-integrity-investigator
```

If your CLI supports one-shot use without installation:

```bash
npx skills use bitcoin-wansui/anti-corruption@public-integrity-investigator
```

> Use the space-separated form `--skill public-integrity-investigator` rather than `--skill=public-integrity-investigator` for maximum compatibility.

### 2. Give the GitHub link to an Agent

For Agents that can read GitHub and persist files, you can simply send:

```text
Install this skill for yourself:
https://github.com/bitcoin-wansui/anti-corruption/tree/main/skills/public-integrity-investigator

Read SKILL.md and all referenced files. If your environment supports persistent
skills, install it into your persistent/user-level skills directory. Otherwise,
load and follow it for this session.
```

Important: **reading a Skill is not necessarily the same as persistently installing it.** The Agent needs filesystem/configuration support for persistent installation.

### 3. Download a Skill ZIP

A packaged copy is available at:

[`dist/public-integrity-investigator.skill.zip`](./dist/public-integrity-investigator.skill.zip)

Use this with products that support importing a Skill ZIP, including ChatGPT Skills where available.

## How to use it

After installation, ask the Agent naturally. Examples:

```text
Investigate the mayor of [city]. Build a career timeline, authority map,
public relationship graph, project/company network, and an evidence ledger.
Separate confirmed facts, anomaly signals, and unverified hypotheses.
```

```text
A public official was just announced as under disciplinary investigation.
Trace their past 10 years of positions, major projects, procurement,
SOE/financing-platform links, counterparties, and relevant superiors.
Actively search for counter-evidence and temporal mismatches.
```

The Skill should trigger on public-integrity research, official career mapping, government procurement/project tracing, public company/ownership relationships, audit/disciplinary records, and evidence-backed integrity-risk analysis.

## What it does

The workflow can:

- resolve identity and career timelines;
- map formal authority and institutional responsibilities;
- trace procurement, tenders, land, public projects, SOEs and financing platforms;
- expand counterparties into a time-aware relationship graph;
- detect repeat winners, procurement concentration, project changes and network migration;
- search disciplinary, judicial, audit and administrative records;
- actively search for normal explanations and counter-evidence;
- produce an auditable evidence ledger.

## Core safeguards

This repository is **not** a system for declaring people corrupt.

- A subordinate being investigated does **not** imply the leader is involved.
- Working together, appearing in the same meeting, sharing a hometown, or dealing with the same company does **not** establish a private relationship.
- A company winning government contracts does **not** by itself show favoritism, collusion, bribery, or benefit transfer.
- Risk signals are research priorities, not findings of misconduct.
- Material claims should be traceable to public evidence.
- Do not collect or publish private addresses, phone numbers, children's schools, private accounts, or unnecessary sensitive personal data.
- Only authoritative disciplinary, judicial, audit, or other competent findings should be described as established violations.

A valid result is often:

> **公开证据目前不足以支持该推断。**

## Evidence and signal model

Evidence quality:

- **A — Primary authoritative:** discipline commissions, courts, procuratorates, governments, legislatures, audit bodies, registries, procurement and transaction platforms.
- **B — Strong secondary:** established media reproducing or independently verifying primary facts.
- **C — Useful lead:** company releases, trade media, local portals and archives.
- **D — Unverified lead:** forums, social posts, anonymous claims and scraped aggregators.

The Skill includes signal tests for procurement concentration, post-arrival contract acceleration, network migration, nominal competitor linkage, project changes, land/project linkage, SOE concentration, personnel-business overlap, disciplinary clusters, repeated audit findings, public-data mismatches, and repeated preferential contact followed by transactions.

**Signals are not guilt scores.**

## Example case: Zhao Qun / 赵群

The first case study is in [`cases/zhao-qun/`](./cases/zhao-qun/).

The research began after the August 2026 public announcement that 宫亚南 was under disciplinary and supervisory investigation. From that news, the workflow deliberately made a **linear upstream extrapolation** and selected 赵群, Party Secretary of Yingdong District, as a research subject.

That selection mechanism is **not evidence that Zhao Qun did anything wrong**.

The narrower conclusion was:

> **截至研究日期，在所覆盖的公开资料范围内，未发现足以支持赵群本人存在违法违纪或不当利益输送的可验证证据。**

“Not found” is not the same as “proved absent.” The case is included precisely to show that an integrity-research workflow must be able to reject attractive but unsupported hypotheses rather than manufacture an accusation.

- [Case notes](./cases/zhao-qun/README.md)
- [Full HTML report](./cases/zhao-qun/report.html)

## A call for better public disclosure and verification

Public oversight is often limited not by a lack of willingness to investigate, but by the fact that information that could lawfully be disclosed remains fragmented, incomplete, difficult to verify, or difficult for machines to process.

We encourage governments, public institutions, SOEs and other public bodies—while protecting state secrets, legitimate commercial secrets and necessary personal privacy—to publish more complete, structured and machine-readable information about public procurement, tenders, major projects, budgets, contracts, amendments, final accounts, land transactions, subsidies, investment agreements, SOE investments, guarantees, asset transfers, audit remediation, and other lawfully disclosable public-power records.

Publication should not be the end of oversight. We also encourage discipline inspection, audit, legislative, fiscal-supervision and other competent authorities to verify not only **whether disclosure exists**, but whether it is:

1. **Complete** — required material has not been selectively omitted.
2. **Authentic** — published data matches original accounts, contracts and registers.
3. **Consistent** — different agencies and reporting periods do not silently contradict one another.
4. **Traceable** — revisions, project changes and funding changes preserve a public history.

We hope public-information systems can move beyond “a PDF was once uploaded to a webpage” toward **structured, searchable, bulk-downloadable, machine-readable and version-preserving public data infrastructure**, ideally with reliable timestamps or signatures.

Better transparency protects conscientious public officials as well as the public. **Transparency is not about presuming guilt. It is about making the truth easier to establish.**

## Acknowledgements

Special thanks to the [LINUX DO](https://linux.do/) community.

It is full of people willing to share tools, experience, strange ideas and surprisingly useful discussions. More importantly: **the people there are genuinely fun.** 😄

This project grew out of exactly that kind of open, curious environment where ideas can be thrown onto the table, challenged, improved and turned into something practical.

## Repository structure

```text
anti-corruption/
├── README.md
├── README.zh-CN.md
├── dist/
│   └── public-integrity-investigator.skill.zip
├── skills/
│   └── public-integrity-investigator/
│       ├── SKILL.md
│       ├── agents/
│       │   └── openai.yaml
│       ├── assets/
│       │   └── icon.svg
│       └── references/
│           ├── data-sources.md
│           ├── graph-schema.md
│           ├── signal-catalog.md
│           └── report-template.md
└── cases/
    └── zhao-qun/
        ├── README.md
        └── report.html
```

## Intended use

For public-interest research, journalism-style OSINT, academic exploration, public-finance analysis, compliance research and evidence organization using lawful public information.

Do not use it for harassment, doxxing, rumor laundering, political targeting, or presenting inference as proven misconduct.
