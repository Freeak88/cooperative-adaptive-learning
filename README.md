# Cooperative Adaptive Learning
### Can AI agents learn more together while using less compute?

**An open, bilingual research protocol on compute-efficient cooperative multi-agent learning, adaptive peer teaching, continual learning, and resource allocation under hard budgets.**

[**Español**](README.es.md) · [**Research protocol**](docs/RESEARCH_PROTOCOL.md) · [**Related work**](docs/RELATED_WORK.md) · [**Collaboration invitation**](docs/COLLABORATE.md)

> **Status: early research proposal — v0.1, October 24, 2026.** No algorithmic advantage, benchmark result, peer-reviewed publication or institutional affiliation is claimed. We are actively seeking critique of novelty and experimental design.

## The research question

**Under the same total compute budget, can a heterogeneous community of learning agents perform better by deciding *when to teach, repair, train, collaborate or conserve resources*?**

Conventional learning systems often optimize individual models or allocate capacity based on immediate performance. We want to test whether **adaptive mutual aid** can create higher long-term collective capability per unit of compute **without systematically erasing weaker agents' previously acquired skills**.

The proposal is inspired by **Kropotkin's mutual aid**, **Ostrom's governance of shared resources**, and research on **collective intelligence** and **multi-agent reinforcement learning (MARL)**. This inspiration does not constitute scientific evidence of superiority.

### Research at a glance

| Dimension | Proposed evaluation |
|---|---|
| Goal | Verified held-out task success per total resource consumed |
| Adaptation | Learn whether to teach peers, recover skills, update locally, collaborate or do nothing |
| Constraints | Hard aggregate compute/communication budget; explicit historical skill-retention reporting |
| Controls | Independent learners, population-based training, fixed peer teaching and ablations |
| Realism | Changing tasks, heterogeneous capabilities, scarce and variable hardware |
| Deliverable | A **falsifiable, reproducible** research result — including negative findings |

## Proposed learning loop

~~~mermaid
flowchart TD
    A["Heterogeneous learners<br/>and shared task"] --> B["Observe skills,<br/>uncertainty and remaining budget"]
    B --> C{"Which learning action<br/>has best expected value?"}
    C --> D["Teach or request help"]
    C --> E["Retrieve or repair skills"]
    C --> F["Train or adapt locally"]
    C --> G["Collaborate on task"]
    C --> H["No-op; save resources"]
    D --> I["Independent evaluation"]
    E --> I
    F --> I
    G --> I
    H --> I
    I --> J["Measure success, cost<br/>and per-agent retention"]
    J --> B
~~~

The diagram is **a proposed decision policy**, not a working implementation. Controller overhead, teacher/model calls and communication must all count against the same budget.

## The hypothesis we would like to falsify

An adaptive-support learning policy could improve **held-out correctness per compute unit**, compared with matched-budget independent, competitive and fixed-cooperation baselines, especially when agents have **complementary specializations** and skills taught today can be **reused tomorrow**.

It might also fail: coordination overhead, unstable policies or scarce bandwidth could make cooperation *less* efficient.

**Illustrative go/no-go target:** at least **20% lower all-in resource cost** at non-inferior held-out accuracy, plus a justified limit on loss of prior skills. This target is proposed in advance, **not an observed saving**.

## Research status and roadmap

- [x] Public research question and bilingual explanation
- [x] Draft protocol, explicit falsification criteria and prior-art map
- [x] Ethics and provenance safeguards
- [ ] Independent critical review of baseline selection and novelty
- [ ] Freeze detailed preregistration, metrics, task splits and budget rules
- [ ] Reproducible CPU-first simulation with multiple random seeds
- [ ] Publish matched-budget results, including negative results
- [ ] Consider small open-weight models and heterogeneous nodes only if justified

**We deliberately do not ship an AI framework or train a new model before the experiment warrants it.**

## What is *not* new

Population Based Training (2017) already optimizes populations and schedules; LeCTR (2019) already studies peer teaching; MH-MARL (2023) explores mutual help; Meta-Team and TPGO (2026) study self-evolving agent teams; MEAL (ICML 2026) provides a continual multi-agent benchmark. Research on fairness and shared resource constraints is also well established.

The possible contribution is the **joint, end-to-end empirical test of adaptive support decisions, historical-skill retention and strict all-in compute budgets**. Even this intersection may have closer prior art. See [the annotated literature review](docs/RELATED_WORK.md), and please tell us what we've missed.

## Why resource-constrained and Latin American contexts?

Many universities, cooperatives, public institutions and independent laboratories cannot fund frontier-model training. The research asks whether distributed knowledge, complementary specializations and careful use of small computers can improve their effective access to AI capabilities.

This is **not** a claim that a network of ordinary machines can replace frontier-scale training or that artificial intelligence automatically reduces inequality. Energy, communication, licensing, infrastructure, local autonomy and distribution of benefits must be measured.

This initiative welcomes research participation **from Latin America and everywhere else**. No university, institution or funding source is claimed as a partner.

## Read the protocol / Explore

| Document | Purpose |
|---|---|
| [Research protocol](docs/RESEARCH_PROTOCOL.md) | RQs, hypothesis tests, comparators, variables, phases, cost accounting |
| [Related work and novelty boundaries](docs/RELATED_WORK.md) | Verified academic references and counterevidence |
| [Preregistration template](docs/PREREGISTRATION.md) | What must be frozen before confirmatory testing |
| [Ethics and epistemic boundaries](docs/ETHICS.md) | No naturalistic fallacy, protections and scope |
| [Call for academic collaborators](docs/COLLABORATE.md) | Invitation in English and Spanish |
| [Resumen en español](README.es.md) | Accessible Spanish entrypoint |
| [Contributing](CONTRIBUTING.md) · [Citation](CITATION.cff) | Corrections, reproducibility and attribution |

## Call for collaborators

We're looking for people working on **multi-agent reinforcement learning, resource-constrained AI, meta-learning, continual learning, game theory, collective intelligence, distributed learning, algorithmic fairness and open science**.

The highest-value first contribution is **finding a paper or baseline that disproves our novelty claim**. Open a [research feedback Issue](https://github.com/Freeak88/cooperative-adaptive-learning/issues/new/choose), propose a precise correction or suggest a CPU-only benchmark.

**Citation:** This is a public research protocol, not a peer-reviewed paper. Use GitHub's *Cite this repository* panel / [CITATION.cff](CITATION.cff) and reference the relevant commit for reproducibility.

**License:** MIT. Open research does not imply endorsement of its claims.

<sub>Search terms: cooperative adaptive learning · mutual aid AI · compute-efficient multi-agent learning · resource-constrained AI · peer teaching MARL · collaborative meta-learning · continual learning · skill retention · collective intelligence · Latin American AI research.</sub>
