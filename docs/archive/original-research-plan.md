# Original kill-oriented research and validation plan

## Archival status

This document preserves the plan that replaced the initial implementation-oriented recommendation. It is a historical research protocol, not an active roadmap. The plan stopped at Gate 1 with **Insufficient evidence**. See the [decision record](../validation/stage-0-gate-1-decision.md).

## Purpose

Research was required to proceed strictly through Gates 1–4. A gate marked No would terminate URLC; insufficient evidence would prevent progression. Later gates could not be investigated to rescue an unsupported need.

Every claim was to be recorded as a **fact**, **measurement**, **assumption**, **hypothesis**, or **unresolved question**. Gate decisions required reproducible evidence rather than narrative confidence.

## Stage 0 — Evidence protocol and report audit

**Question:** Could the project be framed as a falsifiable problem, and were the original report's premises reliable enough to justify gate research?

**Evidence required:** A claim ledger covering alleged need, novelty, QR benefit, safety, offline behaviour, persistence, and deployment feasibility, including source quality, limitations, contradictions, and affected gate.

**Research actions:**

- check primary URI, QR, platform, Unicode, and data-carrier standards;
- treat the initial report as a claim index rather than an authoritative conclusion;
- recalculate examples using QR bitstream rules;
- verify standards status and capacity claims; and
- classify conclusions as supported, contradicted, conditional, or untested.

**Pass condition:** The hypothesis could be expressed in measurable terms with accessible evidence routes.

**Immediate termination:** The objective reduced to demonstrating that URLs can be compressed, stakeholders rejected falsifiable gates, or representative evidence could not be obtained ethically.

## Gate 1 — Need

**Question:** Did long QR-bound URLs or redirect dependencies create measurable operational harm for an identifiable user group?

**Evidence required:** Real payloads, QR versions and ECC, physical dimensions, scan context, failure/retry rates, support or reprint records, production constraints, redirect incidents, privacy requirements, and attributable costs.

**Candidate cohorts:**

- long-lived device labels;
- space-constrained packaging and logistics;
- cultural and public-sector publishing; and
- privacy-sensitive static publishing.

**Research actions:**

- build a representative QR-bound URL corpus stratified by actual use case;
- calculate direct-URL QR mode, codewords, version, modules, quiet zone, and module size;
- observe first-attempt success, retries, abandonment, distance, and realistic print conditions;
- compare third-party redirects, owned redirects, persistent identifiers, branded short paths, and direct destinations; and
- ask workflow owners to define a minimally important operational change before comparing solutions.

**Pass condition:** At least one named cohort demonstrated a repeatable, consequential problem that survived ordinary URL and QR practices and was significant enough for its owner to change workflow.

**Failure condition:** Long URLs were uncommon in constrained symbols, density did not materially affect outcomes, or resolver independence offered no meaningful value compared with governed HTTPS alternatives.

**Immediate termination:** No realistic beneficiary, no measurable harm after ordinary practices, or the main beneficiaries required mutability and analytics that immutable local decoding would remove.

## Gate 2 — Differentiation

**Question:** Would URLC provide a needed capability or end-to-end QR advantage that existing standards and combinations could not provide adequately?

**Required comparisons:** Direct URL optimisation, URL hygiene, owned short paths, persistent identifiers, CRI/CBOR, applicable GS1 representations, standard compression plus QR-safe transport, and shared-context techniques where context already existed.

**Measurement rule:** Report source bytes, compressed bytes, transport characters, QR segments, data codewords, final version, physical dimensions, and scan result separately. Test lexical identity separately from semantic equivalence.

**Pass condition:** A Gate 1 requirement could not be met adequately by existing combinations and the advantage survived final-symbol and workflow comparison.

**Immediate termination:** An existing standard or simpler combination delivered the required result, gains disappeared after framing and QR encoding, or lexical preservation lacked a stakeholder requirement.

**Historical outcome:** Not executed because Gate 1 did not pass.

## Gate 3 — Safety

**Question:** Could the differentiated capability be deployed without unacceptable security, privacy, parser, interoperability, or user-safety risks?

**Required work:** Threat modelling, parser differentials, IDN and ambiguous-address cases, handler ownership, destination preview, private-network navigation, malformed-input fuzzing, decompression limits, versioning, and fail-closed behaviour.

**Pass condition:** Deterministic bounded decoding, absolute HTTP(S)-only navigation, safe unknown-version behaviour, acceptable handler provenance, and no unmitigated high-severity residual risk.

**Immediate termination:** Cross-platform origin disagreement, unbounded decompression, ambiguous downgrade behaviour, or a universal-consumer design without secure handler ownership and fallback.

**Historical outcome:** Not executed because Gate 1 did not pass.

## Gate 4 — Value

**Question:** Would proven benefits justify implementation, deployment, maintenance, education, adoption, fragmentation, and possible standardisation cost?

**Required evidence:** Total cost of ownership, stakeholder adoption evidence, independent implementation estimates, maintenance commitments, and quantified benefits from previous gates.

**Pass condition:** Positive value under conservative assumptions, beneficiaries willing to bear adoption cost, and plausible independent interoperability.

**Immediate termination:** Dependence on absent browser/OS vendor interest, costs falling mainly on users while benefits accrued to publishers, implausible independent implementations, or a business case requiring universal adoption.

**Historical outcome:** Not executed because Gate 1 did not pass.

## Implementation boundary

- Before Gate 1: no implementation.
- After Gate 1, only if Gate 2 could not be answered analytically: a codec-neutral measurement harness comparing existing representations.
- After Gate 2, only if Gate 3 required executable evidence: a sandboxed decoder test harness for the single surviving representation.
- A URLC transform would be justified only after Gate 1 demonstrated need and Gate 2 showed that existing representations could not test the required distinct capability.
- A full PoC, URI scheme registration, browser extension, mobile handler, custom dictionary codec, or standards draft remained out of scope until Gates 1–3 passed.

## Governing assumptions

- Scope was absolute HTTP(S) navigation from QR symbols.
- “Offline” meant local recovery of the destination URL, not offline access to the resource.
- All alternatives would receive equal QR optimisation and physical test conditions.
- Negative and expanding cases would remain in the dataset.
- Gate results were Yes, No, or Insufficient evidence; Insufficient did not permit progression.
- Narrowing from universal use to a controlled scanner ecosystem would create a changed product hypothesis and restart Gate 1.

