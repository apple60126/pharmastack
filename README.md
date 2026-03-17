# PharmaStack 🏥

> Open source Claude Code agent system for pharma
> commercial analytics. Inspired by Garry Tan's gstack —
> rebuilt for pharma commercial teams.

## The Problem

IQVIA charges pharma companies $5M+ annually for
commercial AI platforms. Pharma analytics leaders can
build the equivalent internally in days using Claude Code.

## The Solution

8 specialized cognitive modes for pharma commercial work:

| Skill | Mode | What It Does |
|---|---|---|
| `/pharma-ceo` | Chief Commercial Officer | Rethink the commercial problem. Find the 10-star launch strategy. Challenge whether you're solving the right problem. |
| `/patient-finder` | Data Scientist | Identify underdiagnosed patients using claims, EMR, pharmacy, and longitudinal data signals |
| `/field-coach` | Sales Coach | Generate personalized HCP call briefs, NBA by channel, visit priority scores |
| `/market-access` | Market Access Director | Map payer barriers, PA requirements, pull-through strategy by geography |
| `/forecaster` | Commercial Forecaster | Model launch scenarios, patent cliff impact, revenue trajectory |
| `/plan-commercial-strategy` | Brand Strategist | Build commercial strategy from scratch. Find the 10-star launch. |
| `/review-analytics` | Paranoid Analytics Director | Find flaws before insights go to leadership. Grade A-F on 4 dimensions. |
| `/validate-model` | QA Lead | Test patient finder logic, cohort definitions, ICD-10 codes before production |

## Quick Start

### Prerequisites
- Claude Code installed
- Claude Pro or Max subscription

### Install
```bash
git clone https://github.com/apple60126/pharmastack.git
cd pharmastack
claude
```

Claude Code reads the SKILL.md files automatically.

### Run Your First Query
```
Using the pharma-ceo skill:

Why is Leqvio uptake low despite strong clinical evidence
showing 92% of ASCVD patients not reaching LDL-C goals
on statins alone? What is the patient identification and
HCP targeting strategy to accelerate adoption among
cardiologists in the Northeast in the next 90 days?
```

## Example Output

The `/pharma-ceo` skill produced this when asked about
Leqvio's Northeast underperformance:

- Reframed the problem: not a clinical awareness failure —
  a patient identification gap at PCP level, prior auth
  execution failure, and IDN formulary access failure
- Identified 3 structural barriers with specific named
  health systems (Mass General Brigham, NYP, Penn Medicine)
- Generated a 90-day action plan with owners, Day 30
  milestones, and Day 90 KPIs
- Challenged its own assumptions

The `/patient-finder` skill produced:

- 4 patient segments with ICD-10, RxNorm, and LOINC codes
- 630,000 estimated Northeast patient pool
- Ranked next-best-action by channel with conversion
  rates and cost per patient
- Compliance-aware NBA distinguishing pharma constraints
  from payer direct-contact models

## Built On Real Data Experience

The patient-finder architecture is grounded in a production
model previously built for CKD underdiagnosis integrating:

- Aetna commercial claims (full population)
- Medicare claims
- CVS Specialty and Retail pharmacy claims
- Komodo Health longitudinal data
- Definitive Healthcare HCP intelligence
- In-network hospital EMR
- Medicaid claims

The same multi-source architecture applies to any
pharma patient identification challenge.

## Novartis Portfolio Context

Skills are pre-loaded with Novartis portfolio context:

**Growing:** Kisqali (+44%), Kesimpta (+27%),
Pluvicto (+70%), Scemblix (+87%), Leqvio (+70%)

**Under pressure:** Entresto (generics entered 2025),
Cosentyx (biosimilar pressure incoming)

**New launches:** Vanrafia (IgAN), Itvisma (SMA),
Remibrutinib (CINDU — FDA submission filed)

**New commercial model:** Direct-to-patient platform
launched for Cosentyx, expanding to portfolio

## Inspiration

Built by a pharma commercial analytics leader inspired
by Garry Tan's gstack — the insight that AI tools
shouldn't be stuck in one generic mode. Pharma commercial
teams need explicit cognitive gears: founder strategy,
patient analytics, field execution, market access,
and quality review.

## License

MIT
