# URLC feasibility research

> [!IMPORTANT]
> **URLC is not currently proposed as a standard or implementation project.** This repository preserves early feasibility research. Work was suspended because available evidence did not establish a sufficiently significant unmet need.

URLC was an investigation into whether HTTP(S) URLs could benefit from a standardised, lossless, locally decodable representation, primarily when carried in QR codes, without depending on a third-party redirect service.

No URLC codec, URI scheme specification, proof of concept, browser integration, or production implementation exists in this repository. The research stopped before implementation because its first substantive gate—evidence of need—did not pass.

## Original hypothesis

The original hypothesis was that a self-contained representation might:

- reconstruct the original HTTP(S) URL locally and losslessly;
- reduce the final QR symbol size for sufficiently long URLs;
- avoid an additional online resolver operated by a link-shortening service; and
- be useful for long-lived or privacy-sensitive printed material.

These were hypotheses to test, not established benefits. In particular, theoretical compression and QR capacity calculations do not establish that publishers experience a material operational problem.

## Origin and inspiration

The URLC idea was prompted by [ha.mr](https://ha.mr), an open-source static URL compressor and QR optimiser created by [p2r3](https://github.com/p2r3/ha.mr). Its documentation and implementation demonstrate URL-aware structural encoding in a working browser application: common URL components are bit-packed, common domains and top-level domains use Huffman-coded dictionaries, remaining segments use selected character sets or Huffman coding, and QR output uses the QR Alphanumeric character set to reduce encoding overhead.

ha.mr performs compression and decompression in the browser without a backend mapping database. Its normal browser links nevertheless use the `ha.mr` origin to deliver the JavaScript decoder—through a fragment for text links or a path for QR links—although the project also includes a standalone decoder. It is therefore important practical prior art and the historical inspiration for this investigation, but it is not evidence that URL payload density creates a sufficiently significant operational problem to pass Gate 1.

## Validation framework

Research was organised as sequential kill gates:

1. **Gate 1 — Need:** Is there a real, measurable problem significant enough to justify a new solution?
2. **Gate 2 — Differentiation:** Would URLC provide a meaningful capability or advantage unavailable from existing standards and combinations?
3. **Gate 3 — Safety:** Could it be deployed without unacceptable security, privacy, interoperability, or user-safety risks?
4. **Gate 4 — Value:** Would proven benefits justify implementation, deployment, ecosystem, and possible standardisation costs?

Failure or insufficient evidence at a gate prevents progression. Later gates are not used to rescue an unsupported need.

## Current status

| Area | Status |
|---|---|
| Stage 0 — evidence protocol and report audit | **Pass** |
| Gate 1 — Need | **Insufficient evidence** |
| Gate 2 — Differentiation | **Not evaluated** |
| Gate 3 — Safety | **Not evaluated** |
| Gate 4 — Value | **Not evaluated** |
| Implementation | **None** |
| Project | **Research suspended** |

See [STATUS.md](STATUS.md) for the compact status record.

## Why work stopped

Public research established that QR codes are widely deployed, physical design constraints exist, and redirect services introduce an additional dependency. It did not establish the joined evidence needed to pass Gate 1:

`real payload → QR version and physical dimensions → observed failure or cost → causal attribution → inadequate existing counterfactual`

In particular, the research did not find representative evidence showing how often long HTTP(S) URLs materially increase QR failures, reprints, label area, accessibility problems, or operational cost. Nor did it show that ordinary measures—URL hygiene, an organisation-owned HTTPS short path, a governed redirect, or an established persistent identifier—were inadequate.

The correct decision was therefore **Insufficient evidence**, not Yes and not a definitive No. Without external field evidence from actual QR publishers, implementation would test whether a codec can be built rather than whether one should exist.

## Major findings

- QR payload length can change the QR version and physical module geometry. That is a mechanical fact, not evidence of operational need.
- No qualifying public field report was found that isolated URL payload density as the cause of QR scan failures or reprints.
- Common documented readability problems include print quality, quiet zones, contrast, distortion, placement, damage, viewing distance, and scanner behaviour.
- Third-party redirect retirement is a real lifecycle risk, but it can sometimes be mitigated by owned domains or preservation of redirect mappings.
- Redirectability, analytics, revocation, and post-print destination changes are valuable to some publishers; immutable local recovery would remove those capabilities.
- Exact lexical round-trip behaviour remained a proposed distinction, not a validated stakeholder requirement.
- Available evidence identified plausible cohorts for field research, but not a cohort with demonstrated consequential harm and willingness to change its workflow.

## Important prior art

URLC cannot be evaluated as though compact or structured URI representations were new.

- **ha.mr:** a working client-side URL compressor and QR optimiser using structural encoding, Huffman-coded dictionaries, and QR-specific output. It directly informed the URLC hypothesis. See the [live application](https://ha.mr) and [source repository](https://github.com/p2r3/ha.mr).
- **Constrained Resource Identifiers (CRI):** the IETF work represents URI components in CBOR and substantially overlaps any proposed structural binary URI representation. See the [IETF datatracker record](https://datatracker.ietf.org/doc/draft-ietf-core-href/) and [RFC Editor queue](https://queue.rfc-editor.org/).
- **GS1 Digital Link:** GS1 defines URI syntax, resolver behaviour, and lossless compression mechanisms for structured identifiers used in data carriers. See the [GS1 Digital Link standard](https://ref.gs1.org/standards/digital-link/) and [resolver standard](https://ref.gs1.org/standards/resolver/).
- Other relevant baselines include direct URLs with optimal QR segmentation, organisation-owned HTTPS short paths, persistent identifier systems, URI Templates, CBOR, standard compression formats, and QR-safe encodings.

These alternatives were identified during Stage 0. Gate 2 was deliberately not executed because Gate 1 did not pass.

## Why no proof of concept was built

The unresolved blocker was empirical need, not technical feasibility. A URL compressor or custom scheme could demonstrate that reversible encoding is possible, but it could not show that real publishers experience a material problem or that existing practices fail them.

Building a PoC at this stage would risk turning an unvalidated need into an implementation project. The historical report's earlier recommendation to build a PoC was superseded by the kill-gate validation decision and is retained in the archive to show how the research changed direction.

## Conditions for reopening Gate 1

Research should resume only if new evidence includes most of the following:

- a defined cohort of real HTTP(S)-QR publishers;
- consecutive or representative QR publishing records, including problem-free cases;
- original destinations, QR version/ECC, printed size, module size, and production context;
- observed first-attempt failures, retries, abandonment, verification failures, rework, reprints, or material label-area constraints;
- evidence attributing the outcome to payload density after controlling for ordinary production problems;
- documented lifecycle, privacy, or resolver incidents with measurable consequences;
- comparison with URL hygiene, owned HTTPS short paths, governed redirects, and applicable persistent identifiers; and
- a pre-declared operational improvement that the workflow owner considers sufficient to change practice.

Shortener use alone, theoretical QR capacity, synthetic QR tests, or enthusiasm for a new codec is not sufficient.

## Research documents

- [Publication-facing research report](docs/research-report.md)
- [Stage 0 and Gate 1 decision](docs/validation/stage-0-gate-1-decision.md)
- [Evidence ledger](docs/validation/evidence-ledger.md)
- [Gate 1 field research instrument](docs/validation/gate-1-field-research-instrument.md)
- [Evidence acquisition report](docs/validation/evidence-acquisition-report.md)
- [Original kill-oriented research plan](docs/archive/original-research-plan.md)
- [Original concept research report](docs/archive/original-concept-notes.md)

The archive documents are historical. Where an early recommendation conflicts with the Gate 1 decision, the decision record and this README are authoritative about project status.

## Contributing

Contributions should primarily add primary evidence or prior art capable of changing the Gate 1 assessment. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

Original repository research is licensed under [Creative Commons Attribution 4.0 International](LICENSE), copyright © 2026 Shteryan Nikolaev. External standards, papers, web pages, quotations, and other cited material remain under their respective copyrights and licences. If source code is added after the research is legitimately reopened, a separate permissive software licence such as MIT should be considered for that code.
