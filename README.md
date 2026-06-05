# Awesome AI Governance

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)

A curated list of resources for building, shipping, and auditing AI systems in regulated environments. Curated by [Aperintel](https://github.com/aperintel) and the community.

The focus is on AI governance practice: what regulated firms, healthcare operators, public-sector teams, and engineering teams need to evidence that the AI they ship is accountable, auditable, and defensible. Lighter-weight ethics commentary and academic-philosophy reading lists already exist elsewhere; this list is the practitioner's bookmark folder.

## Contents

- [Regulations and frameworks](#regulations-and-frameworks)
- [Standards bodies and working groups](#standards-bodies-and-working-groups)
- [Research papers](#research-papers)
- [Open-source primitives](#open-source-primitives)
- [Commercial governance platforms](#commercial-governance-platforms)
- [AI security and red-team tools](#ai-security-and-red-team-tools)
- [Observability and audit tools](#observability-and-audit-tools)
- [Regulators and policy-making bodies](#regulators-and-policy-making-bodies)
- [Industry conferences](#industry-conferences)
- [Newsletters and blogs](#newsletters-and-blogs)
- [Books](#books)

---

## Regulations and frameworks

- [EU AI Act](https://eur-lex.europa.eu/eli/reg/2024/1689/oj) - The foundational EU regulation. Enforcement of high-risk obligations begins 2 August 2026.
- [EU AI Act Explorer](https://artificialintelligenceact.eu/) - Searchable explorer for the Act's articles, definitions, and timelines.
- [NIST AI Risk Management Framework (AI RMF 1.0)](https://www.nist.gov/itl/ai-risk-management-framework) - US-anchored voluntary framework; widely adopted as a procurement filter.
- [ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html) - AI management system standard. Certification programmes are now live.
- [ISO/IEC 23894:2023](https://www.iso.org/standard/77304.html) - AI risk management guidance, companion to 42001.
- [UK ICO Guidance on AI and Data Protection](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/) - The UK regulator's positioning on automated decisions and AI under UK GDPR.
- [FCA Consumer Duty](https://www.fca.org.uk/firms/consumer-duty) - UK financial-services regulator's framework, increasingly applied to AI-mediated outcomes.
- [NHS DSPT](https://www.dsptoolkit.nhs.uk/) - NHS Data Security and Protection Toolkit. The compliance gate for healthtech ingesting NHS data.

## Standards bodies and working groups

- [IETF SCITT WG](https://datatracker.ietf.org/wg/scitt/about/) - Supply Chain Integrity, Transparency and Trust. The relevant working group for cryptographic audit chains for software supply chains and increasingly for AI provenance.
- [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) - Adjacent standard for cryptographically signed attestations.
- [ETSI TC ESI](https://www.etsi.org/committee/esi) - European Telecommunications Standards Institute, Electronic Signatures and Infrastructure. Where the RFC 3161 trusted timestamping conversation lives.
- [OASIS](https://www.oasis-open.org/) - Standards body where several AI-trust-related profiles are being drafted.

## Research papers

- [Concrete Problems in AI Safety (Amodei et al., 2016)](https://arxiv.org/abs/1606.06565) - The canonical pre-LLM safety paper. Still foundational vocabulary for the field.
- [Constitutional AI (Bai et al., 2022)](https://arxiv.org/abs/2212.08073) - Anthropic's paper on guiding model behaviour via a written constitution.
- [Sleeper Agents (Hubinger et al., 2024)](https://arxiv.org/abs/2401.05566) - On models that behave differently in training versus deployment.

## Open-source primitives

- [Nexuscone](https://github.com/aperintel/nexuscone) - Tamper-evident audit ledger with SHA-256 hash chain, optional Ed25519 signing, optional Bitcoin anchoring via OpenTimestamps. Apache 2.0.
- [OpenTimestamps](https://opentimestamps.org/) - Free Bitcoin-anchored timestamping. The substrate for Nexuscone's external anchor.
- [Sigstore](https://www.sigstore.dev/) - Free signing infrastructure for software supply chains. Increasingly used in AI model attestation.
- [in-toto](https://in-toto.io/) - Framework for protecting software supply chain integrity. Adjacent to AI provenance work.

## Commercial governance platforms

- [Credo AI](https://www.credo.ai/) - Enterprise AI governance platform. Mature regulator-facing posture.
- [Holistic AI](https://www.holisticai.com/) - EU AI Act focused governance platform.
- [Fiddler AI](https://www.fiddler.ai/) - AI observability and audit platform.
- [Trustible](https://trustible.ai/) - AI governance and risk management.
- [Modulos](https://www.modulos.ai/) - One of the first platforms with ISO 42001 product conformity.
- [Saidot](https://www.saidot.com/) - EU AI Act focused governance platform, Helsinki-based.

## AI security and red-team tools

- [PyRIT](https://github.com/Azure/PyRIT) - Microsoft's Python Risk Identification Tool for generative AI red teaming.
- [Garak](https://github.com/leondz/garak) - LLM vulnerability scanner.
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) - NVIDIA's open-source toolkit for guardrails on LLM apps.

## Observability and audit tools

- [Langfuse](https://langfuse.com/) - Open-source LLM observability.
- [Helicone](https://helicone.ai/) - LLM observability platform.
- [PostHog LLM Observability](https://posthog.com/docs/ai-engineering/observability) - LLM observability inside the broader PostHog product analytics platform.
- [Tuning Engines](https://www.tuningengines.com/) - AI control and evidence plane for governed model, MCP, skill, and agent traffic. Gives regulated teams policy decisions, approvals, guardrail outcomes, trace links, state references, costs, and outcomes for audit review.

## Regulators and policy-making bodies

- [UK Information Commissioner's Office (ICO)](https://ico.org.uk/) - UK data protection regulator. The primary regulator most AI products in the UK encounter.
- [European Commission AI Office](https://digital-strategy.ec.europa.eu/en/policies/ai-office) - The EU AI Office, responsible for implementing the AI Act at EU level.
- [US AI Safety Institute](https://www.nist.gov/aisi) - The US AI Safety Institute, established within NIST.
- [UK AI Safety Institute](https://www.aisi.gov.uk/) - The UK AI Safety Institute.

## Industry conferences

- [Money 20/20](https://www.money2020.com/) - Algorithmic decisioning and AI in financial services.
- [FAccT](https://facctconference.org/) - ACM Fairness, Accountability, and Transparency Conference.
- [AIES](https://www.aies-conference.com/) - AAAI/ACM AI Ethics and Society.
- [Compliance Week Europe](https://www.complianceweek.com/) - Compliance officer audience.

## Newsletters and blogs

- [Stratechery on AI Policy](https://stratechery.com/) - Ben Thompson's analysis where it touches AI regulation.
- [Import AI](https://importai.substack.com/) - Jack Clark's policy-and-research weekly.

## Books

- [The Alignment Problem (Brian Christian, 2020)](https://brianchristian.org/the-alignment-problem/) - Accessible introduction to the alignment problem.
- [Algorithms of Oppression (Safiya Umoja Noble, 2018)](https://safiyaunoble.com/research-writing/) - Foundational text on algorithmic bias.

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the criteria a new entry must meet (it must materially help a practitioner ship or audit AI in a regulated environment; pure ethics commentary or generic AI-news links go elsewhere).

## Licence

This list is published under [CC0 1.0 Universal](LICENSE). The linked resources retain their own licences.
