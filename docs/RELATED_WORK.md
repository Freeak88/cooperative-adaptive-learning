# Related work and novelty boundaries

**Evidence status:** annotated starting bibliography, manually checked against publisher or author pages on 2026-10-24. This is *not* an exhaustive systematic review.

| Work | Contribution | What our proposal must add/test |
|---|---|---|
| [Jaderberg et al. (2017), Population Based Training](https://arxiv.org/abs/1711.09846) | Adaptive schedules and population exploitation/exploration under resource budgets | Peer support, retention and aggregate cost accounting compared directly to PBT |
| [Omidshafiei et al. (2019), Learning to Teach in Cooperative MARL](https://doi.org/10.1609/aaai.v33i01.33016128) | LeCTR: agents learn when and what to teach one another | Learning under explicit scarce-resource and long-horizon preservation constraints |
| [Qiu et al. (2023), Promoting Cooperation in MARL via Mutual Help](https://arxiv.org/abs/2302.09277) | MH-MARL: expectation-guided selective imitation | Distinguish proposed help decisions from selective imitation |
| [Leonard & Levin (2022), Collective intelligence as a public good](https://doi.org/10.1177/26339137221083293) | Collective gain, individual costs, game-theoretic tensions | Operationalize gain *and* per-agent regression under cost |
| [He et al. (2026), Learning to Evolve / TPGO](https://doi.org/10.18653/v1/2026.findings-acl.1534) | Meta-optimization of team prompts and tool/workflow graphs | Avoid claiming self-improving optimization as original |
| [Hao et al. (2026), Meta-Team](https://arxiv.org/abs/2605.29790) | Multi-scale experience sharing and self-evolution of LLM teams | Move beyond prompt/team evolution by measuring adaptive investment in teach/repair/train/no-op under hard budgets |
| [Tomilin et al. (ICML 2026), MEAL](https://proceedings.mlr.press/v306/tomilin26a.html) | Continual multi-agent benchmark; long task sequences | Test forgetting beyond short benchmark episodes; adopt benchmark where feasible |
| [Cao et al. (2026), LiRA](https://arxiv.org/abs/2610.07491) | Learns responsibility for shared constraints to improve welfare | Direct comparator in resource allocation; do not claim fair shared budgets are novel |
| [Goethals et al. (2026), Resource-constrained Fairness](https://proceedings.mlr.press/v350/goethals26b.html) | Fairness under hard resource constraints | Define fairness without collapsing it into average task score |
| [Kropotkin (1902), Mutual Aid](https://www.gutenberg.org/ebooks/4341) | Evolutionary and social argument for cooperation | Philosophical inspiration, not experimental support for algorithmic superiority |
| [Ostrom (1990), Governing the Commons](https://doi.org/10.1017/CBO9780511807763) | Institutional design for common-pool resources | Governance and rule adaptation, not a claim that autonomous agents follow human morality |

## What is established

Adaptive populations, peer teaching, fair budget allocation, continual multi-agent learning and self-evolving agent teams each have prior art. Simply combining these terms or naming an approach "mutual aid" is **not** sufficient novelty.

## Candidate gap (unverified)

A unified *learn-when-to-teach, repair, train or abstain* policy **under a hard aggregate resource constraint**, evaluated simultaneously for: (1) held-out collective quality, (2) per-agent historical-skill retention, (3) end-to-end cost, (4) heterogeneity and shifting tasks, and (5) overhead of the coordinating mechanism.

This remains a *candidate intersection*, not a claim that no earlier paper solved it. New contributions must be checked against this table and added as counterevidence when found.

## Search strategy for ongoing literature review

Search Google Scholar, Semantic Scholar, OpenAlex, DBLP, ACL Anthology, PMLR and arXiv. Proposed queries:

- "budget-aware multi-agent continual learning"
- "adaptive peer teaching multi-agent reinforcement learning"
- "mutual help resource allocation heterogeneous agents"
- "team self-evolution cost-aware agent coordination"
- "collective intelligence worst-agent retention fairness"
- "compute constrained cooperative meta-learning"
- "agent learning controller teach train retrieve noop"

Keep a dated search log with query, venue, inclusion reason and notes. Review code and benchmark artifacts, not just abstracts. Update this list when close prior art appears.
