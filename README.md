# federal-intelligence

Generated intelligence deliverables from the federal contracting pipeline. Strike lists, ICF exposure analysis, capability statements, and action plans.

## Strike Lists

| File | Description | Targets |
|------|-------------|---------|
| `strike_list_80234.json` | Geo-boosted for Westminster, CO 80234 | 25 |
| `categorized_strike_list.json` | NLP-clustered by skill domain | 92 filtered |
| `opportunities_master.json` | All fillable opportunities | 309 |

## ICF Exposure

| File | Description |
|------|-------------|
| `icf_exposure.json` | ICF award history + active contracts + recompete tracker |
| `ICF_MASTER.json` | Consolidated ICF analysis + top 20 fillable |

ICF (NASDAQ: ICFI) holds $1.5B+ in federal contracts. Their recompete windows are tracked here.

## Capability Statements

### Colorado-Specific (`documents_80234/`)
Auto-generated with "Local Presence Advantage" sections:
- No travel costs
- Same time zone
- On-site within hours
- Colorado tax nexus

### Generic (`documents/`)
Standard capability statements for nationwide bids.

## Action Plan

`action_plan.json` contains week-by-week priorities:
- **Week 1:** Submit sources-sought responses (sole-source intercepts)
- **Week 2:** File size protests against ICF on DHS/DOE/Interior set-asides
- **Month 1:** Monitor recompete windows, build incumbency

## Profile Audit

`audit_profile.json` identifies gaps:
- DUNS missing → blocks SAM.gov registration
- CAGE missing → blocks DOD contracts
- No clearance → blocks 40% of DOD IT
- Only 2 past performance refs → need 3+ for full proposals

## Data Sources

- `sam_library_july2026.json` — Cached SAM.gov opportunity database (1.6MB)
- USASpending.gov API — ICF award history
- FPDS — Federal Procurement Data System

## Methodology

1. **Scoring:** 14-factor algorithm (clearance, sole-source, set-aside, IT keywords, recency, deadline, dollar value, geo)
2. **NLP:** sklearn KMeans + TF-IDF on 200 features, 10 skill-dictionary dimensions
3. **Geo:** Agency-based inference + federal installation text matching + nearby-state detection
4. **ICF:** USASpending cross-reference + 12-month recompete window calculation

## License

Data is public domain (federal records). Analysis © Effusion Labs LLC.
