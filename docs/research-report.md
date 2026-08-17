# URLC feasibility research report

## Publication note

This report is the publication-facing synthesis of an early feasibility investigation conducted in August 2026. It records both the original hypothesis and the later evidence that weakened the case for continuing.

URLC is **not** an active standards proposal, codec project, or implementation. The governing decision is [Stage 0 and Gate 1](validation/stage-0-gate-1-decision.md): Gate 1 remained **Insufficient evidence**, so Gates 2–4 were not executed and no PoC was authorised.

The [original concept report](archive/original-concept-notes.md) is preserved separately. It reached a more optimistic technical recommendation before the kill-oriented validation framework was applied. That recommendation is historical and superseded; it has not been removed because doing so would obscure how the conclusion changed.

## Research question

The investigation considered whether there was a case for a standardised, lossless, locally decodable representation of absolute HTTP(S) URLs, primarily for carriage in QR codes and without a mandatory third-party redirect lookup.

The proposed properties were:

- recovery of the original URL locally;
- a smaller final QR symbol in relevant cases;
- no mandatory shortening-service request before reaching the destination; and
- sufficient interoperability and safety to justify eventual ecosystem work.

These properties were research hypotheses. No URLC format was specified and no claim was made that decoding the URL would make the destination resource available offline or preserve it if its origin disappeared.

## Method

The initial report assessed technical plausibility, QR geometry, URI syntax, compression transports, redirect behaviour, integration risks, and prior art. A subsequent validation exercise changed the order of inquiry: before comparing representations or building anything, URLC had to demonstrate a real and consequential unmet need.

The sequential framework was:

| Stage | Question | Outcome |
|---|---|---|
| Stage 0 | Are the claims falsifiable, sourced, and testable? | **Pass** |
| Gate 1 — Need | Is there a significant measurable problem for a named cohort? | **Insufficient evidence** |
| Gate 2 — Differentiation | Do existing technologies fail to provide the required outcome? | **Not evaluated** |
| Gate 3 — Safety | Can the distinct capability be deployed acceptably? | **Not evaluated** |
| Gate 4 — Value | Do benefits justify ecosystem and standardisation cost? | **Not evaluated** |

Claims were separated into facts, measurements, assumptions, hypotheses, and unresolved questions. The evidence record is preserved in the [evidence ledger](validation/evidence-ledger.md).

## Findings

### 1. Technical plausibility did not establish need

QR payload length affects encoding capacity, version, module count, and physical geometry. At a fixed print width, fewer modules normally permit larger physical modules. Those are mechanical consequences of QR encoding rules. They do not show how frequently long URLs create a constraint in deployed symbols or whether changing version improves field outcomes enough to matter.

No URLC-specific optical measurements were performed. Public studies and implementation guidance identify multiple interacting variables, including module size, distance, angle, substrate, contrast, quiet zone, damage, printer resolution, reader software, and lighting. A calculated QR-version reduction must therefore remain separate from claims about first-attempt success, speed, abandonment, or reprint cost.

### 2. The missing evidence was operational and causal

The research did not locate a representative public dataset joining:

`destination length → QR encoding/version → physical production → field outcome → operational consequence`

Nor did it find a named primary field report that isolated URL payload density as the cause of a QR reprint or deployment failure after controlling for ordinary design and production faults.

Public sources did establish credible candidate settings: regulated product labels, retail packaging, cultural interpretation, government print, health information, and long-lived identifiers. But deployment alone does not prove a payload-length problem, and using a shortener does not prove that QR size motivated the choice.

The [evidence acquisition report](validation/evidence-acquisition-report.md) identifies organisations likely to possess the missing records and concludes that direct outreach remains necessary.

### 3. Resolver independence was a bounded benefit

A locally decoded representation could remove one intermediary lookup made by a conventional shortening service. That could reduce exposure to service retirement, mapping loss, or service-level telemetry. It would not prevent the final HTTP(S) destination from changing, disappearing, tracking visitors, or becoming unsafe.

The practical counterfactual is also not limited to a commercial third-party shortener. Publishers can use organisation-owned HTTPS paths, governed redirect tables, or established persistent identifier systems. Government guidance examined during validation often preferred an owned short domain or direct final URL for trust and continuity.

Service retirement evidence was mixed rather than uniformly favourable to the hypothesis. Firebase documented that its Dynamic Links would stop resolving, while the U.S. General Services Administration preserved the majority of Go.USA.gov mappings after retiring the service. These cases demonstrate a real lifecycle consideration and the possibility of conventional mitigation; they do not quantify harm to QR publishers. See [Firebase's deprecation FAQ](https://firebase.google.com/support/dynamic-links-faq) and the [Go.USA.gov sunset FAQ](https://www.usa.gov/blog/2022/05/sunsetting-go-usa-gov-frequently-asked-questions).

### 4. Some publishers need the properties URLC would remove

Redirects can provide post-print destination changes, analytics, revocation, locale selection, ownership transfer, and content migration. These are deliberate workflow features for many campaigns and product systems.

Immutable local recovery and redirectability are opposing product properties. A cohort that requires mutable destinations is not evidence for URLC merely because it uses long URLs or QR codes.

### 5. Important prior art materially narrowed the novelty question

The closest work includes:

- [Constrained Resource Identifiers (CRI)](https://datatracker.ietf.org/doc/draft-ietf-core-href/), which represent URI components using CBOR and overlap strongly with any proposed structural binary URI format;
- [GS1 Digital Link](https://ref.gs1.org/standards/digital-link/), which defines structured identifier URLs and compression mechanisms for data carriers;
- [GS1 resolver architecture](https://ref.gs1.org/standards/resolver/), relevant to governed redirect and discovery workflows;
- [URI Templates (RFC 6570)](https://www.rfc-editor.org/rfc/rfc6570), relevant when shared structure already exists;
- [Base45 (RFC 9285)](https://www.rfc-editor.org/rfc/rfc9285), a QR-Alphanumeric-oriented transport encoding rather than evidence for a new URL format;
- direct URLs with correct QR segmentation, standard compression, organisation-owned HTTPS short paths, and persistent identifiers.

CRI and GS1 Digital Link were absent or underweighted in the initial framing. Whether URLC could offer a meaningful capability beyond these approaches would have been a Gate 2 question. Gate 2 was not opened.

### 6. Exact lexical round trip remained an unvalidated requirement

The initial concept distinguished byte-for-byte recovery of the submitted URL spelling from recovery of a semantically equivalent or normalised URL. That distinction can matter technically—for example, percent-escape spelling or host presentation can be changed by normalisation.

The research did not identify a Gate 1 stakeholder whose workflow depended on preserving such lexical distinctions. Exact round trip therefore remained a proposed differentiator, not evidence of need.

### 7. Safety and deployment concerns were identified but not adjudicated

Early research identified destination hiding, custom-scheme interception, inconsistent URL parsing, IDN display, private-network navigation, malformed input, decompression limits, versioning, and handler availability as material concerns. Platform guidance generally gives verified HTTP(S) links stronger ownership and fallback properties than unverified custom schemes.

These observations informed the decision not to treat a custom URI scheme as an obvious deployment path. They are not a Gate 3 result because Gate 3 was never executed.

## Evidence status

### Established facts

- QR payload and mode affect final QR capacity and version.
- Redirect-based short links add a resolver mapping between the printed identifier and destination.
- Compact and structured URI prior art exists, particularly CRI and GS1 Digital Link.
- Custom scheme deployment requires client or operating-system integration and introduces interoperability concerns.
- Real publishers use QR codes in constrained, long-lived, cultural, public-sector, and privacy-sensitive settings.

### Measurements available

- Analytical QR geometry examples from the initial report.
- Published deployment and service statistics for selected QR and short-link systems.
- Laboratory and guidance data about QR print and scanner constraints.

These measurements do not form a representative Gate 1 outcome dataset.

### Hypotheses not established

- Long URLs frequently cause materially larger QR symbols in real publishing workflows.
- Payload density causes consequential field scan failures after normal production controls.
- Removing redirect dependence creates enough operational value to justify a new representation.
- Exact lexical round trip is required by an identifiable cohort.
- A compressed local representation would create a meaningful end-to-end advantage after QR framing and integration costs.

### Unresolved questions

- What proportion of real QR-bound HTTP(S) destinations cross meaningful version or label-area boundaries?
- Which cohorts experience attributable scan failures, reprints, accessibility problems, or lifecycle cost?
- Are owned HTTPS short paths and governed redirects adequate in those cohorts?
- What operational improvement would be large enough to change publisher behaviour?
- Would any distinct benefit remain after existing standards and combinations were tested fairly?

## Decision

Stage 0 passed because the idea could be expressed as falsifiable questions and a suitable evidence protocol could be defined.

Gate 1 did not pass. Candidate use cases existed, but the available evidence did not establish frequency, causal harm, inadequate counterfactuals, or a stakeholder-defined reason to change workflow. The correct status was **Insufficient evidence**.

Under the sequential rules:

- Gate 2 was not evaluated;
- Gate 3 was not evaluated;
- Gate 4 was not evaluated;
- no codec or URI scheme was specified;
- no benchmark, PoC, browser extension, or handler was built; and
- the research was suspended.

## Reopening conditions

Reopening requires external field evidence, not additional codec ideation. A defensible submission would include representative or consecutive records from actual HTTP(S)-QR publishers, physical and QR metadata, measured outcomes and costs, competing-cause controls, ordinary HTTPS counterfactuals, negative cases, and a pre-declared operational threshold.

The proposed minimum recruitment design is documented in the [field research instrument](validation/gate-1-field-research-instrument.md) and [evidence acquisition report](validation/evidence-acquisition-report.md).

Until that evidence exists, no further URLC implementation or standards work is justified.

