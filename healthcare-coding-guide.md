# Healthcare Coding: A Plain-English Guide

Healthcare has its own dense vocabulary of codes, systems, and acronyms. This document explains the most common ones you'll encounter and how they relate to each other.

---

## Why Codes Exist

Every time a patient sees a doctor, gets a lab test, or stays in a hospital, that encounter needs to be described in a standardized way so that:

- **Insurance companies** know what to pay for
- **Hospitals and providers** know how to bill
- **Government agencies** can track disease trends and healthcare quality
- **Researchers** can analyze outcomes across millions of patients

Codes are that standardized language.

---

## Diagnosis Codes: What's Wrong With the Patient

### ICD-10-CM (International Classification of Diseases, 10th Revision, Clinical Modification)

The most fundamental code set in healthcare. Every diagnosis — every condition, disease, injury, or symptom — has an ICD-10 code.

- **Who maintains it:** The World Health Organization (WHO) created ICD; the US uses a clinical modification (CM) managed by CMS and CDC.
- **Format:** A letter followed by numbers and sometimes a decimal. Examples:
  - `E11.9` — Type 2 diabetes mellitus without complications
  - `J18.9` — Pneumonia, unspecified
  - `S52.501A` — Unspecified fracture of the lower end of right radius, initial encounter
- **Where you see it:** Claims, medical records, prior authorizations, quality reporting
- **ICD-10-PCS:** A separate but related code set for *inpatient procedures* (the CM version is for diagnoses). Don't confuse the two.

**Before ICD-10:** The US used ICD-9 until October 2015. ICD-11 exists internationally but the US hasn't fully adopted it yet.

---

## Procedure Codes: What Was Done to the Patient

### CPT (Current Procedural Terminology)

The dominant code set for describing medical, surgical, and diagnostic services performed by physicians and outpatient facilities.

- **Who maintains it:** The American Medical Association (AMA), which owns and licenses it.
- **Format:** 5-digit numeric codes. Examples:
  - `99213` — Office visit, established patient, moderate complexity
  - `93000` — Electrocardiogram (ECG/EKG)
  - `27447` — Total knee replacement
- **Categories:**
  - **Category I:** Standard procedures — the vast majority of codes you encounter
  - **Category II:** Performance measurement codes (supplemental, not required)
  - **Category III:** Emerging technology and research procedures
- **Where you see it:** Physician claims (professional billing), outpatient claims, ambulatory surgery centers

CPT codes are updated annually, with new codes added, revised, and deleted each January.

---

### HCPCS (Healthcare Common Procedure Coding System)

Pronounced "hick-picks." HCPCS is a two-level system that extends CPT for use in Medicare and Medicaid billing.

- **Who maintains it:** CMS (Centers for Medicare & Medicaid Services)

**Level I:** This *is* CPT. The CPT codes are incorporated into HCPCS Level I.

**Level II:** Alphanumeric codes for things CPT doesn't cover well:
- Durable medical equipment (DME) — wheelchairs, crutches, home oxygen
- Ambulance services
- Drugs and biologics administered in an outpatient or physician setting
- Dental and vision services
- Format: One letter + 4 digits. Examples:
  - `A4253` — Blood glucose test strips
  - `J0135` — Adalimumab injection (Humira)
  - `A0429` — Ambulance service, basic life support, emergency transport

**Think of it this way:** CPT = what doctors do in their office or OR. HCPCS Level II = supplies, equipment, and drugs that don't fit neatly into CPT.

---

## Facility and Inpatient Billing

### DRG (Diagnosis-Related Group)

DRGs are used to pay hospitals for *inpatient stays*, not individual services. Instead of billing line-by-line for every test and medication during a hospital stay, the entire stay gets grouped into a single DRG and the hospital receives one bundled payment.

- **Who uses it:** Medicare, Medicaid, and many commercial insurers
- **How grouping works:** A software "grouper" analyzes the patient's diagnoses (ICD-10), procedures performed (ICD-10-PCS), age, sex, and discharge status, then assigns a DRG.
- **Examples:**
  - `DRG 291` — Heart failure and shock with major complications
  - `DRG 470` — Major hip and knee joint replacement without complications
- **Payment:** Each DRG has a relative weight. Higher weight = more resources expected = higher payment. The hospital receives the same payment regardless of actual cost for that patient.
- **MS-DRG:** Medicare Severity DRG — the specific version Medicare uses. MS-DRGs often split into three tiers based on complication/comorbidity levels (with MCC, with CC, without CC/MCC).

**Why it matters:** DRGs create strong financial incentives. A hospital that manages a DRG-470 patient efficiently (shorter stay, fewer complications) keeps the difference. A hospital that exceeds the expected cost absorbs the loss.

---

### Revenue Codes

Four-digit codes on hospital (UB-04) claim forms that describe the *type of service* or cost center — like room and board, pharmacy, lab, or ICU. These appear alongside HCPCS/CPT codes on institutional claims and tell the payer *where* the service happened within the facility.

---

## Other Important Code Sets

### NDC (National Drug Code)

A unique 10- or 11-digit identifier for every drug product sold in the US.

- **Format:** Labeler - Product - Package (e.g., `0069-0105-66`)
- **Maintained by:** FDA
- **Used for:** Pharmacy claims, drug tracking, Medicaid drug rebates
- On a pharmacy claim, you'll see the NDC rather than a CPT or HCPCS code.

---

### SNOMED CT (Systematized Nomenclature of Medicine — Clinical Terms)

A comprehensive clinical terminology system with over 350,000 concepts covering diseases, findings, procedures, body structures, and more.

- **Used in:** Electronic Health Records (EHRs) for clinical documentation, not typically for billing
- **Advantage over ICD:** Much more granular and expressive — designed for clinical accuracy, not just billing categories
- Often mapped *to* ICD codes for reporting and billing purposes

---

### LOINC (Logical Observation Identifiers Names and Codes)

A universal standard for identifying lab tests and clinical observations.

- **Examples:** A "basic metabolic panel" or a "hemoglobin A1c" test each has a LOINC code
- **Used in:** Lab results in EHRs, health information exchange, interoperability
- Maintained by the Regenstrief Institute

---

### CDT (Code on Dental Procedures and Nomenclature)

The dental equivalent of CPT — procedure codes for dental services.

- **Maintained by:** American Dental Association (ADA)
- **Format:** `D` + 4 digits (e.g., `D0120` — periodic oral evaluation)

---

## A Note on "USCLC"

You may have encountered **USCLC** (or similar acronyms) in your workplace context — this likely refers to an internal system, a payer-specific code list, or a regional/organizational abbreviation. It is not a standard national code set like the ones above. If you hear it at work, it's worth asking what specific system or list it refers to in your organization's context.

---

## How These Systems Work Together

Here's a simplified example of a real patient encounter flowing through these systems:

> A Medicare patient is admitted to the hospital with chest pain. Tests reveal a heart attack. They receive a stent procedure and stay 4 days.

| Step | What Happens | Code System Used |
|------|-------------|-----------------|
| Diagnosis recorded | "ST-elevation myocardial infarction of left anterior descending artery" | ICD-10-CM: `I21.02` |
| Inpatient procedure recorded | Percutaneous transluminal coronary angioplasty with stent | ICD-10-PCS |
| Drug administered | Heparin injection during procedure | HCPCS Level II: `J1644` |
| Hospital bills Medicare | Entire stay grouped into one payment | MS-DRG: `246` (Perc cardiovascular proc w drug-eluting stent) |
| Cardiologist bills separately | Professional fee for interpreting imaging and performing procedure | CPT codes |

---

## Quick Reference Summary

| Code Set | What It Codes | Who Maintains It | Used For |
|----------|--------------|-----------------|----------|
| **ICD-10-CM** | Diagnoses and symptoms | CMS / CDC | All claims, records |
| **ICD-10-PCS** | Inpatient procedures | CMS | Hospital inpatient billing |
| **CPT** | Outpatient procedures and services | AMA | Physician and outpatient claims |
| **HCPCS Level II** | Supplies, equipment, drugs | CMS | Medicare/Medicaid claims |
| **DRG / MS-DRG** | Inpatient episode grouping | CMS | Hospital inpatient payment |
| **NDC** | Drug products | FDA | Pharmacy claims |
| **SNOMED CT** | Clinical concepts (broad) | SNOMED International | EHR documentation |
| **LOINC** | Lab tests and observations | Regenstrief Institute | Lab results, interoperability |
| **CDT** | Dental procedures | ADA | Dental claims |

---

## Key Organizations to Know

- **CMS** — Centers for Medicare & Medicaid Services. The federal agency that runs Medicare and Medicaid and maintains many of these code sets.
- **AMA** — American Medical Association. Owns and licenses CPT.
- **WHO** — World Health Organization. Maintains the base ICD system.
- **ONC** — Office of the National Coordinator for Health Information Technology. Drives EHR standards and interoperability policy.
- **NUCC / NUBC** — National Uniform Claim Committee / National Uniform Billing Committee. Set standards for professional (CMS-1500) and institutional (UB-04) claim forms.
