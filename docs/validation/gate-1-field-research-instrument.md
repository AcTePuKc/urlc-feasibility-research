# Gate 1 field research instrument

This instrument is the minimum non-code work required before URLC can move beyond **Insufficient evidence**. It is designed to discover that the project has no need as readily as it is designed to find a need.

## 1. Cohort recruitment

Recruit owners of deployed QR workflows, not codec enthusiasts or general consumers. Seek evidence from these distinct hypotheses:

| Cohort | Claimed problem | Eligibility |
|---|---|---|
| Long-lived device labels | External short-link lifetime is shorter than the device or policy lifetime. | QR labels expected to remain deployed for years and containing HTTP(S) destinations. |
| Space-constrained packaging or logistics | Direct destinations force modules below a verified print/read requirement or consume valuable label area. | Production QR symbols with documented physical constraints and scan/quality evidence. |
| Cultural or public-sector publishing | Third-party redirect dependence conflicts with preservation, procurement, accessibility, or privacy policy. | Deployed public QR links and an accountable owner of the domain and printed asset. |
| Privacy-sensitive static publishing | A third-party dynamic QR was adopted only for compactness, despite no need for analytics or retargeting. | Publisher can document provider choice and has authority to change the workflow. |

Exclude payment, authentication, Wi-Fi, app-pairing, and non-HTTP QR payloads unless URLC's scope is explicitly revised and Gate 1 restarted.

## 2. Pre-registration interview

Record answers before showing any compression result:

1. What physical or operational job does the QR code perform?
2. What is the expected printed lifetime and destination lifetime?
3. Who owns the encoded domain, redirect mapping, artwork, and scanner environment?
4. What failures have occurred, how were they attributed, and what did they cost?
5. Is the destination expected to change after printing?
6. Are scan analytics required, optional, prohibited, or supplied elsewhere?
7. What privacy, accessibility, procurement, or preservation rule applies?
8. Which existing mitigations have been tried?
9. In operational units, what minimum improvement would justify changing the publishing workflow?
10. Would users be expected to install or maintain decoding software? If yes, who bears that cost?

The owner must state the minimally important change in a unit it already manages: scan success, retry/abandonment, maximum distance, label area, reprint rate, support incidents, latency, availability objective, privacy finding, or lifecycle cost. Do not translate this into a universal compression percentage.

## 3. Data schema

Collect one record per deployed symbol or production design. Sensitive URLs may be reduced locally, but the reduction must preserve the fields required to calculate QR geometry.

| Field | Required | Purpose / privacy rule |
|---|---:|---|
| Cohort and organisation pseudonym | Yes | Stratification without public identification. |
| Workflow and environment | Yes | Human phone scan, industrial reader, print/display context. |
| Original payload byte length | Yes | Required even when the raw URL cannot leave the owner. |
| Raw payload | Preferred | Store only with explicit authority; remove live secrets. |
| URL component lengths | Yes if raw omitted | Scheme, authority, path, query, fragment. |
| Token/secret flags | Yes | Signed URL, bearer token, session identifier, personal data. Never copy live secrets into the research corpus. |
| Actual QR mode segments | Yes | Detect Byte/Alphanumeric/Numeric behaviour. |
| Version and ECC | Yes | Establish capacity and redundancy. |
| Matrix and quiet zone | Yes | Verify conformance and physical envelope. |
| Printed width/height and module size | Yes | Link payload to optical geometry. |
| Substrate, curvature, contrast, finish, damage exposure | Yes | Control major confounders. |
| Printer/process and quality grade | Where available | Separate payload from production defects. |
| Scanner/device/app | Yes | Decoder/platform stratification. |
| First-attempt success, retries, time-to-success, abandonment | At least one outcome | Gate 1 requires observed harm, not anecdotes. |
| Support incident and reprint count/cost | Where claimed | Quantify consequence. |
| Redirect chain and owner | Where present | Separate self-owned and third-party dependency. |
| Required mutability and analytics | Yes | Identify cases URLC would make worse. |
| Expected service life | Yes | Compare link and physical-asset horizons. |

## 4. Existing-practice counterfactuals

For every allegedly affected symbol, generate or obtain comparable versions in this order:

1. Current production symbol.
2. Direct destination after removing unnecessary tracking parameters.
3. Short path on an owner-controlled HTTPS domain.
4. Self-hosted redirect if post-print mutability is required.
5. Applicable persistent identifier or domain-specific compact syntax.
6. Same payload with corrected QR mode selection, ECC, quiet zone, physical size, and print settings.

Hold the destination, renderer, ECC policy, physical envelope, and test conditions constant where the comparison permits. Record when a counterfactual changes a required product property rather than treating it as equivalent.

## 5. Optical observation protocol

Use the deployment's real scanner population and production print process. For each symbol variant:

- randomise presentation order and blind the operator to the variant where practical;
- test normal conditions first, then the known boundary conditions for that workflow;
- record first-attempt success, frames or time to decode, retries, maximum reliable distance, and abandonment;
- retain failures and expansions; do not report only successful symbols;
- analyse symbols clustered by organisation and design rather than treating repeated scans as independent URLs;
- report confidence intervals and the absolute operational difference, not only percentages.

The experiment is a need test, not a codec comparison. No URLC representation is included at Gate 1.

## 6. Redirect-dependency assessment

For every dynamic or shortened QR, record:

- who controls the domain and mapping;
- redirect count, service availability commitment, export/migration rights, and shutdown policy;
- whether a direct or self-owned HTTPS route is possible;
- whether retargeting, analytics, abuse blocking, geographic routing, or expiration is required;
- privacy data observed by the intermediary and the applicable policy constraint;
- the consequence and recovery path if the service or account disappears.

A theoretical extra failure point is not sufficient. Gate 1 requires a consequence the owner considers material after comparing self-owned HTTPS and governed persistent identifiers.

## 7. Gate calculation

Mark Gate 1 **Yes** only when all are true for at least one cohort:

1. The burden is observed repeatedly and expressed in a pre-registered operational unit.
2. Payload density or redirect dependency is shown to be causal or a necessary contributor.
3. The burden survives the existing-practice counterfactuals.
4. The measured effect meets the owner's pre-registered minimally important change.
5. The owner is willing to change the workflow and acknowledges the decoder/adoption trade-off.

Mark Gate 1 **No** when the recruited cohorts fail these conditions with adequate statistical precision or when the ordinary counterfactuals remove the problem. Otherwise retain **Insufficient evidence** and do not progress.

## 8. Deliverables from field work

- Privacy-reviewed data dictionary and provenance record.
- Aggregate URL-length and QR-version distributions per cohort.
- Joined geometry/outcome analysis with confounders and negative cases.
- Redirect-dependency and counterfactual comparison.
- Stakeholder minimum-important-change declarations made before results.
- A signed Gate 1 decision record stating Yes, No, or Insufficient evidence.
