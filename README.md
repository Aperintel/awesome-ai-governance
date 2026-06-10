# Awesome AI Governance

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)

A curated list of resources for building, shipping, and auditing AI systems in regulated environments. Curated by [Aperintel](https://github.com/aperintel) and the community.

The focus is on AI governance practice: what regulated firms, healthcare operators, public-sector teams, and engineering teams need to evidence that the AI they ship is accountable, auditable, and defensible. Lighter-weight ethics commentary and academic-philosophy reading lists already exist elsewhere; this list is the practitioner's bookmark folder.

**EU AI Act enforcement note:** High-risk AI system obligations under EU AI Act Annex III apply from 2 August 2026. Several sections below map directly to those obligations.

## Contents

- [Regulations and frameworks](#regulations-and-frameworks)
- [Standards bodies and working groups](#standards-bodies-and-working-groups)
- [Research papers](#research-papers)
- [Open-source primitives](#open-source-primitives)
- [Commercial governance platforms](#commercial-governance-platforms)
- [AI security and red-team tools](#ai-security-and-red-team-tools)
- [Observability and audit tools](#observability-and-audit-tools)
- [Agentic AI governance](#agentic-ai-governance)
- [Bias, fairness and impact assessment](#bias-fairness-and-impact-assessment)
- [Regulators and policy-making bodies](#regulators-and-policy-making-bodies)
- [Industry conferences](#industry-conferences)
- [Newsletters and blogs](#newsletters-and-blogs)
- [Books](#books)

---

## Regulations and frameworks

- [EU AI Act](https://eur-lex.europa.eu/eli/reg/2024/1689/oj) - The foundational EU regulation. Enforcement of high-risk obligations begins 2 August 2026.
- [EU AI Act Explorer](https://artificialintelligenceact.eu/) - Searchable explorer for the Act's articles, definitions, and timelines.
- [NIST AI Risk Management Framework (AI RMF 1.0)](https://www.nist.gov/itl/ai-risk-management-framework) - US-anchored voluntary framework; widely adopted as a procurement filter.
- [NIST AI 600-1: Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf) - NIST's specific guidance on managing risks from generative and foundation models, including agentic systems. Maps to the AI RMF.
- [ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html) - AI management system standard. Certification programmes are now live.
- [ISO/IEC 23894:2023](https://www.iso.org/standard/77304.html) - AI risk management guidance, companion to 42001.
- [UK ICO Guidance on AI and Data Protection](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/) - The UK regulator's positioning on automated decisions and AI under UK GDPR.
- [FCA Consumer Duty](https://www.fca.org.uk/firms/consumer-duty) - UK financial-services regulator's framework, increasingly applied to AI-mediated outcomes.
- [NHS DSPT](https://www.dsptoolkit.nhs.uk/) - NHS Data Security and Protection Toolkit. The compliance gate for healthtech ingesting NHS data.
- [Singapore Model AI Governance Framework](https://www.pdpc.gov.sg/help-and-resources/2020/01/model-artificial-intelligence-governance-framework) - Widely referenced voluntary framework from Singapore's PDPC. Practical and well-structured for deployers.
- [Canada Artificial Intelligence and Data Act (AIDA)](https://ised-isde.canada.ca/site/innovation-better-canada/en/artificial-intelligence-and-data-act) - Canada's proposed AI regulation, part of Bill C-27 (prorogued January 2025; did not become law). Retains relevance as the reference point for Canadian AI governance discussions.
- [OECD AI Principles](https://oecd.ai/en/ai-principles) - The baseline international principles adopted by 46 countries. Foundational vocabulary for cross-border deployments.

## Standards bodies and working groups

- [IETF SCITT WG](https://datatracker.ietf.org/wg/scitt/about/) - Supply Chain Integrity, Transparency and Trust. The relevant working group for cryptographic audit chains for software supply chains and increasingly for AI provenance.
- [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) - Adjacent standard for cryptographically signed attestations.
- [ETSI TC ESI](https://www.etsi.org/committee/esi) - European Telecommunications Standards Institute, Electronic Signatures and Infrastructure. Where the RFC 3161 trusted timestamping conversation lives.
- [OASIS](https://www.oasis-open.org/) - Standards body where several AI-trust-related profiles are being drafted.
- [IEEE 2089-2021](https://standards.ieee.org/ieee/2089/7633/) - Standard for age-appropriate digital services. Relevant to AI systems that interact with or make decisions about minors.

## Research papers

- [Concrete Problems in AI Safety (Amodei et al., 2016)](https://arxiv.org/abs/1606.06565) - The canonical pre-LLM safety paper. Still foundational vocabulary for the field.
- [Constitutional AI: Harmlessness from AI Feedback (Bai et al., 2022)](https://arxiv.org/abs/2212.08073) - Anthropic's paper on guiding model behaviour via a written constitution.
- [On the Opportunities and Risks of Foundation Models (Bommasani et al., 2021)](https://arxiv.org/abs/2108.07258) - Stanford CRFM's comprehensive survey of risks from large pre-trained models. The paper that put foundation model governance on the enterprise agenda.
- [Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training (Hubinger et al., 2024)](https://arxiv.org/abs/2401.05566) - On models that behave differently in training versus deployment. Directly relevant to deployment-time audit requirements.
- [Alignment Faking in Large Language Models (Greenblatt et al., 2024)](https://arxiv.org/abs/2412.14093) - Anthropic paper demonstrating that models can strategically comply during training while pursuing different goals at deployment. A significant input to the case for tamper-evident audit records.
- [Risks from Learned Optimization in Advanced Machine Learning Systems (Hubinger et al., 2019)](https://arxiv.org/abs/1906.01820) - Introduces mesa-optimization and deceptive alignment. Foundational for anyone designing oversight mechanisms for learned systems.
- [Datasheets for Datasets (Gebru et al., 2018)](https://arxiv.org/abs/1803.09010) - The paper that established the expectation for dataset documentation. Directly cited in EU AI Act Article 10 training data requirements.
- [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993) - Established the model card format. Now a de facto standard for responsible AI disclosure and referenced in several national AI governance frameworks.

## Open-source primitives

- [Nexuscone](https://github.com/aperintel/nexuscone) - Tamper-evident audit ledger with SHA-256 hash chain, optional Ed25519 signing, optional Bitcoin anchoring via OpenTimestamps. Apache 2.0.
- [OpenTimestamps](https://opentimestamps.org/) - Free Bitcoin-anchored timestamping. The substrate for cryptographic audit anchoring.
- [Sigstore](https://www.sigstore.dev/) - Free signing infrastructure for software supply chains. Increasingly used in AI model attestation.
- [in-toto](https://in-toto.io/) - Framework for protecting software supply chain integrity. Adjacent to AI provenance work.
- [Giskard](https://github.com/Giskard-AI/giskard) - Open-source testing framework for ML models and LLM applications. Covers vulnerability scanning, bias detection, and robustness testing in one tool.
- [Evidently AI](https://github.com/evidentlyai/evidently) - Open-source ML and LLM observability. Drift detection, data quality checks, and model performance monitoring with a Python-first API.
- [Promptfoo](https://github.com/promptfoo/promptfoo) - Open-source LLM testing and red-teaming. Runs automated evaluations against prompts, catches regressions, and surfaces security vulnerabilities before deployment.
- [Counterfit](https://github.com/Azure/counterfit) - Microsoft's command-line tool for security testing of AI systems. Implements adversarial ML attacks to assess robustness to evasion, poisoning, and extraction.

## Commercial governance platforms

- [Credo AI](https://www.credo.ai/) - Enterprise AI governance platform. Mature regulator-facing posture.
- [Holistic AI](https://www.holisticai.com/) - EU AI Act focused governance platform.
- [Fiddler AI](https://www.fiddler.ai/) - AI observability and audit platform.
- [Trustible](https://trustible.ai/) - AI governance and risk management.
- [Modulos](https://www.modulos.ai/) - One of the first platforms with ISO 42001 product conformity.
- [Saidot](https://www.saidot.com/) - EU AI Act focused governance platform, Helsinki-based.
- [Arthur AI](https://www.arthur.ai/) - Enterprise ML monitoring, explainability, and fairness. Strong financial-services and insurance client base.
- [WhyLabs](https://whylabs.ai/) - AI observability platform built on whylogs, an open-source data logging library.
- [Arize AI](https://arize.com/) - ML observability and LLM tracing. Strong tooling for production model debugging and performance monitoring.

## AI security and red-team tools

- [PyRIT](https://github.com/Azure/PyRIT) - Microsoft's Python Risk Identification Tool for generative AI red teaming.
- [Garak](https://github.com/NVIDIA/garak) - LLM vulnerability scanner. Tests for prompt injection, data leakage, hallucination, and other failure modes.
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) - NVIDIA's open-source toolkit for adding programmable guardrails to LLM applications.
- [Promptfoo](https://github.com/promptfoo/promptfoo) - LLM red-teaming and regression testing. Configurable attack strategies and automated evaluation pipelines.
- [LlamaGuard](https://github.com/meta-llama/PurpleLlama/tree/main/Llama-Guard4) - Meta's open-source content-safety classification model (v4, latest). Designed to be used as an input-output safeguard in production LLM systems.
- [Counterfit](https://github.com/Azure/counterfit) - Adversarial ML attack framework for assessing model robustness.

## Observability and audit tools

- [Langfuse](https://langfuse.com/) - Open-source LLM observability. Tracing, evaluations, and prompt management.
- [Helicone](https://helicone.ai/) - LLM observability platform with caching, rate limiting, and usage analytics.
- [PostHog LLM Observability](https://posthog.com/docs/ai-engineering/observability) - LLM observability inside the broader PostHog product analytics platform.
- [Arize Phoenix](https://github.com/Arize-ai/phoenix) - Open-source LLM tracing and evaluation. Strong on retrieval-augmented generation debugging and multi-turn conversation traces.
- [Weights & Biases Weave](https://weave-docs.wandb.ai/) - LLM tracing and evaluation built into the W&B platform. Tracks prompts, responses, and model lineage across experiments.
- [MLflow](https://mlflow.org/) - Open-source ML lifecycle platform. The model registry, experiment tracking, and lineage components are the governance-relevant pieces.

## Agentic AI governance

Agentic AI systems plan across multiple steps, call external tools, and act with limited human involvement. They introduce governance requirements not covered by standard LLM deployment checklists. This section covers resources specific to governing autonomous and multi-agent systems.

- [EU AI Office: General-Purpose AI Guidance](https://digital-strategy.ec.europa.eu/en/policies/ai-office) - The AI Office's developing guidance on general-purpose AI models, increasingly covering agentic capabilities and autonomous decision chains.
- [NIST AI 600-1 Agentic Considerations](https://airc.nist.gov/Docs/1) - NIST's generative AI profile includes specific risk considerations for agentic systems: planning, tool use, goal pursuit, and multi-step reasoning.
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - Anthropic's open standard for connecting AI agents to tools and data sources. The de facto standard for agentic tool use; understanding it is prerequisite to auditing agentic systems.
- [agentgateway](https://agentgateway.dev/) - Linux Foundation open-source proxy for MCP tool calls and agent-to-agent traffic. Includes an OPA policy engine, RBAC, and OTel emission. The governance control point for agentic tool use.
- [OpenTelemetry GenAI Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) - The emerging standard for emitting structured observability spans from AI and agent systems. Required reading for anyone building agentic audit infrastructure.
- [AgentBench](https://github.com/THUDM/AgentBench) - Open-source benchmark for evaluating LLM agents on real-world tasks. Useful for establishing a performance baseline before regulated deployment.

## Bias, fairness and impact assessment

- [Fairlearn](https://fairlearn.org/) - Microsoft's open-source toolkit for assessing and improving model fairness. Python API, mitigation algorithms, and a visual dashboard.
- [AI Fairness 360 (AIF360)](https://github.com/IBM/AIF360) - IBM Research's open-source library covering bias detection and mitigation from pre-processing through to post-processing.
- [What-If Tool](https://pair-code.github.io/what-if-tool/) - Google's visual interface for probing ML model behaviour across demographic subgroups, without writing code.
- [Aequitas](https://github.com/dssg/aequitas) - Open-source bias and fairness audit toolkit from the University of Chicago Data Science for Social Good group.
- [Algorithmic Impact Assessment (AIA) Guidance](https://www.canada.ca/en/government/system/digital-government/digital-government-innovations/responsible-use-ai/algorithmic-impact-assessment.html) - Canada's published framework for assessing the impact of automated decision-making in public-sector contexts. Widely referenced in private-sector practice.
- [NYC Local Law 144 (Automated Employment Decision Tools)](https://www.nyc.gov/site/dca/about/automated-employment-decision-tools.page) - The first US law to mandate bias audits for AI in hiring. Sets a practical floor for what a bias audit must demonstrate.

## Regulators and policy-making bodies

- [UK Information Commissioner's Office (ICO)](https://ico.org.uk/) - UK data protection regulator. The primary regulator most AI products in the UK encounter.
- [European Commission AI Office](https://digital-strategy.ec.europa.eu/en/policies/ai-office) - The EU AI Office, responsible for implementing the AI Act at EU level.
- [UK AI Safety Institute](https://www.aisi.gov.uk/) - Evaluates frontier models and publishes safety guidance.
- [US AI Safety Institute (NIST)](https://www.nist.gov/aisi) - The US AI Safety Institute, established within NIST.
- [Financial Conduct Authority (FCA)](https://www.fca.org.uk/publications/discussion-papers/dp2-22-ai-and-machine-learning) - UK financial-services regulator. Their AI/ML discussion paper and Consumer Duty guidance are the primary documents for fintech AI governance.
- [Prudential Regulation Authority (PRA)](https://www.bankofengland.co.uk/prudential-regulation) - UK prudential regulator for banks and insurers. Their AI in financial services work runs alongside the FCA's.
- [European Banking Authority (EBA)](https://www.eba.europa.eu/) - EU banking regulator. Their guidelines on internal governance and ICT risk management apply to AI systems in financial services.
- [European Securities and Markets Authority (ESMA)](https://www.esma.europa.eu/) - EU capital markets regulator. Published guidance on AI in investment management and financial advice.
- [US Federal Trade Commission (FTC)](https://www.ftc.gov/business-guidance/blog/2023/02/keep-your-ai-claims-in-check) - US consumer protection regulator. Their AI guidance focuses on deceptive claims, discrimination, and unfair practices in AI-mediated consumer decisions.

## Industry conferences

- [Money 20/20](https://www.money2020.com/) - Algorithmic decisioning and AI in financial services.
- [FAccT](https://facctconference.org/) - ACM Fairness, Accountability, and Transparency Conference. The primary academic venue for ML fairness and accountability research.
- [AIES](https://www.aies-conference.com/) - AAAI/ACM AI Ethics and Society.
- [Compliance Week Europe](https://www.complianceweek.com/) - Compliance officer audience; AI governance is an increasingly prominent track.
- [AI Safety Summit](https://www.gov.uk/government/topical-events/ai-safety-summits) - UK-government-convened summits on frontier AI risks. Published commitments from labs and governments.

## Newsletters and blogs

- [Stratechery on AI Policy](https://stratechery.com/) - Ben Thompson's analysis where it touches AI regulation and market structure.
- [Import AI](https://importai.substack.com/) - Jack Clark's policy-and-research weekly. One of the most consistently well-sourced newsletters in the field.
- [The Algorithm (MIT Technology Review)](https://www.technologyreview.com/newsletters/the-algorithm/) - MIT Technology Review's AI newsletter, strong on regulatory and societal coverage.


## Books

- [The Alignment Problem (Brian Christian, 2020)](https://brianchristian.org/the-alignment-problem/) - Accessible introduction to the alignment problem.
- [Algorithms of Oppression (Safiya Umoja Noble, 2018)](https://safiyaunoble.com/research-writing/) - Foundational text on algorithmic bias and its real-world consequences.
- [Atlas of AI (Kate Crawford, 2021)](https://katecrawford.net/) - Examines the material and political dimensions of AI infrastructure. Relevant background for anyone building governance frameworks that go beyond technical compliance.
- [The Ethical Algorithm (Michael Kearns and Aaron Roth, 2019)](https://global.oup.com/academic/product/the-ethical-algorithm-9780190948207) - How to design algorithms that are fair, private, and robust. Written for practitioners, not just researchers.

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the criteria a new entry must meet (it must materially help a practitioner ship or audit AI in a regulated environment; pure ethics commentary or generic AI-news links go elsewhere).

## Licence

This list is published under [CC0 1.0 Universal](LICENSE). The linked resources retain their own licences.
