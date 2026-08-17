# URLC validation: Stage 0 and Gate 1 decision

**Assessment date:** 2026-08-17  
**Input:** [Original concept research report](../archive/original-concept-notes.md)  
**Decision discipline:** Gates are sequential. A later gate is not used to rescue an earlier one.

## Executive decision

| Stage | Result | Consequence |
|---|---|---|
| Stage 0 - evidence protocol and report audit | **Pass** | The main propositions are falsifiable, and credible evidence routes exist. |
| Gate 1 - Need | **Insufficient evidence** | Stop. Gates 2-4 are not executed and no URLC implementation is authorised. |

The available evidence establishes three facts, but not a product need:

1. Longer payloads mechanically require larger QR versions, and larger modules are generally easier to read under otherwise equal conditions.
2. Some real QR codes use redirect services, and such services add an observable and operational intermediary.
3. Some niches have long-lived or space-constrained labels.

What is absent is the evidence Gate 1 requires: the frequency with which real QR-bound URLs create a material constraint, failures or costs attributable to that density, a demonstrated inadequacy of ordinary HTTPS alternatives, and a named cohort willing to change its workflow. The current record supports technical plausibility, not a significant unmet need.

This is **not** a Gate 1 No. Candidate niches exist, so a definitive No would exceed the evidence. It is also not a Yes: the missing evidence is exactly the causal and operational evidence that the gate requires. Under the agreed rules, Insufficient does not permit progression.

## Method and evidence labels

The attached report was used only to enumerate claims. It was not treated as evidence for its own recommendation.

Evidence is labelled as:

- **Fact:** directly supported by a standard, registry, platform owner, or reproducible specification.
- **Measurement:** observed in a stated dataset or experiment; it does not automatically generalise beyond that population.
- **Assumption:** a premise selected for analysis but not yet evidenced.
- **Hypothesis:** a testable proposed causal or operational relationship.
- **Unresolved question:** information required for a gate decision but not presently available.

The companion [evidence ledger](./evidence-ledger.md) records the source, scope, confidence, limitations, and gate relevance of each decision-critical claim.

## Stage 0 - report audit

### Question

Can URLC's alleged need and benefits be expressed as falsifiable propositions, and are the report's foundational claims reliable enough to begin validation?

### Verified facts

- QR Model 2 versions run from 21 x 21 modules at Version 1 to 177 x 177 at Version 40, adding four modules per side for each version. Capacity depends on mode and ECC. [DENSO capacity table](https://www.qrcode.com/en/about/version.html)
- At ECC M, a 184-character byte-mode payload exceeds Version 9's 180-byte capacity and fits Version 10's 213-byte capacity. A 92-character byte-mode payload fits Version 6; 92 Alphanumeric characters fit Version 5. The attached report's capacity example is arithmetically correct under its stated single-mode assumptions. [DENSO Version 1-10 table](https://www.qrcode.com/en/about/versionPage/versionPage1_10.html)
- Including a four-module quiet zone on each side, Versions 10, 6, and 5 occupy 65, 49, and 45 modules across. The report's fixed-width module-size increases (32.7% and 44.4%) and fixed-module-size area reductions (43.2% and 52.1%) recalculate correctly.
- Base45 maps two bytes to three characters and is designed for QR Alphanumeric mode. Its alphabet includes space and `%`; therefore a raw Base45 stream is not automatically valid scheme-specific URI text under RFC 3986. [RFC 9285](https://www.rfc-editor.org/info/rfc9285), [RFC 3986](https://www.rfc-editor.org/info/rfc3986/)
- CRI represents URI components in CBOR, covers most HTTP URIs, and only promises conversion back to an *equivalent* URI; URI-to-CRI conversion is intentionally unspecified. This confirms substantial overlap and confirms that CRI is not an exact lexical round-trip format. [CRI draft](https://datatracker.ietf.org/doc/draft-ietf-core-href/)
- CRI is currently RFC-to-be 9988 and remains blocked in final review. It is not yet a published RFC. [RFC Editor status](https://queue.rfc-editor.org/final-review/rfc9988/)
- The current IANA URI scheme registry contains no `urlc` entry. This establishes name availability only, not novelty. [IANA URI schemes](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml)
- GS1 already defines lossless compressed Digital Link URIs for data carriers. Its compressed form remains a valid URL on the same domain, and GS1 software can extract identifiers without an online lookup. This is directly relevant prior art omitted or underweighted by the report. [GS1 Digital Link](https://ref.gs1.org/standards/digital-link/), [GS1 resolver standard](https://ref.gs1.org/standards/resolver/)
- Apple says custom schemes are an attack surface, cannot prevent multiple apps registering the same scheme, and should give way to Universal Links where possible. Android documents analogous deep-link hijacking and recommends verified App Links. [Apple custom schemes](https://developer.apple.com/documentation/Xcode/defining-a-custom-url-scheme-for-your-app), [Android deep-link security](https://developer.android.com/privacy-and-security/risks/unsafe-use-of-deeplinks)

### Correctly bounded claims

- The report correctly separates theoretical compression, binary-to-text expansion, QR mode, and final QR version.
- It correctly treats scan improvement as a hypothesis rather than an automatic consequence of compression. DENSO says larger modules are more stable and easier to read, while controlled research shows decoder performance depends on pixel-per-module scale, blur, sampling alignment, and decoder implementation. [DENSO module guidance](https://www.qrcode.com/en/howto/cell.html), [Performance of QR Code Detectors near Nyquist Limits](https://pmc.ncbi.nlm.nih.gov/articles/PMC9572759/)
- It correctly limits “offline” to recovering the URL without a URLC-specific network service. It cannot make the destination resource durable.

### Claims not established by the report

- That materially troublesome long URLs are frequent in QR deployments.
- That QR density is a significant operational problem rather than one of several print, placement, contrast, curvature, damage, lighting, and camera variables.
- That removing a redirect service is more valuable to publishers than destination mutability, analytics, abuse filtering, and universal HTTPS compatibility.
- That exact lexical reconstruction is required by any identified user workflow.
- That browser or OS vendors would implement the format.
- That a bespoke URL representation improves final QR versions often enough to justify a new decoder ecosystem.

### Stage 0 result

**Pass.** The project can be challenged using measurable propositions. The report's conclusions are not accepted, but its central hypotheses are testable.

## Gate 1 - Need

### Question

Do long QR-bound URLs or redirect dependencies create repeatable, consequential harm for an identifiable cohort after ordinary URL and QR practices are applied?

### Evidence found

#### Real-world payload length

- The 2025 peer-reviewed **QRisk** field study collected 860 physical QR codes between January 2023 and December 2024 across five countries. More than 93% contained URLs; URL lengths ranged from 12 to 203 characters, with an average of 45. The sample was heavily concentrated in France (721/860), did not publish a length distribution suitable for QR-version analysis, and did not measure scan failures or print constraints. [Paper](https://hal.science/hal-04987069v1/file/ARES_QR_codes_Archive.pdf), [publication record](https://doi.org/10.1007/978-3-032-00627-1_1)
- A 2015 study analysed 87,647,504 scans from one popular scanner application across 241 countries. About 75% of QR/barcode scans led to web URLs, and payloads of 8-128 characters were the most common density band. This is strong historical evidence that many encountered payloads were modest, but it predates native-camera scanning and current QR practices and does not expose the raw corpus or scan-failure attribution needed here. [MobiSys paper](https://homes.cs.washington.edu/~franzi/pdf/qr-mobisys2015.pdf)
- QRStuff's 2026 first-party report covers a 100,000-URL creation sample and roughly 101.9 million geolocated 2025 scans, but publishes no payload-length or QR-version distribution. Its raw URLs are not public. The data therefore demonstrates that useful operational datasets exist, not that long URLs are frequent. [QRStuff methodology](https://www.qrstuff.com/scan-report/)

**Finding:** Public evidence does not show that materially long payloads are common. The best recent field sample points in the opposite direction at the mean, but is too geographically skewed and distribution-poor to establish a general No.

#### Operational effect of density

- QR capacity and geometry establish that a longer byte-mode payload can force a higher version. That is a mechanical fact, not an observed operational cost.
- DENSO advises printing modules as large as possible and states that larger modules are more stable and easier to read. Controlled detector experiments show performance degradation near low pixel-per-module sampling and under blur. These support the direction of the hypothesis. [DENSO](https://www.qrcode.com/en/howto/cell.html), [detector study](https://pmc.ncbi.nlm.nih.gov/articles/PMC9572759/)
- Packaging studies show that module size, substrate, curvature, print process, contrast, and deformation affect readability. They do not isolate URL length as a material field problem or show how often URL shortening would change outcomes. [Traceability readability study](https://doi.org/10.1016/j.compag.2014.08.015)
- No located public dataset joins payload, version, ECC, physical dimensions, print process, scan attempts, abandonment, and downstream cost. Without that join, the project cannot attribute a failure or reprint to URL length.

**Finding:** The causal chain “long URL -> higher version -> smaller module -> operational harm” is plausible but not measured in a representative real deployment.

#### Redirect dependency and privacy

- A 2023 study collected 948 physical QR codes and examined 37 QR-generator services. In its valid unique scans, 235 (32%) used a dynamic QR/shortener, while the authors found no evidence that QR codes were a substantial or unique privacy threat relative to ordinary online link sharing. The sample was a convenience sample concentrated around Chicago and the pandemic period. [Tracking, But Make It Offline](https://conpro23.ieee-security.org/papers/siddiqi-conpro23.pdf)
- The same study found that dynamic services provide two publisher-valued capabilities that URLC intentionally loses: destination changes and scan analytics. It also found some services made dynamic links without clearly informing creators.
- RFC 9238, for long-lived manufacturer MUD labels, explicitly recognises the trade-off: shorteners reduce QR pixels but are acceptable only if their stability and privacy stance suit the device lifetime. This identifies a plausible niche, not measured harm. [RFC 9238](https://www.rfc-editor.org/info/rfc9238/)
- Google's official goo.gl sunset history demonstrates that intermediary retirement is a real architectural risk. In 2025 Google retained active links but deactivated a subset it considered inactive, after previously promising continued redirects. [Google Developers Blog](https://developers.googleblog.com/google-url-shortener-links-will-no-longer-be-available/)
- Commercial offerings make the trade-off explicit: Bitly sells redirectability, analytics, branded domains, and a 99.9% enterprise SLA. These are benefits to many publishers, not accidental overhead. [Bitly pricing and SLA](https://bitly.com/pages/pricing)
- Persistent-identifier practice challenges the idea that syntax supplies persistence. ARK states that persistence is a matter of service, while DOI couples resolution with governance and record-maintenance duties. A self-owned HTTPS domain or governed PID may remove third-party concentration without a new client codec. [ARK specification](https://arks.org/specs/), [DOI Handbook](https://www.doi.org/doi-handbook/html/)

**Finding:** Redirect dependency has real architectural and privacy costs, but public evidence does not show that the affected publishers regard those costs as greater than mutability, analytics, trust/safety functions, and universal compatibility.

#### Who might benefit

Plausible cohorts, not yet validated beneficiaries, are:

- manufacturers placing long-lived identifiers on devices, as recognised by RFC 9238;
- packaging and supply-chain operators with constrained labels, although GS1 already provides domain-specific compact representations;
- museums, archives, and government publishers seeking to minimise external dependencies;
- privacy-sensitive publishers that currently use third-party dynamic QR services unintentionally.

No located study provides, for any of these cohorts, all three of: frequency, consequential harm, and willingness to adopt a new decoding dependency.

### Counterfactuals that must be applied before URLC

Gate 1 cannot count a problem that disappears under existing operational control. Each candidate cohort must first test:

1. Remove unnecessary campaign and tracking parameters.
2. Use a short path on a publisher-controlled HTTPS domain.
3. Use a self-hosted redirect when destination mutability is required.
4. Use an established persistent identifier when governance and relocation are required.
5. Use the domain-specific compact representation where one exists, including GS1/EPC.
6. Select appropriate ECC, physical size, quiet zone, contrast, placement, and print verification.

### Gate 1 criteria applied

| Required element | Evidence status |
|---|---|
| Named real cohort | **Partial:** several plausible cohorts, none recruited or measured. |
| Frequency of materially long QR URLs | **Missing:** recent field mean is 45 characters; no usable tail/version distribution. |
| Consequential density-related harm | **Missing:** no joined payload-to-failure/cost dataset. |
| Harm remains after ordinary practices | **Missing:** no controlled counterfactual comparison. |
| Significant value from removing redirects | **Partial:** dependency and privacy properties are real; stakeholder valuation is absent. |
| Willingness to change publishing workflow | **Missing.** |
| Stakeholder-defined minimum important improvement | **Missing.** |

### Gate 1 decision

**INSUFFICIENT EVIDENCE. Do not proceed to Gate 2.**

The immediate kill criteria are not conclusively met because credible niches exist. The pass criteria are plainly not met because the project's key prevalence, causal-impact, counterfactual, and adoption evidence is absent.

## Evidence required to revisit Gate 1

The smallest adequate next research package is non-code work:

1. Recruit at least one owner in each claimed high-value cohort: long-lived devices, constrained packaging/labels, cultural/public-sector publishing, and privacy-sensitive static publishing.
2. Obtain privacy-reviewed records for a period long enough to include normal production variation. Required fields are raw or locally reduced payload length, actual QR version/mode/ECC, printed dimensions and module size, substrate/placement, scan attempts or support incidents, reprints, and associated cost.
3. Pre-register each cohort's minimally important change in its own operational units before comparing alternatives.
4. Recreate affected symbols using the six ordinary counterfactuals above; repeat field or controlled scans while holding destination, ECC, renderer, and physical envelope constant.
5. For redirect independence, document required lifetime, current domain/control model, outage or retirement exposure, analytics/mutability needs, privacy constraints, and willingness to operate a controlled domain or install a decoder.

Gate 1 may be marked Yes only if at least one cohort shows repeatable consequential harm, that harm survives these counterfactuals, and its owner is willing to change workflow. It becomes No if no cohort does so.

## Implementation decision

No URLC implementation, compression benchmark, custom alphabet, scheme registration, browser extension, decoder, or PoC is warranted. The blocker is not a technical measurement that code can resolve; it is missing real-world need evidence.

Gates 2, 3, and 4 remain deliberately unexecuted. Stage 0 prior-art and safety facts are recorded only because they audit claims in the attached report; they are not substitutes for passing Gate 1.
