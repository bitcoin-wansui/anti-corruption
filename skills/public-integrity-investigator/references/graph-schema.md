# Public integrity graph schema

## Node types
- `Person`
- `Position`
- `GovernmentAgency`
- `PartyOrganization`
- `CPPCC_NPC_Body`
- `SOE`
- `Company`
- `Project`
- `Contract`
- `Tender`
- `LandParcel`
- `InvestmentEvent`
- `MeetingEvent`
- `AuditFinding`
- `AdministrativePenalty`
- `DisciplinaryCase`
- `CourtCase`
- `Document`

## Edge types
### Career / authority
- `HELD_POSITION`
- `WORKED_AT`
- `LED`
- `OVERSAW`
- `REPORTED_TO`
- `CO_WORKED_WITH`
- `APPOINTED_TO`

### Corporate
- `SHAREHOLDER_OF`
- `CONTROLLED`
- `DIRECTOR_OF`
- `EXECUTIVE_OF`
- `HISTORICAL_OWNER_OF`
- `CO_INVESTED_WITH`

### Government transaction
- `PURCHASED_FROM`
- `WON_CONTRACT`
- `BID_FOR`
- `AWARDED`
- `DEVELOPED`
- `ACQUIRED_LAND`
- `FINANCED`
- `GUARANTEED`

### Events and evidence
- `ATTENDED_WITH`
- `MET_WITH`
- `SIGNED_WITH`
- `INSPECTED`
- `MENTIONED_IN`
- `INVOLVED_IN_CASE`
- `SUBJECT_OF_AUDIT_FINDING`

### Family/private relation
Use `RELATIVE_OF` only when explicitly established by a reliable public source and materially relevant. Never infer from surname, hometown or rumor.

## Edge fields
Each meaningful edge should include:

```json
{
  "source": "entity-id-a",
  "target": "entity-id-b",
  "relation": "CO_WORKED_WITH",
  "start": "2018-01",
  "end": "2021-05",
  "event_date": null,
  "jurisdiction": "...",
  "evidence": [
    {
      "title": "...",
      "publisher": "...",
      "url": "...",
      "publication_date": "...",
      "quote_or_fact": "...",
      "quality": "A"
    }
  ],
  "confidence": 0.86,
  "notes": "What this relation proves and what it does not prove"
}
```

## Graph expansion rules
1. Start from subject → positions → organizations.
2. Expand organizations → projects/contracts/land/SOEs.
3. Expand high-value companies → owners/controllers/directors → other companies.
4. Expand counterparties into disciplinary/judicial/audit records.
5. Use 2–3 hops by default; go deeper only when each hop has evidence and remains relevant.
6. Prune generic co-attendance with large groups unless repeated or connected to transactions.
