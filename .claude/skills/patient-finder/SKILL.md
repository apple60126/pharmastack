## PATIENT FINDER SKILL
## Underdiagnosed & Undertreated Patient Identification

---
## FRAMEWORK PHILOSOPHY

Patient identification requires layering multiple data types
because no single source tells the complete story:

- CLAIMS data tells you what was DIAGNOSED and PRESCRIBED
- LAB data tells you the actual BIOLOGY
- PHARMACY data tells you what was DISPENSED and ADHERED TO
- LONGITUDINAL data tells you the PATIENT JOURNEY over time
- HCP data tells you WHERE to intervene and WITH WHOM
- GOVERNMENT data tells you the UNDERSERVED populations missed
  by commercial-only analysis

The most powerful models combine all six data types.
The specific vendor for each type is secondary to having
coverage of all six.

---
## DATA TYPES REQUIRED — WITH VENDOR EXAMPLES

### 1. MEDICAL CLAIMS (Diagnosis + Procedure + Utilization)
What it tells you: confirmed diagnoses, specialist visits,
procedures, prior auth patterns, care utilization

Vendor examples (use what is available):
- IQVIA APLD (Anonymous Patient-Level Data)
- Symphony Health
- Optum Clinformatics
- IBM MarketScan
- Komodo Health
- HealthVerity
- Aetna full commercial claims (payer-direct)
- Truven Health Analytics

For Leqvio specifically:
- ASCVD diagnosis codes: I25.x, I63.x, I70.x
- HeFH: E78.01
- Cardiology visit frequency and recency
- Prior auth denial rates by payer and geography

### 2. PHARMACY CLAIMS (Rx Dispensing + Adherence)
What it tells you: what was actually dispensed, dose
history, refill patterns, therapy gaps, statin adherence

Vendor examples:
- IQVIA NPA (National Prescription Audit)
- IQVIA APLD pharmacy component
- Symphony Rx
- CVS Specialty and Retail (payer-direct)
- Surescripts
- Komodo pharmacy claims
- SSA/CMS Part D data

For Leqvio specifically:
- High-intensity statin Rx 90+ days:
  Atorvastatin 40mg (RxNorm 617311), 80mg (617312)
  Rosuvastatin 20mg (301542), 40mg (301543)
- Statin discontinuation or dose reduction pattern
- Absence of PCSK9 inhibitor:
  Evolocumab (RxNorm 1860484)
  Alirocumab (RxNorm 1743281)
  Inclisiran (RxNorm 2371130)

### 3. LAB / EMR DATA (Actual Biology)
What it tells you: real clinical values that claims cannot
capture — the critical differentiator vs. claims-only models

Vendor examples:
- Participating hospital EMR (Epic, Cerner, Meditech)
- HealthVerity Real World Data
- Veeva Nitro
- Flatiron Health (oncology-focused)
- Tempus
- Komodo EMR component
- Quest Diagnostics / LabCorp data feeds

Key insight: Claims tell you what was diagnosed.
EMR lab values tell you the actual biology. A claims-only
model cannot confirm statin inadequacy — only a lab value can.

For Leqvio specifically:
- LDL-C value (LOINC 2089-1) above 70 mg/dL = statin inadequate
- LDL-C above 55 mg/dL in very high risk (post-CABG Z95.1,
  post-PCI Z95.5) = even tighter goal missed
- eGFR (LOINC 33914-3) below 60 = CKD comorbidity,
  tightens LDL goal further

Translation from prior CKD model experience:
CKD used eGFR below 60 as the biological signal that
claims missed. Leqvio uses LDL-C above 70 the same way —
the lab value proves the patient needs the therapy even
when the claims record shows a statin on board.

### 4. LONGITUDINAL PATIENT DATA (Journey Over Time)
What it tells you: how patients move through the
healthcare system across payers, time, and care settings

Vendor examples:
- Komodo Health (cross-payer longitudinal)
- HealthVerity Privacy-Protected Longitudinal (PPL)
- IQVIA OneKey + APLD linked
- Optum longitudinal EHR
- IBM Watson Health

For Leqvio specifically:
- Time from statin initiation → first LDL lab →
  missed therapy escalation = the action gap
- Cross-payer matching catches patients who switch
  insurance and appear as new patients in single-payer views
- Patient journey from PCP → cardiologist referral →
  Rx written → PA outcome → fill or abandon

### 5. HCP + PROVIDER INTELLIGENCE (Where to Intervene)
What it tells you: which HCPs have the most untreated
eligible patients, their prescribing behavior, IDN
affiliation, and referral patterns

Vendor examples:
- Definitive Healthcare
- IQVIA OneKey
- Veeva Network
- SK&A
- Doceree
- Monocl

For Leqvio specifically:
- Cardiologist and PCP panel size for ASCVD patients
- Statin-inadequate patient volume per HCP NPI
- IDN affiliation — formulary committee influence
- Prescribing behavior: writes statins but never PCSK9
- Office staff PA completion rate by practice

### 6. GOVERNMENT + PUBLIC PAYER DATA
What it tells you: Medicare, Medicaid, and dual-eligible
populations often missed in commercial-only analysis

Vendor examples:
- CMS Medicare 5% Limited Data Set (LDS)
- CMS 100% Medicare (with DUA)
- Medicaid MAX/TAF data
- CMS Part D Prescriber Data (public)
- State Medicaid claims (state-specific DUA)

For Leqvio specifically:
- Medicare Part B (buy-and-bill) vs Part D (pharmacy) —
  different reimbursement pathway, different rep message
- Dual eligible ASCVD patients: highest CV risk,
  lowest treatment rates, largest untapped segment
- CMS Part D prescriber data: publicly available,
  shows which PCPs prescribe PCSK9 inhibitors at all

---
## PATIENT SEGMENTS — LEQVIO ELIGIBILITY FRAMEWORK

CORE ELIGIBILITY FILTER (all four gates required):
1. ASCVD confirmed OR HeFH diagnosis
2. High-intensity statin on board 90+ days
3. LDL-C above goal (70 mg/dL standard; 55 mg/dL very high risk)
4. No PCSK9 inhibitor or inclisiran on record

SEGMENT A — Confirmed ASCVD + Active Statin + LDL≥70 + Recent Visit
Risk Score: 9-10/10 — Fastest 90-day win

SEGMENT B — ASCVD + Statin + No Recent LDL Lab in 12 Months
Risk Score: 7-8/10 — Largest hidden cohort, documentation gap

SEGMENT C — HeFH (E78.01) + Any Statin + Age Under 65
Risk Score: 8-9/10 — Falls through cardiology/PCP gap

SEGMENT D — Statin Intolerance (M79.3) + ASCVD + No PCSK9
Risk Score: 7-8/10 — Highest conversion, RNAi mechanism is the answer

---
## NEXT BEST ACTION ENGINE — PHARMA-SPECIFIC

COMPLIANCE CONSTRAINT: Pharma cannot directly identify
or contact individual patients by name. All patient-facing
actions route through HCP, opt-in hub programs, or DTC.

NBA BY CHANNEL — RANKED BY ROI:

1. HCP CHANNEL (highest ROI — always first)
- Rep visit with anonymized panel data: "Dr. X, you have
  ~34 patients meeting Leqvio criteria with no PCSK9 on record"
- MSL scientific exchange — especially for statin intolerant
  segment where RNAi mechanism is the clinical answer
- EHR best practice advisory — fires when HCP opens
  qualifying patient chart in Epic or Cerner
- Peer-to-peer KOL program — local cardiologist shares
  real-world Leqvio experience with target HCPs
- Co-pay card and patient support materials in HCP office

2. HUB / PATIENT SERVICES (after HCP engagement)
- HCP-initiated referral to patient support program (opt-in)
- Hub nurse navigator call — injection training, adherence, refills
- Pre-filled PA template sent to HCP office before Rx written
- PA support line — hub staff calls payer on behalf of HCP
- Co-pay assistance card to reduce patient out of pocket

3. PAYER / MARKET ACCESS (enables all other channels)
- PA pre-screening by geography — pre-load templates where
  burden is highest
- IDN P&T committee formulary submission — one approval
  removes friction for all affiliated HCPs
- Outcomes-based contract — rebate tied to LDL-C goal attainment
- Step therapy waiver for statin-intolerant patients

4. DTC / DISEASE AWARENESS (volume play, lower ROI per patient)
- Know your LDL number campaign — drives patients to request labs
- Home cholesterol screening kit — generates lab data that
  triggers prescribing conversation
- Digital retargeting to patients searching cholesterol/heart terms
- TV/digital DTC driving ask-your-doctor behavior

5. SYSTEM / EHR (highest leverage, slowest to implement)
- Epic best practice advisory integration
- CVS Caremark pharmacy flag for pharmacist counseling
- IDN preferred formulary for seamless HCP access

NBA DECISION LOGIC BY SEGMENT:
- Segment A → HCP rep visit first, hub PA support second
- Segment B → EHR advisory or disease awareness first
  to generate the missing lab value
- Segment C → HCP internist/lipidologist + FH community enrollment
- Segment D → MSL RNAi exchange + hub nurse navigator
  after HCP writes Rx

---
## WHAT PHARMA LEARNS FROM PAYER NBA MODELS

Payer advantage: direct patient access as care manager,
can mail/call/visit patients by name.

Pharma counter-strategy:
1. Better HCP panel data than the payer has —
   show HCPs their own untreated patient volume
2. Hub services that remove the PA burden the payer creates
3. EHR integration that puts the clinical trigger at point of care
4. Disease awareness that creates patient pull-through demand

The winning NBA combines all four simultaneously —
the same integrated logic used in payer care management
models, adapted for pharma compliance constraints.
