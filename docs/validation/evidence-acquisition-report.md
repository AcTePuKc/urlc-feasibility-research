# Gate 1 evidence acquisition report

**Project:** URLC concept validation  
**Decision scope:** Gate 1 — Need only  
**Decision at start:** **Insufficient evidence**  
**Date:** 17 August 2026  
**Authorisation boundary:** Research and recruitment planning only. Do not implement URLC, compare codecs, or begin Gate 2.

> **Archival outcome:** This report assessed whether the missing evidence could realistically be acquired. No outreach was conducted. The project was subsequently suspended pending external evidence of need.

## 1. Decision purpose

This plan tests whether the missing Gate 1 evidence identified in `stage-0-gate-1-decision.md`, `evidence-ledger.md`, and `gate-1-field-research-instrument.md` can realistically be acquired.

The acquisition problem is feasible, but public research alone is unlikely to resolve it. Public sources identify large, real QR deployments; regulated lifetimes; label-area and module-size rules; public-sector distrust of third-party redirectors; and organisations that hold the missing records. They generally do **not** publish the joined operational data Gate 1 needs:

`encoded destination → payload length → QR version/ECC → printed size/module size → scan outcome → operational consequence → counterfactual`

This plan therefore uses public evidence to select and qualify publishers, then requests narrowly defined, privacy-preserving evidence from the workflow owners. It does not ask whether anyone would adopt URLC.

## 2. Evidence language and classification

Every claim added to the Gate 1 ledger must retain the framework's claim type:

- **Fact:** a verifiable state of a standard, policy, deployment, or organisation.
- **Measurement:** a result with a defined population, method, and unit.
- **Assumption:** a working premise not yet evidenced.
- **Hypothesis:** a falsifiable proposed relationship.
- **Unresolved question:** a question for which current evidence is inadequate.

Every external source is also assigned one Gate 1 evidence class:

- **Direct evidence:** first-party documentation or data showing an actual QR deployment, operational requirement, policy, measurement, incident, or workflow. “Direct” describes proximity to the asserted fact; it does not mean the source alone proves URLC need.
- **Indirect evidence:** standards, guidance, laboratory results, or service descriptions that make a Gate 1 hypothesis plausible but do not measure the relevant publisher outcome.
- **Anecdotal:** an unverified individual account or unnamed case lacking a reproducible method.
- **Irrelevant to Gate 1:** useful for engineering, safety, or general QR knowledge but unable to establish frequency, operational harm, resolver burden, or a real beneficiary.

Theoretical capacity tables and generated QR corpora are **irrelevant to operational need** unless joined to real publishing constraints and field outcomes. The presence of a short URL is not evidence that QR size motivated shortening.

## 3. What must be acquired

Gate 1 can be decided only after acquiring evidence in five linked layers.

| Layer | Minimum evidence | Why public material is insufficient |
|---|---|---|
| Deployment denominator | Number of QR-bearing items, jobs, SKUs, labels, signs, or publications, including negative/short cases | Public case studies usually highlight selected pilots and omit the total population |
| Payload and symbol | Final encoded destination, character/byte length, ECC, version, module count, printed dimensions, quiet zone, and production method | Publishers show finished designs but rarely retain or publish structured symbol metadata |
| Outcome | First-attempt success, retries, abandonment, verification grade, help-desk incident, rejection, rework, or reprint | Public guidance states risks, not rates or causes |
| Causal/counterfactual evidence | Whether failures survive correct contrast, placement, quiet zone, print quality, URL hygiene, and an owned HTTPS short path | Most failure reports cannot isolate payload density from physical defects |
| Consequence and importance | Cost, delay, label area, reprint volume, accessibility effect, risk tolerance, and pre-declared minimally important change | Only the workflow owner can state whether the burden would change practice |

### Acquisition feasibility test

Evidence is realistically acquirable when an organisation:

1. has a demonstrable QR publishing workflow;
2. owns or can export the required payload/design/verification records;
3. has a plausible accountable team;
4. can share aggregated or redacted data without exposing personal, confidential, or security-sensitive information; and
5. can compare affected and unaffected outputs, not only recount a success story.

## 4. Candidate map by cohort

### 4.1 Long-lived device labels

| Candidate | Why it qualifies and known QR use | Documented constraint | Public evidence | Evidence requiring direct contact | Plausible workflow owner | Initial priority |
|---|---|---|---|---|---|---|
| European Commission EPREL and energy-label suppliers | QR codes are generated for regulated product labels and have appeared on covered energy labels since 2021. This is a large, repeatable device/appliance labelling population. | Labels have prescribed dimensions; suppliers and dealers must keep QR codes readable. Commission guidance identifies unreadability caused by poor adhesive application. | Scale, regulatory workflow, label dimensions, readability obligation, and a concrete non-density readability mode. | QR payload/version distribution; physical module sizes; verification failures; complaints; rejected or reprinted labels; whether URL simplification/owned redirects were considered; attributable cost. | European Commission DG ENER EPREL product/technical team; supplier regulatory-labelling engineering; retailer compliance/merchandising. | **High** |
| EU battery-passport implementation programmes and battery manufacturers | From 18 February 2027 regulated batteries must carry a QR-linked battery passport. The passport must remain available through long asset and recycling lifecycles. | Marking must be visible, legible, indelible, high contrast, and readily readable by common handheld readers; small batteries and durable marking create a credible space/lifetime constraint. | Binding requirements and persistence model. | Pre-production symbol sizes and payloads; marking trials; failures after abrasion/ageing; chosen resolver/domain architecture; smallest label/engraving envelope; whether density affects design. | European Commission DG GROW/DG ENV implementation team; Battery Pass/Global Battery Alliance technical workstream; manufacturer product compliance and traceability teams. | **High for lifecycle/constraints; Medium for observed failures** |
| FCC U.S. Cyber Trust Mark programme, Lead Administrator, and Cybersecurity Label Administrators | The consumer IoT label includes a QR code linking to a public product registry. | Registry information is intentionally dynamic, including support and authorisation status. | Official architecture and programme roles. | Production label dimensions, payload strategy, field volumes, scan/support data, and whether longevity or third-party service dependence creates operational cost. | FCC Public Safety and Homeland Security Bureau programme team; Lead Administrator/CLA registry engineering; participating manufacturers' product-compliance teams. | **Medium** |
| MUD QR implementers and NIST NCCoE participants | RFC 9238 defines a QR-based MUD URL workflow; NIST has demonstrated MUD-based IoT onboarding with industry participants. | RFC 9238 says an immutable QR should use a URL stable for the device lifetime and notes that shorter URLs yield fewer pixels. | Standards motivation and laboratory/testbed implementation. | Evidence of production deployment, device count, label envelope, scan failures, resolver incidents, and whether any manufacturer actually changed URL length because of symbol size. | RFC authors; NIST NCCoE project lead; device onboarding/product-security teams at participating vendors. | **Low unless a production deployment is identified** |

**Cohort feasibility finding:** EPREL has the best existing denominator and mature deployed base. Battery passports provide unusually clear lifecycle and physical requirements but, because field deployment begins in 2027, cannot yet supply mature failure rates. MUD is valuable only if a production publisher can be found; the standard itself is not evidence of operational need.

### 4.2 Space-constrained packaging and logistics

| Candidate | Why it qualifies and known QR use | Documented constraint | Public evidence | Evidence requiring direct contact | Plausible workflow owner | Initial priority |
|---|---|---|---|---|---|---|
| Tesco and GS1 UK retail 2D pilots | A two-year programme tested QR/GS1 2D codes at tills, in warehouses, and with phones, including inline printing and verification. | High-speed retail scanning, pack design, line-speed printing, and verification of every pack. GS1 retail guidance fixes X-dimension ranges and requires an uncompressed GS1 Digital Link URI at POS. | Named, real multi-environment pilot and operational test context. | Full payload/version/size corpus; scanner-device matrix; false no-read and retry data; line rejects/rework/reprints; affected SKUs; layout compromises; reasons for URL choices; cost. | Tesco packaging technical/engineering, retail technology, supply-chain systems, or sustainability packaging; GS1 UK 2D programme and testing leads. | **High** |
| GS1 member-organisation barcode verification services (UK, Canada, Singapore, New Zealand) | These services inspect production symbols using ISO methods and advise members before print. They may hold the closest substitute dataset to field recruitment. | Public guidance links non-scanning to redesign/reprint risk and identifies frequent physical causes such as quiet zones and print quality. | Verification method, failure categories, and consequences described by first-party organisations. | De-identified 2D-only verification records: symbology, data length/version, X-dimension, grade/failure parameter, application, and resubmission outcome. The key question is whether payload density remains predictive after physical-quality controls. | Verification laboratory manager; data/standards lead; member support director. | **High** |
| Bayer consumer-health connected-packaging team | Bayer publicly deployed GS1-powered QR codes on product packaging with medical, regulatory, brand, digital, and product stakeholders. | Regulated copy, accessibility, pack artwork, and finite packaging space. | Named deployed SKUs and workflow functions. | Label artwork envelope; encoded destinations; whether QR size displaced required copy; verification/consumer scan data; print rejects/revisions; resolver and privacy requirements; lifecycle. | Global packaging development; regulatory labelling; digital product/connected packaging; accessibility lead. | **High** |
| Deposit-return and packaging traceability pilots (Polytag, participating brands, GS1 UK) | Unique QR identifiers have been incorporated into packaging designs for deposit-return and traceability trials. | Per-item coding, inline print, high volumes, wet/curved/reflective containers, and constrained artwork. | Actual pilots and explicit packaging redesign to accommodate codes. | Payload and version distribution; print/verification reject rate; line speed; scan yield; label-area change; rework/reprint cost; dependence on dynamic resolver and analytics. | Polytag product/printing engineering and data platform; brand packaging engineering; GS1 UK circular-economy programme. | **High** |
| GS1-powered small-brand deployments | Named small brands use QR codes on soap, food, drink, and other packaging. | Small packs, limited design capacity, and outsourced print runs can magnify reprint cost. | Named QR deployments. | Denominator, URL motive, QR size, printer constraints, scan complaints, redesign/reprint history, and minimum useful improvement. | Founder/operations; packaging designer; print supplier. | **Medium** |
| MHRA and medicine-pack publishers | Current MHRA labelling guidance permits/addresses QR codes while requiring a corresponding URL; medicine packs are highly space constrained. | Mandatory labelling content, accessibility, change control, and small pack area. | Regulatory context and QR use rules. | Actual prevalence, payload and symbol characteristics, human-factors validation, readability deviations, reprints, and whether an owned short URL already resolves the issue. | MHRA labelling/patient-information policy; pharmaceutical regulatory affairs and packaging engineering. | **Medium to High** |

**Cohort feasibility finding:** This is the most likely cohort to yield joined technical and economic records. GS1 verification services, Tesco/GS1 UK, and packaging printers can distinguish density from print-quality causes. Several public examples also value mutability, analytics, or product-level identity; those cases may be negative evidence for URLC even if QR constraints are real.

### 4.3 Cultural and public-sector publishing

| Candidate | Why it qualifies and known QR use | Documented constraint | Public evidence | Evidence requiring direct contact | Plausible workflow owner | Initial priority |
|---|---|---|---|---|---|---|
| Nottinghamshire County Council Communications and Marketing | The council centrally creates QR codes for print and static displays and explicitly identifies the owning team. | Codes must be accessible, large enough for viewing distance, multi-device tested, accompanied by a short URL, and normally use the final URL rather than a third-party dynamic redirect. | Detailed first-party workflow and explicit long-term-control policy. | QR job log or sample; destination lengths/versions; print dimensions; rejected artwork, incidents, complaints, reprints; why short paths are created; duration; minimum useful change. | Communications and Marketing; Communications Business Partner; accessibility/content design. | **High** |
| UK Government Digital Service (GOV.UK Publishing) and departmental campaign teams | GOV.UK supports owned short URLs for offline campaigns and requires requesters to specify audience and duration. | Trust, link persistence, content ownership, campaign lifespan, and restrictions against opaque third-party shorteners. | First-party URL policy and short-URL request workflow. | De-identified short-URL request corpus with channel and stated rationale; subset used in QR; lifecycle incidents; maintenance cost; whether QR density was ever the deciding reason; direct-URL counterfactual. | GDS GOV.UK Publishing/product operations; departmental digital communications/campaign teams. | **High** |
| British Museum Interpretation Team | It conducts formal front-end, formative, and summative exhibition evaluations and holds an archive of reports. QR use is plausible in visitor evaluation and interpretation projects. | Small object labels, accessibility, gallery lighting, viewing distance, and exhibition lifetime. | Evaluation capability and archive; some QR-based cultural evaluation examples. | Inventory of QR-bearing exhibits/signage; destinations and printed sizes; observed scan attempts/success; visitor complaints; reprints; whether QR size affected label content or layout. | Head of Interpretation and Volunteers; visitor research and evaluation; exhibition design; digital product. | **High** |
| National Museums Scotland interpretation/digital teams | A first-party case describes QR codes integrated into exhibition labels and analytics used to understand scans and visitor flow. | Object-label space, visitor trust, exhibit duration, and accessibility. | Named museum QR deployments and availability of analytics. | Per-code artwork/payload/version; non-scan observations; label redesign/reprint; use of third-party dynamic QR service and expected persistence; denominator of visitors/exposures. | Interpretation; digital media/product; audience research; exhibition design. | **High** |
| Imperial War Museums audience research | IWM uses QR-coded exit signage for exhibition surveys and conducts summative evaluation. | Temporary exhibit signage, visitor flow, participation, and survey completion. | Current QR deployment and evaluation measurements. | QR artwork and payload; scan-to-completion funnel; observed non-scans; sign size/location; version or URL changes; reprints. | Audience research/evaluation; interpretation; digital product; visitor experience. | **Medium** |
| City of Edinburgh Museums and Galleries | Council implementation plans specify QR-linked BSL tours across multiple museum venues and name an accountable programme role. | Accessibility, multiple venues, fixed exhibit signage, modest project budgets, and content longevity. | Named deployments, dates, budgets, and role. | URL/symbol inventory; user testing with BSL audiences; placement/size limitations; failures or reprints; hosting/redirect choices. | Learning and Public Programmes Manager; Collections Information; accessibility/digital interpretation. | **Medium to High** |

**Cohort feasibility finding:** Museums and councils are recruitable because public sources name the responsible functions and several already conduct visitor evaluation. Their likely benefit variable may be accessibility, label area, or link longevity rather than throughput. Analytics alone cannot establish decode failures because exposure and failed attempts are usually unobserved.

### 4.4 Privacy-sensitive static publishing

| Candidate | Why it qualifies and known QR use | Documented constraint | Public evidence | Evidence requiring direct contact | Plausible workflow owner | Initial priority |
|---|---|---|---|---|---|---|
| GOV.UK/Government Communication Service and GDS | Official accessibility guidance rejects TinyURL, t.co, and similar services because they hide destination, may track users, and can break; it recommends owned GOV.UK short URLs. | Trust, destination transparency, longevity, accessibility, and government-domain control. | Explicit first-party policy against third-party redirectors and an existing owned-HTTPS alternative. | QR-specific demand, incidence and cost of third-party failures, owned-redirect operating burden, campaign lifetime, and whether final URLs cause materially larger symbols. | GDS domain/URL product owner; GCS accessibility; departmental campaign and security teams. | **High** |
| GovTech Singapore GoGovSG | Government operates an official shortener and QR generator specifically to offer trusted government-domain links, anti-phishing, management, and analytics at large scale. | Public trust, phishing resistance, service availability, ownership transfer, and analytics. | First-party service, public code, and large usage figures; reasons for an official rather than commercial shortener. | QR subset and payload corpus; service incidents/operating cost; print lifetimes; link-owner churn; why users shorten links; requests driven specifically by QR size; public acceptance of direct URLs. | Open Government Products GoGovSG product/engineering/research team; government communications users. | **High** |
| NHSGGC Royal Hospital for Children web and Medical Illustration teams | The documented patient-information workflow creates both QR codes and shortened URLs for printed appointment letters. | Sensitive health context, accessibility, governed content, changing resources, and printed materials. | A first-party workflow showing actual QR and short-link production. | Number and lifetime of QR publications; destination lengths and QR sizes; why the short URL is used; privacy/security policy; scan/support failures; reprint or stale-link incidents; value of mutability. | RHC website team; Medical Illustration; patient information governance; information security/data protection. | **High** |
| UKHSA Immunisation Publication Team | A government service assessment describes QR codes integrated into printed public-health resources and identifies the admin users. | Privacy, trust, accessibility, health-message change control, and potentially long print inventories. | Named service and QR-enabled print distribution. | Corpus, print volumes/lifetimes, QR/URL design rules, privacy review, scan issues, stock withdrawal or reprint, and whether redirects are permitted. | Immunisation Publication Team; UKHSA digital product; communications; privacy/security. | **Medium to High** |
| ICO consumer-IoT guidance team and IoT notice publishers | ICO guidance uses QR codes to deliver privacy information from devices or packaging to a screen. | The link itself sits at a privacy decision point; tracking and opaque redirection could conflict with user expectations. | Regulator-endorsed QR use for privacy notices and broader tracking rules. | Whether implementers use QR at scale, their URL/redirect policies, notice lifetimes, complaints, and any density/label constraint. | ICO policy team for contextual guidance; manufacturer privacy engineering/legal and packaging teams for operational data. | **Medium** |
| U.S. GSA/USAGov Go.USA.gov sunset team and former agency users | Government employees used the service for more than a decade; the service retired in 2022 and its FAQ explicitly addressed short URLs embedded in print. | Link persistence, trust, security, metric loss, migration, and printed artefacts outside central control. | Direct retirement record; mitigation preserved the majority of links rather than allowing universal breakage. | Number of QR/print links, links not preserved, user-impact incidents, reprints, migration labour/cost, and which agencies held long-lived printed stock. | GSA USAGov product/archive team; former agency web operations and public-affairs teams. | **High for resolver-dependency evidence** |

**Cohort feasibility finding:** This cohort can test whether eliminating a third party has material value, but it is also rich in existing solutions: owned HTTPS short paths, official government shorteners, and governed redirects. Evidence that these controls work adequately would support Gate 1 No for the resolver-independence hypothesis.

## 5. Results of the specific evidence searches

| Requested phenomenon | Public result | Classification and implication | Remaining acquisition route |
|---|---|---|---|
| Scan failures attributable to payload density or symbol size | No named, primary field report was located that joins a real URL payload/version to a field no-read rate and isolates density from print, contrast, damage, placement, viewing distance, or scanner support. GS1 guidance says data volume, X-dimension, printer resolution, and physical conditions interact. EPREL documents unreadability from adhesive application. | **Unresolved question.** The public evidence is indirect for density and direct for other failure causes. It cannot support a density causal claim. | Obtain de-identified verification records and controlled A/B data from GS1 labs, retail pilots, or publishers with retained artwork and incidents. |
| Reprints caused by QR readability | GS1 member organisations warn that pre-verification avoids redesign/reprint/withdrawal. Commercial and forum stories describe rework or reprints, but the named public sources do not establish a URL-density cause. | GS1 guidance: **indirect evidence** of consequence. Unnamed commercial cases and forum posts: **anecdotal** or **irrelevant** where they are not URL QRs. | Ask printers, packaging technical teams, and verification labs for job-level rejections/resubmissions and attributable costs. |
| Failures caused by retired redirect services | Firebase states that all Firebase Dynamic Links began returning 404 after 25 August 2025 and its `.page.link` domains could not be transferred. GSA retired Go.USA.gov but preserved the majority of existing links and explicitly considered print references. | Both are **direct evidence** of service lifecycle outcomes. They establish a hazard and a mitigation range, not QR prevalence or operational loss. | Recruit former Firebase publishers and GSA/agency link owners; ask for QR/print subset, migration effort, affected stock, failure reports, and reprint cost. |
| Policies against third-party redirectors | UK Government communication guidance warns that opaque third-party short links can hide destination, track users, and break. Nottinghamshire directs staff to static final URLs for long-term control. | **Direct evidence** of real policy constraints. It simultaneously points to owned HTTPS paths as a conventional alternative. | Ask policy owners how often the restriction creates a material QR problem and whether owned short paths are adequate. |
| Long-lived QR requirements | EU battery passports must persist through product and recycling lifecycles. Energy labels are regulated, mass-deployed product labels. RFC 9238 recommends device-lifetime stability for MUD URLs. | Battery law and EPREL deployment: **direct evidence**. RFC 9238: **indirect evidence** until production use is shown. | Battery pre-production trials, EPREL deployed-symbol records, and manufacturer maintenance/label data. |
| Module-size or label-area constraints | GS1 retail guidance specifies X-dimension/quiet-zone ranges and discusses print resolution and pack conditions. EPREL specifies label dimensions. Battery law requires readily readable durable marks. Council guidance ties code size to viewing distance. | **Direct evidence** of governed physical constraints; **not** direct evidence that long URLs cause operational harm. | Request actual symbols, artwork envelopes, printer resolution, scan results, and alternative layouts. |
| Publishers shortening only to reduce QR size | RFC 9238 states that shorter MUD URLs make QR codes easier to scan because they have fewer pixels. Several publisher guides pair short URLs with QR codes, but their stated motives include human readability, permanence, analytics, mutability, or trust. | RFC statement: **indirect evidence**. Shortener use without recorded motive is not evidence. No qualifying public operational case was located. | Request contemporaneous design briefs or short-link request records with reason codes; do not infer motive after the fact. |

### Search stopping rule

Further broad web searching is low yield. Continue desk research only for a named target's records, freedom-of-information publication scheme, dataset catalogue, or evaluation archive. Do not count repeated generic advice as cumulative evidence.

## 6. Public datasets and reports that can partially replace recruitment

| Dataset/report | What it can answer | What it cannot answer | Evidence class | Acquisition action |
|---|---|---|---|---|
| GS1 member-organisation 2D verification records (not presently public as row data) | Distribution of 2D grades, failure parameters, X-dimensions, symbology, resubmission, and possibly data length across real products | Field scanning, URL purpose, publisher cost, and whether a symbol contains an HTTP URL unless retained | Potential **direct measurement** if released; public service pages are **indirect** | Request a de-identified aggregate extract with a data dictionary and inclusion period; prioritise GS1 UK/Canada/Singapore |
| Tesco/GS1 UK two-year pilot records | Real inline-print, POS, warehouse, and phone performance across production packs | Unless exported, public case material does not give the joined per-symbol data or denominators | Potential **direct measurement**; current public summary is **direct deployment evidence** | Request test protocol, payloads, versions, physical dimensions, scanner matrix, failures, and rejected packs |
| EPREL public product database and generated label files | Large real corpus of final label designs and QR destinations; useful for prevalence, URL length, version, and physical-size reconstruction | Scan success, reprints, complaints, cost, or whether the QR was printed correctly | **Direct evidence** for deployed payload/design; incomplete for harm | Confirm terms and sample stratified product groups; pair with Commission/supplier incident data |
| British Museum and other museum evaluation archives | Visitor exposure, engagement, evaluation methods, and sometimes QR scan analytics | A missing scan cannot distinguish non-interest from failed detection; artwork metadata may be absent | **Direct** if reports contain a defined QR population; otherwise **indirect** | Request the QR-specific evaluation subset and matching exhibit artwork from interpretation teams |
| GoGovSG public service statistics and open-source repository | Scale of an owned government shortener, operating design, QR generation, and ownership controls | Why each link was shortened, QR proportion, printed lifetime, failure/reprint data | **Direct** for service use; **indirect** for URLC need | Ask product team for anonymised reason/channel/lifecycle distributions and QR subset |
| Go.USA.gov sunset records and archived metrics | Service scale, retirement timeline, continuity mitigation, and possibly click history | Printed/QR subset and exposure denominator; absence of clicks is ambiguous | **Direct** for resolver lifecycle | Seek aggregate internal sunset impact assessment or records from former agency users |
| QRisk research corpus | Distribution of decoded URLs, URL lengths, domains, and threats in a collected QR sample | Representative prevalence in target cohorts, print dimensions, QR version/ECC, exposure, failed scans, or operational consequence | **Indirect evidence** | Request corpus metadata and collection protocol from authors; use only to inform sampling, never as Gate 1 outcome evidence |
| Common Crawl URL index | Background distributions of public URL lengths and structures | Whether a URL is encoded in a QR code or creates an operational problem | **Irrelevant to Gate 1 outcome; indirect for corpus design only** | Use only to sanity-check URL archetypes after real QR-bound samples are acquired |
| Public QR/barcode image datasets on Zenodo/Kaggle and Barcode-30k | Detector robustness under synthetic/image perturbations | Real publisher workflow, URL-density prevalence, label cost, or field consequences | **Irrelevant to Gate 1** | Do not use for a Need decision |
| GS1 Tier 1 retail scanner test report/test suite | Scanner compatibility, conversion behaviour, and laboratory timing under a defined protocol | Actual URL-bound packaging prevalence, consumer field failures, and reprint economics | **Indirect evidence** | Use to interpret field data, not replace recruitment |
| IWM, National Museums Scotland, and other museum analytics | QR scans and downstream completion/engagement for named exhibits | Failed attempts and causal effect of payload density without observation or paired designs | **Direct measurement** for engagement; **indirect** for readability | Pair logs with artwork inventory, observation, and counterfactual symbols |

No located open dataset provides the full Gate 1 join. The most valuable substitute is not a generic QR image corpus; it is a negotiated, de-identified extract from a real verification or publishing system.

## 7. Highest-value outreach shortlist

No message is to be sent under this plan. The entries below are recruitment targets and evidence requests only.

### Target 1

**Organisation:** GS1 UK and Tesco  
**Industry/cohort:** Retail grocery; space-constrained packaging/logistics  
**Why relevant:** Two years of multi-environment 2D-code pilots create the best prospect of joined production, scanner, and packaging data.  
**Known QR use:** Till, warehouse, and consumer-phone trials; inline printing and verification.  
**Known constraint:** POS throughput, pack artwork, print resolution, high-speed lines, and multiple scanning environments.  
**Evidence already available:** Named pilot; standards-defined X-dimensions and test expectations.  
**Evidence needed:** Denominator; payload/version/ECC/size corpus; scanner matrix; no-read/retry rates; line rejects; rework/reprints; cause codes; cost; URL-choice rationale; owned-short-link counterfactual.  
**Likely contact role:** GS1 UK 2D programme/testing lead; Tesco packaging technical or retail-technology lead.  
**Gate 1 question this target could answer:** Do real URL-bearing retail codes cause a consequential density problem after correct printing and normal QR optimisation?  
**Priority:** **High**

### Target 2

**Organisation:** GS1 barcode-verification laboratories (start with UK, Canada, or Singapore)  
**Industry/cohort:** Cross-industry packaging/logistics dataset holder  
**Why relevant:** Verification data can provide many real positive and negative cases with standardised physical-quality measurements.  
**Known QR use:** ISO/IEC 15415 verification of 2D symbols submitted by members.  
**Known constraint:** Quiet zone, modulation, print resolution, symbol size, and decode/grade failures.  
**Evidence already available:** Published service and failure taxonomy; warnings about reprint/redesign consequences.  
**Evidence needed:** De-identified 2D records with symbology, URL/non-URL flag if available, data length/version, X-dimension, grade parameter, failure reason, sector, resubmission, and outcome.  
**Likely contact role:** Verification laboratory manager or GS1 standards/data lead.  
**Gate 1 question this target could answer:** How frequent are density-related verification failures compared with ordinary physical defects, and in which applications?  
**Priority:** **High**

### Target 3

**Organisation:** European Commission EPREL, plus a small sample of regulated suppliers  
**Industry/cohort:** Appliances/device labels; long-lived device labels  
**Why relevant:** Mature, mass deployment with centrally generated labels and legal readability duties offers a strong denominator.  
**Known QR use:** QR on covered EU energy labels, linking to EPREL product information.  
**Known constraint:** Prescribed label dimensions and documented unreadability from label application.  
**Evidence already available:** Regulatory scope, label generator, dimensions, deployment history, and readability guidance.  
**Evidence needed:** Product-stratified label/QR corpus, version and module size, validation method, complaints and non-read incidents, supplier reprints/rework, cost, and cause attribution.  
**Likely contact role:** DG ENER EPREL technical/product owner; supplier regulatory-labelling or packaging engineering.  
**Gate 1 question this target could answer:** In a large long-lived label population, are long destinations materially increasing QR failures or label burden?  
**Priority:** **High**

### Target 4

**Organisation:** Nottinghamshire County Council Communications and Marketing  
**Industry/cohort:** Local government; cultural/public-sector and privacy-sensitive static publishing  
**Why relevant:** The council has a central, documented QR workflow, final-URL policy, accessibility rules, and a named owner.  
**Known QR use:** Posters, leaflets, pull-up banners, and static displays.  
**Known constraint:** Viewing distance, accessibility, device compatibility, destination transparency, and long-term reliability.  
**Evidence already available:** Detailed QR policy, rejection of uncontrolled dynamic redirects, and required short textual alternative.  
**Evidence needed:** Job/sample inventory; final URL lengths and QR versions; dimensions; rejected artwork; complaints/reprints; duration; reasons short paths were or were not created; minimum meaningful improvement.  
**Likely contact role:** Communications Business Partner; accessibility/content-design lead.  
**Gate 1 question this target could answer:** Does avoiding third-party redirects leave a material direct-URL QR problem in ordinary public-sector print?  
**Priority:** **High**

### Target 5

**Organisation:** UK Government Digital Service, GOV.UK Publishing  
**Industry/cohort:** Central government; privacy-sensitive static publishing  
**Why relevant:** It operates the existing owned-short-URL counterfactual and collects audience/duration information for offline requests.  
**Known QR use:** Not established for every request; government campaign teams use QR in print, while GOV.UK owns the redirect/short-path policy.  
**Known constraint:** Trust, security, domain ownership, persistence, accessibility, and campaign lifecycle.  
**Evidence already available:** Short-URL standards, request process, and policy against opaque third-party shorteners.  
**Evidence needed:** Anonymised request reasons/channels; QR subset; destination lengths; lifespan; link changes; service burden/incidents; whether size was the deciding constraint; counterfactual without shortening.  
**Likely contact role:** GOV.UK Publishing product/operations owner; GCS accessibility or campaign standards.  
**Gate 1 question this target could answer:** Are owned HTTPS short paths an adequate, low-burden response to public-sector QR and trust needs?  
**Priority:** **High**

### Target 6

**Organisation:** National Museums Scotland  
**Industry/cohort:** Museum; cultural/public-sector publishing  
**Why relevant:** It has named exhibition-label QR deployments and scan analytics rather than merely a proposed use.  
**Known QR use:** Object demonstrations, audio interpretation, and visitor-flow analytics.  
**Known constraint:** Small labels, gallery conditions, visitor trust, accessibility, and exhibition duration.  
**Evidence already available:** First-party case narrative and existence of per-code analytics.  
**Evidence needed:** Artwork/payload/version/size inventory; exposure estimates; observed failed attempts; third-party service dependency; complaints, changes, and reprints.  
**Likely contact role:** Interpretation or digital-media lead; audience-research/evaluation; exhibition design.  
**Gate 1 question this target could answer:** Does QR density measurably reduce interaction or force unacceptable label-design tradeoffs in galleries?  
**Priority:** **High**

### Target 7

**Organisation:** NHSGGC Royal Hospital for Children  
**Industry/cohort:** Healthcare; privacy-sensitive static publishing  
**Why relevant:** A governed workflow explicitly produces both QR codes and shortened URLs in patient-facing print.  
**Known QR use:** Patient-information leaflets and printed appointment materials.  
**Known constraint:** Privacy, accessibility, governance, changing clinical content, and print lifecycle.  
**Evidence already available:** First-party standard operating procedure and named production teams.  
**Evidence needed:** Why each representation is chosen; URL/QR size corpus; print volumes/lifetimes; scan/support issues; stale links; reprints; privacy review; value of redirect mutability.  
**Likely contact role:** RHC website team; Medical Illustration; patient-information governance.  
**Gate 1 question this target could answer:** Is URL length a material driver in privacy-sensitive health print, or are human-readable aliases and content governance the real need?  
**Priority:** **High**

### Target 8

**Organisation:** U.S. General Services Administration / USAGov and selected former Go.USA.gov agency users  
**Industry/cohort:** Government publishing; resolver-dependency comparator  
**Why relevant:** It is a documented government shortener retirement that explicitly considered links in printed publications.  
**Known QR use:** Not quantified publicly; the service supported government outreach and print links.  
**Known constraint:** Persistence, public trust, migration, loss of metrics, and artefacts already in circulation.  
**Evidence already available:** Retirement timeline, usage statistics, print-specific FAQ, and preservation of most links.  
**Evidence needed:** QR/print subset; unpreserved links; impacted artefacts; complaints; reprints; migration effort/cost; how agencies mitigated the change.  
**Likely contact role:** Former Go.USA.gov product/archive owner; agency web operations or public affairs.  
**Gate 1 question this target could answer:** Does removing a redirect dependency avoid a material, otherwise unmanageable lifecycle cost?  
**Priority:** **High**

### Target 9

**Organisation:** Bayer connected-packaging programme  
**Industry/cohort:** Regulated consumer health; space-constrained packaging  
**Why relevant:** Named production SKUs and a cross-functional packaging/medical/regulatory workflow.  
**Known QR use:** GS1-powered QR on consumer-health product packs.  
**Known constraint:** Pack area, regulated information, accessibility, print quality, and content updates.  
**Evidence already available:** Public deployment case and responsible functions.  
**Evidence needed:** Actual artwork envelope, payload/version/size, verification and consumer scan data, design revisions/reprints, resolver rationale, and importance threshold.  
**Likely contact role:** Packaging development, regulatory labelling, or connected-packaging product owner.  
**Gate 1 question this target could answer:** Does a regulated production pack suffer measurable harm from URL-bearing QR density, and would immutability remove valued update capability?  
**Priority:** **High**

### Target 10

**Organisation:** GovTech Singapore / Open Government Products GoGovSG  
**Industry/cohort:** Government technology; privacy-sensitive static publishing  
**Why relevant:** It is a large, official, open-source government shortener with QR generation and anti-phishing goals.  
**Known QR use:** Service directly generates QR codes; government officers use official short links.  
**Known constraint:** Trust, service availability, analytics, ownership transfer, and government-domain control.  
**Evidence already available:** Public service rationale, usage scale, code, and operations documentation.  
**Evidence needed:** QR/print share, request motives, destination-length distribution, service cost/incidents, print lifetime, and adequacy of owned redirects.  
**Likely contact role:** GoGovSG product manager, engineering lead, or user-research lead.  
**Gate 1 question this target could answer:** Does a well-governed owned redirect service already remove the important dependency and trust burdens at acceptable cost?  
**Priority:** **Medium to High**

### Target 11

**Organisation:** EU battery-passport implementation programme / Battery Pass consortium  
**Industry/cohort:** Batteries and EVs; long-lived device labels  
**Why relevant:** The law creates an unusually long-lived QR-linked identity and availability obligation.  
**Known QR use:** Mandatory from February 2027; active implementation work is expected before that date.  
**Known constraint:** Durable physical marking, small form factors, long lifecycle, operator cessation, and recycling-stage access.  
**Evidence already available:** Binding legal requirements.  
**Evidence needed:** Pre-production test corpus, size/engraving envelopes, ageing trials, resolver architecture, failures, and cost; later, actual field data.  
**Likely contact role:** Technical standards workstream; manufacturer traceability/compliance engineering.  
**Gate 1 question this target could answer:** Is resolver-independent local recovery important enough in a multi-decade product lifecycle, and is QR density a real design constraint?  
**Priority:** **Medium now; High after deployment data exists**

### Target 12

**Organisation:** British Museum Interpretation and Visitor Research  
**Industry/cohort:** Museum; cultural/public-sector publishing  
**Why relevant:** It has a formal evaluation programme and an archive capable of supporting evidence beyond stakeholder recollection.  
**Known QR use:** QR-mediated visitor research and digital interpretation are documented in cultural-sector projects; the exact current inventory needs confirmation.  
**Known constraint:** Object-label area, accessibility, lighting, viewing distance, and exhibit lifecycle.  
**Evidence already available:** Formal evaluation methods and named archive/roles.  
**Evidence needed:** Confirmation and inventory of deployed codes; artwork/payload/size; observation and analytics; failures, complaints, redesign/reprint; duration.  
**Likely contact role:** Interpretation Team; visitor research/evaluation; exhibition design.  
**Gate 1 question this target could answer:** Can a museum's evaluation archive demonstrate an operational QR-density problem rather than low visitor interest?  
**Priority:** **Medium to High**

## 8. Recruitment and acquisition sequence

### Phase 1 — Dataset-owner feasibility (two weeks)

Prepare, but do not yet send, one-page evidence requests for:

1. GS1 verification labs;
2. Tesco/GS1 UK pilot owners;
3. EPREL technical/product owner;
4. GOV.UK Publishing/GDS;
5. one museum evaluation team; and
6. GSA Go.USA.gov archive/product owner.

Before contact, define permissible aggregation, a minimal data dictionary, retention period, redaction, and a secure transfer route. Ask first whether the fields exist, not for unrestricted raw business data.

**Phase success:** at least one technical dataset owner can supply a payload-to-quality extract, and at least one public/static publisher can supply workflow and consequence data.  
**Phase failure:** all high-priority owners confirm that payloads, symbol metadata, and outcome records were never retained and no reconstruction is possible. In that case, move to a small prospective observational study rather than inventing retrospective precision.

### Phase 2 — Purposive stakeholder recruitment (four to six weeks)

Recruit across all four cohorts using the field instrument. Within each cohort, seek:

- one workflow with a credible physical or lifecycle constraint;
- one ordinary/negative case where QR codes are used without known problems; and
- where possible, a person able to supply records rather than opinions.

Do not screen candidates in by asking whether URLs are “too long.” Ask for recent QR jobs, then reconstruct length, version, dimensions, and outcomes. This prevents problem-aware recruitment from inflating prevalence.

### Phase 3 — Evidence extraction and reconstruction

For each participant, request a privacy-reviewed sample of recent consecutive jobs rather than handpicked difficult examples. The minimum row schema is:

`cohort, job/SKU pseudonym, date, purpose, final destination, redirect owner, expected lifetime, ECC, QR version, module count, printed width/height, module size, substrate/process, viewing/scanning context, verification result, field outcome, incident/rework/reprint, cost/delay, counterfactual tried`

Sensitive destinations may be replaced by length and structural features if the original is validated locally by the participant. Preserve expanding, short, and problem-free cases.

### Phase 4 — Causal follow-up

For any claimed density incident:

1. obtain the original artwork and production specification;
2. identify competing causes (quiet zone, contrast, distortion, damage, placement, printer resolution, reader capability, unsafe scan context);
3. establish the contemporaneous fix actually attempted;
4. compare with URL hygiene and an owned HTTPS short path where operationally allowed; and
5. record whether the owner would have changed workflow for the measured improvement, without mentioning URLC.

No codec or URLC transform is required. Existing QR tools may reconstruct version/module counts from the original encoded text as allowed by the current framework.

### Phase 5 — Gate decision

Mark Gate 1:

- **Yes** only if at least one named cohort has a repeatable, consequential burden that survives normal practices and has a pre-declared operational importance threshold.
- **No** if well-sampled constrained and ordinary publishers show that long direct URLs are uncommon, density is not an outcome driver, or owned HTTPS links/normal URL governance adequately address resolver concerns.
- **Insufficient evidence** if data cannot distinguish density from other causes, samples are self-selected success/problem stories, or denominators and counterfactuals remain absent.

## 9. Minimum defensible sample

The minimum is **eight organisations/workflows**, not merely eight interviewees:

- two per cohort;
- in each cohort, one deliberately constrained workflow and one ordinary or negative comparator;
- at least four must provide consecutive job/SKU-level records, not interview testimony alone;
- at least one record-bearing participant must be a verification laboratory or high-volume packaging programme;
- at least one must be a mature long-lived device-label publisher (preferably EPREL/supplier data);
- at least one must operate an owned HTTPS short-link service or governed redirect counterfactual;
- at least one cultural/public publisher must have observation or evaluation capability; and
- at least one participant must supply a retired-service or resolver incident history.

This is a minimum for a bounded Gate 1 decision, not a prevalence estimate for all QR use. If the aim becomes population-level frequency with stated confidence intervals, a sampling frame and substantially larger stratified sample will be required. No defensible numeric sample size can be set until the variance and available denominator are known.

The eight-workflow minimum may be reduced only if a large, well-documented dataset covers several cohorts and includes the full evidence join. It must be increased if participants supply only handpicked cases, if both organisations in a cohort share the same platform/provider, or if no negative cases are retained.

## 10. Evidence gaps that require actual publishers

The following cannot be resolved by standards, capacity calculations, public case studies, or generic QR datasets:

1. the denominator of recent real QR publishing jobs in each cohort;
2. the proportion that encode materially long final HTTP(S) destinations;
3. final version, physical module size, and actual production conditions for those jobs;
4. first-attempt field failure, retry, abandonment, and support rates attributable to density;
5. rework, delay, withdrawal, reprint, lost-sale, accessibility, or compliance consequences;
6. whether the same problem survives URL hygiene, correct QR production, and an owned HTTPS short path;
7. why a shortener was chosen at the time, rather than a retrospective inference;
8. whether mutability, analytics, ownership, or trust are benefits the publisher cannot relinquish;
9. how long static artefacts actually remain in circulation and who bears link-maintenance cost; and
10. the minimally important operational change that would cause the owner to alter workflow.

## 11. Immediate termination conditions during acquisition

Terminate URLC at Gate 1, without Gate 2 work, if any of the following is established with adequate coverage:

- consecutive samples show no recurring density-related harm after ordinary QR production controls;
- the apparently affected workflows actually require mutable destinations, analytics, or revocation and regard those as more valuable than local immutable recovery;
- owned HTTPS short paths or persistent governed redirects solve the identified burden at acceptable cost;
- failures are overwhelmingly explained by print quality, placement, damage, user context, or scanner limitations rather than payload length/version;
- beneficiaries cannot state an operational consequence or minimally important change;
- reported resolver failures are mitigated through domain ownership, archival redirect tables, or existing continuity controls without material burden; or
- only hypothetical, laboratory, synthetic, or self-selected problem cases can be obtained.

Acquisition should also stop as **Insufficient evidence**, not silently become Yes, if no participant retains enough information to make a causal determination.

## 12. Answers required by this task

### A. Is direct field outreach still necessary?

**Yes.** Public sources qualify realistic cohorts and expose where records are likely to exist, but they do not provide the joined, causal, consequential evidence Gate 1 requires. Direct outreach should target data owners and workflow owners, not a general opinion survey.

### B. What is the minimum number and type of stakeholders needed?

**Eight independent organisations/workflows: two per cohort**, with at least four supplying consecutive record-level samples. The set must include a verification/high-volume packaging data owner, a mature device-label publisher, an owned-redirect operator, a cultural/public publisher with evaluation capability, and a resolver-retirement or incident owner. Each cohort needs both a constrained case and an ordinary/negative comparator. This supports a bounded kill/pass decision; it does not estimate global prevalence.

### C. Is there enough public evidence to mark Gate 1 No without outreach?

**No.** Public evidence strongly supports scepticism: known QR failures often arise from physical production; official owned short paths exist; dynamic redirection can provide valued mutability and analytics; and no qualifying public density-caused reprint case was found. But absence of published joined data is not evidence that the operational problem does not exist, especially where verification and incident records are private.

### D. Is there enough public evidence to mark Gate 1 Yes without outreach?

**No.** Public material establishes QR use, physical constraints, lifecycle requirements, and redirect hazards. It does not establish how frequently long URLs cross meaningful symbol boundaries, cause field harm, or impose consequences large enough to change a real publisher's workflow. Gate 1 therefore remains **Insufficient evidence**.

## 13. Source register

The classification applies to the specific Gate 1 claim for which each source is used.

| Source | Gate 1 use | Classification |
|---|---|---|
| [European Commission — EPREL generated labels and PDFs](https://energy-efficient-products.ec.europa.eu/suppliers/eprel-generated-labels-and-pdfs_en) | Actual regulated QR-label generation and label dimensions | **Direct evidence** |
| [European Commission — EPREL supplier information](https://energy-efficient-products.ec.europa.eu/suppliers_en) | Readability duty and adhesive-related unreadability | **Direct evidence** |
| [European Commission — five years of QR access to EPREL](https://energy-efficient-products.ec.europa.eu/news/celebrating-5-years-qr-access-eprel-2026-02-27_en) | Deployment history and scale context | **Direct evidence** |
| [EU Regulation 2023/1542 on batteries](https://eur-lex.europa.eu/eli/reg/2023/1542/oj/eng) | Mandatory QR, durability/readability, and passport lifetime | **Direct evidence** |
| [FCC Cyber Trust Mark programme order](https://docs.fcc.gov/public/attachments/DA-24-617A1_Rcd.pdf) | Actual programme architecture and dynamic registry purpose | **Direct evidence** |
| [RFC 9238 — Loading Manufacturer Usage Description URLs from QR Codes](https://www.ietf.org/rfc/rfc9238.html) | Proposed device-lifetime QR workflow and short-URL rationale | **Indirect evidence** |
| [NIST SP 1800-15 — Securing Small-Business and Home IoT Devices](https://csrc.nist.gov/pubs/sp/1800/15/final) | Laboratory/testbed MUD implementation and candidate organisations | **Indirect evidence** |
| [GS1 — 2D Barcodes at Retail Point-of-Sale Implementation Guideline](https://ref.gs1.org/guidelines/2d-in-retail/) | Production constraints, X-dimension, uncompressed POS URI requirement, test context | **Direct evidence** for workflow constraints; **indirect** for URL-caused harm |
| [GS1 — 2D barcodes in retail test suite](https://ref.gs1.org/test-suites/2d-barcodes-in-retail/) | Defined compatibility tests | **Indirect evidence** |
| [GS1 UK — QR case studies](https://www.gs1uk.org/standards-services/get-market-ready/qr-codes-powered-by-gs1/case-studies) | Named production/pilot candidates | **Direct evidence** of deployment |
| [GS1 UK — Bayer connected packaging](https://www.gs1uk.org/standards-services/get-market-ready/qr-codes-powered-by-gs1/case-studies/Bayer-connected-packaging-journey) | Named deployed consumer-health packaging workflow | **Direct evidence** |
| [GS1 Canada — Barcode Scan Verification](https://www.gs1ca.org/barcode-scan-verification/) | Verification service and asserted redesign/reprint risk | **Indirect evidence** until row data is obtained |
| [GS1 New Zealand — verification failure explained](https://support.gs1nz.org/hc/en-us/articles/206608348-Barcode-verification-failure-Explained) | Common physical failure modes | **Indirect evidence** |
| [GS1 Singapore — Barcode Verification](https://gs1.org.sg/barcode-verification/) | ISO verification and asserted non-scan consequences | **Indirect evidence** until records are obtained |
| [Nottinghamshire County Council — Using QR codes](https://www.nottinghamshire.gov.uk/global-content/how-to-create-accessible-content/qr-codes) | Actual publishing policy, owner, physical/accessibility constraints, redirect policy | **Direct evidence** |
| [GOV.UK Publishing — Follow URL standards](https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/plan-manage-content/follow-url-standards/) | Owned URL and redirect governance | **Direct evidence** |
| [GOV.UK — How to request a short URL](https://insidegovuk.blog.gov.uk/2014/04/07/how-to-request-a-short-url/) | Offline short-path workflow, audience and duration fields | **Direct evidence** |
| [Government Communication Service — accessibility standards](https://www.communications.gov.uk/guidance/accessible-communications/accessibility-standards/) | Policy against opaque/tracking/brittle third-party shorteners | **Direct evidence** |
| [British Museum — Visitor research and evaluation](https://www.britishmuseum.org/research/projects/visitor-research-and-evaluation) | Evaluation archive and accountable team | **Direct evidence** of evaluation capability; QR inventory unresolved |
| [Imperial War Museum Annual Report 2023–24](https://assets.publishing.service.gov.uk/media/66e98e2210f8726dc23aa2c5/Imperial_War_Museum_Annual_Report_and_Accounts_2023_to_2024.pdf) | QR-coded exhibition-exit surveys and measured evaluation | **Direct evidence** |
| [National Museums Scotland — QR codes in museums](https://blog.nms.ac.uk/2022/07/19/qr-codes-in-museums-worth-the-effort/) | Named exhibit-label uses and scan analytics | **Direct evidence** |
| [City of Edinburgh BSL implementation plan](https://consultationhub.edinburgh.gov.uk/cg/bslimplementationplan/user_uploads/bsl-plan_implementation-2024-2030_engagement-autumn-2024.pdf) | Named museum QR projects, budget, dates, and role | **Direct evidence** |
| [NHSGGC RHC patient-information SOP](https://www.clinicalguidelines.scot.nhs.uk/ggc-paediatric-guidelines/ggc-paediatric-guidelines/author-guidance/patient-information-for-the-rhc-website-sop/) | Governed health-print workflow creating QR and short URLs | **Direct evidence** |
| [UKHSA Health Publications alpha assessment](https://digitalhealth.blog.gov.uk/2026/02/16/ukhsa-health-publications-alpha-assessment/) | QR-enabled public-health print service and owner | **Direct evidence** |
| [ICO — consumer IoT privacy information](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/online-tracking/guidance-for-consumer-internet-of-things-products-and-services/how-should-we-tell-people-what-we-re-doing/) | QR as a privacy-notice delivery mechanism | **Direct evidence** of regulator guidance; **indirect** for deployment |
| [Firebase — Dynamic Links deprecation FAQ](https://firebase.google.com/support/dynamic-links-faq) | Shutdown date, 404 outcome, and non-transferable service domains | **Direct evidence** |
| [USAGov — Go.USA.gov sunset FAQ](https://www.usa.gov/blog/2022/05/sunsetting-go-usa-gov-frequently-asked-questions) | Retirement, print-link question, mitigation, trust/security guidance | **Direct evidence** |
| [USAGov — final Go.USA.gov statistics](https://www.usa.gov/blog/2022/11/sunsetting-go-usa-gov-final-user-statistics) | Service scale and retirement record | **Direct evidence** |
| [GovTech Singapore — GoGovSG](https://www.tech.gov.sg/products-and-services/for-government-agencies/productivity-and-marketing/gogovsg/) | Official trusted shortener, QR generation, scale, and rationale | **Direct evidence** |
| [GoGovSG source repository](https://github.com/opengovsg/GoGovSG) | Ownership/operations and QR capability | **Direct evidence** for service design; **indirect** for need |
| [Common Crawl overview](https://commoncrawl.org/overview) | Background URL corpus only | **Irrelevant to Gate 1 outcome** |
| [QRisk research paper](https://hal.science/hal-04987069v1/file/ARES_QR_codes_Archive.pdf) | Collected QR URL-length/security distribution | **Indirect evidence** |
| [Zenodo colour QR image dataset](https://zenodo.org/records/15718521) | Printed/captured QR images for colour research | **Irrelevant to Gate 1** |
| [Kaggle benign/malicious QR dataset](https://www.kaggle.com/datasets/samahsadiq/benign-and-malicious-qr-codes) | Synthetic images generated from URL lists | **Irrelevant to Gate 1** |
| Anonymous commercial rework/reprint case studies | Illustrate possible operational costs without verifiable URL/payload causation | **Anecdotal** |
| Forum and social-media reports of unreadable QR print runs | Lead generation only | **Anecdotal** |

## 14. Current Gate status

**Gate 1 — Need: Insufficient evidence.**

The missing evidence is realistically acquirable through a bounded outreach effort, especially from GS1 verification/pilot owners, EPREL publishers, governed public-sector QR teams, museum evaluation teams, and redirect-service operators. No implementation work is authorised or needed to conduct this acquisition.
