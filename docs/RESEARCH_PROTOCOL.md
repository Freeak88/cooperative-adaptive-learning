# Research protocol | Budget-aware mutual-aid learning

**Status:** Draft research protocol v0.1 — 2026-10-24. Not preregistered; no experiment has been run.  
**Scope:** Compute-efficient cooperative multi-agent learning under resource scarcity, with individual-capability retention and repair.

## Abstract

We investigate whether *adaptive mutual aid* among heterogeneous learning agents can improve verified collective performance per unit of end-to-end computational cost while preserving previously acquired individual capabilities. Agents may teach peers, access shared memory, undertake local updates, recover forgotten skills, collaborate at inference time, or refrain from intervention. A resource-aware controller selects actions using bounded estimates of future learning benefit. The proposed research compares this controller against non-cooperative learning, population-based training, fixed peer teaching, and simpler resource allocation baselines under matched budgets. No claim of novelty, efficiency, or moral status of current AI systems is assumed.

## Research questions

- **RQ1 (efficiency):** Under a fixed total resource budget, does adaptive peer support improve held-out task performance relative to strong competitive and fixed-cooperation controls?
- **RQ2 (retention):** Can it reduce worst-agent skill regression during a shifting sequence of tasks?
- **RQ3 (allocation):** When is helping a lower-performing specialist more cost-effective than further training a higher-performing one?
- **RQ4 (resilience):** How do task drift, resource scarcity, node heterogeneity, and communication costs change those results?
- **RQ5 (mechanism):** Are observed gains due to the *adaptive allocation of support* rather than simply more interaction, memory, or compute?

## The intervention

At decision step t, controller policy π observes only information available at that time:
- per-agent validation performance and uncertainty;
- skills retained across previous tasks;
- currently available compute, memory and communication budgets;
- estimated costs of help, local updates, retrieval, collaboration and no-op;
- failure history and specialization overlap.

An action aₜ belongs to {teach(i,j), retrieve(i), train(i), repair(i), collaborate(S), noop}. The policy may change how learning resources are allocated; **it cannot modify held-out tests or silently redefine the success metric**. For v0.1, a transparent cost-aware bandit or contextual ranking controller is preferable to a costly LLM supervisor. Parameter updates are optional in later phases, not required to validate the mechanism.

## Budget model and primary outcome

Let Q(T) be team performance on a hidden held-out evaluation set after T learning steps, C(T) the aggregate cost including training, inference, teacher calls, coordination and communications, and B the budget.

Choose a policy π maximizing Q(T) subject to C(T) ≤ B. Record the **primary outcome** as the number of held-out tasks solved correctly per normalized unit of measured compute expenditure. Report *both* absolute quality at fixed budget and quality/cost; do not reward merely refusing hard tasks.

For a fair comparison report:
- physical CPU/GPU seconds and peak memory;
- energy (if measured, with methodology), API expenses where applicable;
- tokens and messages for LLM variants;
- wall-clock latency (secondary, since parallelism confounds aggregate compute);
- task throughput and success, including per-task difficulty.

Costs must include evaluation and controller overhead if these vary between conditions. Do not count hidden-test feedback as training information.

## Retention / capability constraint

For each agent i, define pre-registered reference tasks Sᵢ and score Pᵢ(t). Record max individual regression maxᵢ(Pᵢ(0)-Pᵢ(T)) and worst-agent change minᵢ(Pᵢ(T)-Pᵢ(0)). The *proposed* constraint is Pᵢ(T) ≥ Pᵢ(0)-ε for all i, subject to feasibility. **Infeasible constraints must be reported, not concealed.**

Do not equate preservation of a software configuration with ethical rights or consciousness.

## Experimental phases

### Phase 0: audit and setup (no model training)
- Complete a dated systematic search and map related work, especially LeCTR, MH-MARL, PBT, Meta-Team, TPGO, continual MARL and budget-aware multi-agent allocation.
- Define task generator, deterministic scoring, budget accounting, minimum meaningful effect, and leakage barriers.
- Freeze pilot hypotheses before looking at final test results.

### Phase 1: inexpensive simulation (CPU preferred)
- Four heterogeneous learners with non-overlapping initial strengths; 3–5 consecutive task families with controlled distribution shift.
- Pre-specified compute budgets: low, medium, high, reported in normalized units and actual wall/CPU time.
- Equal random seeds / task sequences across methods; at least 10 seeds in confirmatory runs after pilot feasibility.
- Held-out performance on both past and new task families.
- Log every support action and its measured incremental cost.
- Report learning curves, budget-consumption curves, Pareto frontiers, variance and confidence intervals.

### Phase 2: small open-weight models (conditional)
Only if Phase 1 shows reproducible gains, transfer the policy to modest open models with optional retrieval, distillation or LoRA adapters. Account for all inference and training costs and include an equivalent-budget single-model baseline. Respect data/model licenses and privacy.

### Phase 3: heterogeneous Latin American nodes (conditional)
Simulate first, then test intermittent network links, asymmetric hardware and cross-institution contributions. Avoid sending private data to unauthorized nodes. Measure communication costs explicitly; do not assume decentralization is cheaper.

## Comparator methods

1. **Independent learners:** no cross-agent support.
2. **PBT-style:** score-based exploit/explore and resource reassignment; retain a fair equivalent implementation of reference algorithm.
3. **Fixed peer teaching:** same communication capacity, fixed policy deciding whom to help.
4. **Adaptive controller without fairness/retention term:** ablation isolating the cost of constraints.
5. **Adaptive mutual aid (proposed):** resource-aware support plus a retention safeguard.
6. **Oracle upper bound (simulation only, optional):** full counterfactual information, labeled unattainable in practice.

For LLM-phase comparisons include a single stronger model within the *same money/compute* budget.

## Registered hypotheses (provisional; freeze before first confirmatory run)

- **H1:** Adaptive mutual aid has greater held-out correct solutions per compute unit than each feasible comparator.
- **H2:** It has lower worst-agent capability loss than performance-only allocation at matched budget.
- **H3:** Its advantage, if any, grows with specialization complementarity and reusability of taught skills.
- **H4:** Beyond a communication-cost threshold, multi-agent support ceases to be efficient.

**Candidate go/no-go threshold:** at least 20% lower total cost at non-inferior held-out success (non-inferiority margin to be specified by benchmark), and no meaningful regression in protected skills, across seeds. This is an *a priori proposed target*, not an achieved result.

## Negative results and falsification

The claim is unsupported if benefits vanish against matched-budget baselines; if gains result solely from leaked test feedback; if controller overhead exceeds savings; if individual retention regularly fails; or if confidence intervals are compatible with no effect. Results that favor competitive baselines will be published alongside positive results.

## Statistical and reproducibility plan

- Run pilot sweeps separately from confirmatory evaluations.
- Pre-register final tasks, seeds, budgets, outcomes, stopping rules, exclusion criteria and effect thresholds.
- Report per-seed results, bootstrap uncertainty or justified statistical tests, hardware, versions, model hashes and exact cost accounting.
- Use predeclared paired comparisons, plus confidence intervals for both quality and resource differences.
- Publish code and permissibly redistributable data, scripts and configuration; clearly label unavailable third-party resources.
- Do not claim a peer-reviewed article, released dataset or validated algorithm before one exists.

## Scope and ethics

The references to Kropotkin's mutual aid, Ostrom's common-pool governance, and multicellular cooperation motivate research questions, **not biological proofs or moral prescriptions**. A model replica is not automatically a person; possible future AI welfare remains an open ethical question. Do not use social or medical analogies to classify human beings as disposable, defective or cancer-like. See [Ethics](ETHICS.md).

## Next evidence milestone

An externally reproducible CPU-only experiment demonstrating whether support allocation yields measurable benefits against **independent learning, fixed teaching and a score-based baseline** under identical task sequences and cost budgets. Until then, this repository presents a research proposal, not confirmed findings.
