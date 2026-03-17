# PharmaStack 🏥

> Open source Claude Code agent system for pharma commercial
> analytics and business insights. Inspired by Garry Tan's
> gstack — rebuilt for pharma commercial teams.

## The Problem

Pharma commercial teams face the same analytical challenges
across every company and therapeutic area:

- **Patients go undiagnosed** — claims data alone cannot
  find them
- **HCPs are targeted generically** — not by their actual
  patient panel opportunity
- **Market access barriers kill prescriptions** — before
  they ever fill
- **Launches fail analytically** — not clinically
- **Insights live in silos** — market research, forecasting,
  field analytics, and market access never talk to each other

IQVIA charges $5M+ annually for platforms that partially
solve these problems. PharmaStack lets pharma analytics
teams build the equivalent internally in days.

## The Solution

10 specialized cognitive modes — each a different expert
brain you can summon on demand:

| Skill | Mode | What It Does |
|---|---|---|
| `/pharma-ceo` | Chief Commercial Officer | Rethink the commercial problem. Challenge whether you're solving the right question. Find the 10-star strategy. |
| `/patient-finder` | Data Scientist | Identify underdiagnosed and undertreated patients using claims, EMR, pharmacy, and longitudinal data signals |
| `/field-coach` | Sales Coach | Generate personalized HCP call briefs, next-best-action by channel, visit priority scores |
| `/market-access` | Market Access Director | Map payer barriers, PA requirements, formulary strategy, pull-through by geography |
| `/forecaster` | Commercial Forecaster | Model launch scenarios, patent cliff impact, revenue trajectory, market share projections |
| `/plan-commercial-strategy` | Brand Strategist | Build commercial strategy from scratch. Pressure-test whether you're solving the right problem. |
| `/market-researcher` | Market Research Director | Design research plans, synthesize primary and secondary insights, brand positioning analysis |
| `/competitive-intelligence` | CI Analyst | Track pipeline threats, competitor positioning, launch sequencing, market share dynamics |
| `/review-analytics` | Paranoid Analytics Director | Find flaws before insights go to leadership. Grade A-F on data quality, methodology, and business logic. |
| `/validate-model` | QA Lead | Test patient finder logic, cohort definitions, ICD-10 codes, and model assumptions before production |

---

## Example: Four Companies, Four Challenges, One System

### Example 1 — Cardiovascular Drug Launch
**The Challenge:** A cholesterol-lowering injectable with
strong clinical evidence but massive underutilization.
92% of eligible patients are not at their LDL-C goal
on statins alone. Most are never identified.

**PharmaStack `/patient-finder` output:**
- 4 patient segments defined by claims + EMR lab signals
- Specific ICD-10, RxNorm, and LOINC codes for each segment
- 630,000 estimated Northeast patient pool
- Ranked next-best-action: rep visit, PA support,
  EHR advisory, nurse navigator, patient mailer
- Conversion rates and cost-per-patient-started by action

**PharmaStack `/pharma-ceo` output:**
- Reframed the problem: not a clinical awareness failure —
  a patient identification gap at PCP level, a prior auth
  execution failure, and an IDN formulary access failure
- 90-day action plan with named health system targets
- Day 30 milestones and Day 90 KPIs with owners

---

### Example 2 — Franchise Defense & IRA Impact Research
**The Challenge:** A blockbuster oncology immunotherapy
faces patent expiry in 3 years with a biosimilar wave
coming. A subcutaneous formulation is in development
as a potential franchise extender. Simultaneously a
cardiovascular drug faces IRA Medicare price negotiation
that could reshape commercial strategy.

The brand team submitted 4 research questions. Before
designing anything, PharmaStack challenged the premise:

**`/market-researcher` first questioned:**
> *"Q2 has a hidden variable your survey will miss —
> oncology infusion centers generate revenue from IV
> chair occupancy and buy-and-bill margin. Oncologists
> will not disclose this in a standard survey. Q3 is
> a payer research question being asked to the wrong
> audience. Q4 has three distinct sub-problems requiring
> three different methodologies and respondent types."*

**Then designed a 4-study research program:**
- Study 1: SC value perception — qualitative IDIs with
  practice administrators (not just oncologists) to surface
  infusion center economic barriers standard surveys miss.
  Discrete choice experiment to force real trade-offs
  instead of rating scales
- Study 2: Patient switching behavior — parallel HCP and
  patient surveys. Patient IDIs via hub program to understand
  whether patients actually want home administration before
  designing a conversion campaign around it
- Study 3: Payer biosimilar substitution policy — payer IDIs
  only, no surveys. P&T committee members and pharmacy
  directors, not oncologists
- Study 4: IRA impact — three-audience design: cardiologists
  segmented by Medicare panel share, Medicare patients via
  advocacy partners, and MA payer medical directors

**Each study ends with decision triggers:**
> *"If >60% of community oncologists cite infusion revenue
> loss as a concern: SC launch strategy must include an
> infusion center economics solution. Price premium
> strategy is limited."*

**What the research plan explicitly does not cover:**
Biosimilar pricing strategy, DTC creative development,
IRA policy scenario planning — and explains exactly
which function owns each of those instead.

---

### Example 3 — Rare Disease Launch (IgAN / Kidney Disease)
**The Challenge:** A rare autoimmune kidney disease drug
approved on accelerated approval. ~200,000 US patients
but the majority are undiagnosed. Requires kidney biopsy
to confirm — claims data alone cannot find eligible patients.
50% of patients are already CKD Stage 3+ at diagnosis.

**Built on real experience:** The patient-finder
architecture is grounded in a production CKD
underdiagnosis model previously built using:
- Commercial insurance claims (full population)
- Medicare claims
- Specialty and retail pharmacy claims
- Longitudinal patient data (cross-payer)
- HCP and provider intelligence data
- In-network hospital EMR (lab values)
- Medicaid claims

**PharmaStack `/patient-finder` output:**
- Proxy signals for undiagnosed patients:
  hematuria + proteinuria + RAS inhibitor without
  formal diagnosis code
- EMR lab signals: UPCR ≥1.5 g/g (LOINC 2889-4),
  eGFR declining trend (LOINC 33914-3)
- AKI → CKD → rare kidney disease progression pathway
- 4 patient segments from confirmed diagnosed to
  highest-risk undiagnosed
- Nephrologist panel data approach for HCP targeting

---

### Example 4 — Three Simultaneous Launches
**The Challenge:** Three pipeline drugs launching in the
same fiscal year across different therapeutic areas —
narcolepsy, a rare blood cancer, and psoriasis. Each
has a completely different patient identification
challenge. Commercial analytics team is stretched thin.

**PharmaStack `/pharma-ceo` output:**
- Diagnosed vs. reframed the problem for each launch:
  - Narcolepsy: 10-year average diagnosis delay —
    patient identification is the primary barrier
  - Rare blood cancer: small diagnosed population —
    HCP targeting and site activation is the barrier
  - Psoriasis: crowded market — HCP switching
    behavior is the barrier, not patient finding
- Different NBA strategy for each launch
- Resource allocation recommendation across three
  simultaneous commercial priorities
- Portfolio-level KPI framework for the leadership team

---

## Built On Real Pharma Analytics Experience

- Founded an acute kidney injury (AKI) medical device
  startup — deep understanding of AKI → CKD → ESRD
  progression pathway
- Led kidney care analytics at a major US payer —
  CKD underdiagnosis NBA model, value-based care
  programs, dialysis clinical trial analytics
- Multi-source data architecture: commercial claims,
  Medicare, specialty/retail pharmacy, longitudinal
  patient data, HCP intelligence, hospital EMR, Medicaid
- Harvard Medical School-trained immunologist

---

## Quick Start

### Requirements
- Claude Code installed
- Claude Pro or Max subscription ($20-100/month)

### Install
```bash
git clone https://github.com/apple60126/pharmastack.git
cd pharmastack
claude
```

Claude Code reads the SKILL.md files automatically
on startup.

### Run Your First Query
```
Using the pharma-ceo skill:

A drug has strong clinical evidence but uptake
is lower than expected 6 months post-launch.
The brand team believes the problem is HCP
awareness. Is that the right diagnosis?
What is the actual commercial problem and
what is the 90-day action plan?
```

---

## Why One System for All Pharma

The analytical challenges are the same across every
company. Patient identification, HCP targeting,
market access, forecasting, and competitive
intelligence follow the same logic whether the
drug is for IBD, oncology, rare disease,
cardiovascular, or neuroscience.

What changes is the specific ICD-10 codes,
the payer landscape, the HCP specialty,
and the competitive context.

PharmaStack is the methodology. You bring
the company context.

---

## Inspiration

Built by a pharma commercial analytics leader
inspired by Garry Tan's gstack — the insight
that AI tools shouldn't be stuck in one generic
mode. Pharma commercial teams need explicit
cognitive gears just like software engineering teams:
founder strategy, patient analytics, field execution,
market access, competitive intelligence, and
quality review.

**gstack:** github.com/garrytan/gstack

---

## License

MIT — use freely, contribute back

---

*Not affiliated with any pharmaceutical company.
Drug and company examples are illustrative only.*
