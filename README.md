# Public Integrity Investigator

[中文 README](./README.zh-CN.md)

A public-information OSINT workflow and ChatGPT Skill for researching public officials, public-sector projects, procurement, companies, land, state-owned platforms, disciplinary records, and evidence-backed integrity-risk signals.

The project is designed around one rule: **investigate relationships and transactions without turning suspicion into accusation.**

## What it does

Given a public official, office, jurisdiction, project, or company, the workflow can:

- resolve the subject's identity and career timeline;
- map formal authority and institutional responsibilities;
- trace public procurement, tenders, land, projects, SOEs and financing platforms;
- expand companies and counterparties into a time-aware relationship graph;
- look for repeat winners, procurement concentration, project changes, network migration and other research signals;
- search disciplinary, judicial, audit and administrative records;
- actively search for counter-evidence and normal explanations;
- produce an evidence ledger separating confirmed facts, anomaly signals and unverified hypotheses.

## Core safeguards

This repository is **not** a system for declaring people corrupt.

- A subordinate being investigated does **not** imply the leader is involved.
- Working together, appearing in the same meeting, coming from the same hometown, or dealing with the same company does **not** establish a private relationship or improper conduct.
- A company winning government contracts does **not** by itself show favoritism, collusion, bribery or benefit transfer.
- Risk signals are research priorities, not findings of misconduct.
- Material claims should be traceable to public evidence.
- Private addresses, personal phone numbers, children's schools and other unnecessary sensitive personal information should not be collected or published.
- Only an authoritative disciplinary, judicial or other competent finding should be described as an established violation.

A recurring phrase in the workflow is:

> **“公开证据目前不足以支持该推断。”**

That is a valid research result.

## Repository structure

```text
.
├── README.md
├── README.zh-CN.md
├── skill/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── data-sources.md
│       ├── graph-schema.md
│       ├── report-template.md
│       └── signal-catalog.md
└── cases/
    └── zhao-qun/
        ├── README.md
        └── report.html
```

## Skill workflow

The Skill follows this investigation sequence:

1. **Resolve identity** — establish who the subject is and the relevant dates.
2. **Build the authority map** — identify what the person could plausibly influence.
3. **Build a public relationship graph** — people, agencies, companies, projects, contracts and events.
4. **Follow money and projects** — procurement, tenders, land, SOEs and financing platforms.
5. **Run signal tests** — concentration, post-arrival acceleration, network migration, related bidders, project changes, disciplinary clusters and disclosure mismatches.
6. **Search counter-evidence** — test ordinary explanations and temporal mismatches.
7. **Report with an evidence ledger** — facts, signals, unanswered questions and source quality.

See [`skill/SKILL.md`](skill/SKILL.md) for the full instructions.

## Example case: Zhao Qun / 赵群

The first example in this repository is a public-information research report about **赵群**, the Party Secretary of Yingdong District, Fuyang, Anhui, as of the research date.

The case began after a public disciplinary announcement concerning **宫亚南**. From that news, the research deliberately made a **linear upstream extrapolation**: a subordinate was investigated, so the research explored the public institutional environment and the superior leadership chain.

This choice of subject **is not evidence that Zhao Qun did anything wrong**.

The case is included to demonstrate how the workflow should handle exactly this kind of high-risk reasoning situation:

- test the initial suspicion rather than assume it;
- reject leads when the dates do not fit;
- distinguish district-level governance risks from personal wrongdoing;
- preserve counter-evidence;
- stop short of attribution when the public evidence does not support it.

The research conclusion was not “Zhao Qun is clean” and not “Zhao Qun is corrupt.” It was narrower:

> **截至研究日期，在所覆盖的公开资料范围内，未发现足以支持赵群本人存在违法违纪或不当利益输送的可验证证据。**

This means only that the reviewed public record did not establish such a claim. It does not prove the absence of undisclosed conduct, and it should not be represented as a formal clearance, audit opinion, disciplinary conclusion, judicial finding, or investigative determination.

Open the case report at [`cases/zhao-qun/report.html`](cases/zhao-qun/report.html).

## Evidence model

The project uses four broad evidence levels:

- **A — Primary authoritative:** discipline commissions, courts, procuratorates, government, legislatures, audit bodies, registries and official procurement/transaction platforms.
- **B — Strong secondary:** established media reproducing or independently verifying primary facts.
- **C — Useful lead:** trade media, company releases, local portals and archives.
- **D — Unverified lead:** forums, social posts, anonymous claims and scraped aggregators.

Low-quality allegations should never be promoted into the main findings without stronger corroboration.

## Signal model

Signals are not guilt scores. Examples include:

- procurement concentration;
- post-arrival contract acceleration;
- network migration across a public official's postings;
- nominal competitor linkage;
- unusual project changes;
- land-project linkage;
- SOE / financing-platform concentration;
- personnel-business temporal overlap;
- disciplinary clusters;
- repeated audit findings;
- public-data or disclosure mismatches;
- repeated preferential contact followed by transactions.

Every signal should include the observed facts, why it matters, temporal fit, confidence, plausible normal explanations, and the next records that would confirm or weaken it.

## A call for better public disclosure and verification

The more this project examines public records, the clearer one limitation becomes: public oversight is often constrained not by a lack of willingness to investigate, but by the fact that information that could lawfully be disclosed is still too fragmented, incomplete, difficult to verify, or difficult for machines to process.

We therefore encourage public institutions, government agencies, state-owned enterprises and other public bodies to expand the scope and quality of lawful disclosure while continuing to protect state secrets, legitimate commercial secrets and necessary personal privacy.

In particular, more complete disclosure would be valuable for:

- government procurement, tendering and major public projects;
- project approvals, budgets, contracts, amendments, final accounts and performance results;
- land transfers, planning changes, subsidies, industrial incentives and the public portions of investment agreements;
- SOE and local financing-platform investments, guarantees, related-party transactions, asset transfers and major fund movements;
- officials' publicly disclosable career histories, responsibilities, participation in major public decisions and conflict-of-interest declarations;
- follow-up and final remediation after audit, inspection or disciplinary review findings;
- historical versions, revision logs and stable permanent links for previously disclosed records.

Most importantly, **publication should not be treated as the end of oversight**.

We also encourage discipline inspection bodies, audit institutions, legislatures, fiscal-supervision bodies and other competent oversight authorities to examine not only whether disclosure occurred, but whether the disclosed information is **true, complete, accurate and timely**.

A strong public-disclosure system should be able to answer four questions:

1. **Completeness** — Was everything legally required to be disclosed actually disclosed, or were material records selectively omitted?
2. **Authenticity** — Does the published information match original accounts, contracts, registers and real-world facts?
3. **Consistency** — Do records published by different agencies, in different years or in different reports contradict one another?
4. **Traceability** — When data, projects or funding purposes change, can the public still inspect the complete historical record?

We hope public information systems can increasingly move beyond “a PDF was once uploaded to a webpage” toward **structured, machine-readable, searchable, bulk-downloadable and version-preserving public data infrastructure**, ideally with reliable timestamps, digital signatures or other means of proving publication history.

In an Agent era, citizens may no longer need to personally read tens of thousands of budgets, procurement notices, corporate filings and audit reports. Their software may be able to do much of that work for them. As the cognitive cost of oversight falls, the more important institutional questions become:

> **Is enough information available to supervise public power? Who verifies the information that is disclosed? And when inconsistencies are discovered, is there a formal and traceable mechanism to challenge and correct them?**

Better transparency protects conscientious public officials as well as the public. The clearer the facts are, the less room there is for rumor, speculation and guilt by association.

**Transparency is not about presuming guilt. It is about making the truth easier to establish.**

## Intended use

This project is for public-interest research, journalism-style OSINT, academic exploration, public-finance analysis, compliance research and evidence organization using lawful public information.

It should not be used for harassment, doxxing, rumor laundering, political targeting, or presenting inference as proven misconduct.

## Status

Early public version. The data-source coverage and automated graph analysis can be expanded significantly.
