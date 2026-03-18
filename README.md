# Awesome RL-based Agentic Search Papers
This repository summarizes recent research on reinforcement‑learning (RL)‑based agentic search systems. These systems treat information‑seeking as a decision process: when a large language model (LLM) faces a complex question, it can plan and act by issuing search queries, revising those queries, and integrating evidence into its reasoning. RL techniques allow these agents to learn when to search, how intensively to search and how to integrate retrieved evidence into reasoning.

For more details, please check out our survey paper: [A Comprehensive Survey on Reinforcement Learning-based Agentic Search: Foundations, Roles, Optimizations, Evaluations, and Applications](https://arxiv.org/abs/2510.16724). If you find this repository helpful, please cite our survey paper.

```
@article{lin2025comprehensive,
  title={A Comprehensive Survey on Reinforcement Learning-based Agentic Search: Foundations, Roles, Optimizations, Evaluations, and Applications},
  author={Minhua Lin, Zongyu Wu, Zhichao Xu, Hui Liu, Xianfeng Tang, Qi He, Charu Aggarwal, Hui Liu, Xiang Zhang, Suhang Wang},
  journal={arXiv preprint arXiv:2510.16724},
  year={2025}
}
```

We are actively maintaining this repository!

## Contents
* [Overview of RL-based Agentic Search](#overview-of-rl-based-agentic-search)
* [Illustrative Framework of RL-based Agentic Search](#illustrative-framework-of-rl-based-agentic-search)
* [Representative Survey](#representative-survey)
* [Method](#method)
* [Evaluation](#evaluation)

## Overview of RL-based Agentic Search
![Overview of RL-based Agentic Search](figures/overview_rl_agentic_search.jpg)

## Illustrative Framework of RL-based Agentic Search
![Illustrative Framework of RL-based Agentic Search](figures/figure_rl_search_framework.jpg)

## Representative Survey
| Time  | Paper Title | Venue |
| :---- | :----------- | :---- |
| 2026.3 | [SoK: Agentic Retrieval-Augmented Generation (RAG): Taxonomy, Architectures, Evaluation, and Research Directions](https://arxiv.org/abs/2603.07379) | *arXiv* |
| 2026.1 | [Agentic Reasoning for Large Language Models](https://arxiv.org/abs/2601.12538) | *arXiv* |
| 2025.12 | [Deep Research: A Systematic Survey](https://arxiv.org/abs/2512.02038) | *arXiv* |
| 2025.10 | [A Comprehensive Survey on Reinforcement Learning-based Agentic Search: Foundations, Roles, Optimizations, Evaluations, and Applications](https://arxiv.org/abs/2510.16724) | *arXiv* |
| 2025.9 | [Reinforcement Learning Foundations for Deep Research Systems: A Survey](https://arxiv.org/abs/2509.06733) | *arXiv* |
| 2025.9 | [The Landscape of Agentic Reinforcement Learning for LLMs: A Survey](https://arxiv.org/abs/2509.02547) | *TMLR* |
| 2025.8 | [A Survey of LLM-based Deep Search Agents: Paradigm, Optimization, Evaluation, and Challenges](https://arxiv.org/abs/2508.05668) | *arXiv* |
| 2025.6 | [Reasoning RAG via System 1 or System 2: A Survey on Reasoning Agentic Retrieval-Augmented Generation for Industry Challenges](https://arxiv.org/abs/2506.10408) | *arXiv* |
| 2025.4 | [Synergizing RAG and Reasoning: A Systematic Review](https://arxiv.org/abs/2504.15909) | *arXiv* |
| 2025.1 | [Agentic Retrieval-Augmented Generation: A Survey on Agentic RAG](https://arxiv.org/abs/2501.09136) | *arXiv* |
---

## Method
### How RL is Used: Optimization Strategies
The below table summarizes representative works with corresponding optimization strategies. Specifically, ORM and PRM denote the Outcome Reward Model and the Process Reward Model, respectively. “Rule-based” indicates that the reward function is entirely computed from predefined rules; otherwise, an LLM is involved as a reward judge.
<details>
<summary>📊 Click to expand long table (scrollable). </summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">

| Method | RL Func. Role | Cold Start? | Training Env. | RL Alg. | Reward Type | Reward Func. | Opt. Scope | Dataset |
|---|---|---|---|---|---|---|---|---|
| [Search-R1](https://arxiv.org/abs/2503.09516) | Adapt-Search | ✗ | Real-world | PPO<br>GRPO | Rule-based ORM | Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [ReSearch](https://arxiv.org/abs/2503.19470) | Adapt-Search | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [AutoCoA](https://arxiv.org/abs/2503.06580) | Adapt-Search | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [SimpleDeepSearcher](https://arxiv.org/abs/2505.16834) | Adapt-Search | ✓ | Real-world | SFT | - | - | Single-agent | [[2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [FRAMES](https://aclanthology.org/2024.acl-long.716/), [GAIA](https://arxiv.org/abs/2311.12983)] |
| [ExSearch](https://arxiv.org/abs/2505.20128) | Adapt-Search | ✗ | Real-world | GEM | PRM | Trajectory Quality | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [IKEA](https://arxiv.org/abs/2505.07596) | Search Efficiency | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Knowledge-boundary | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060)] |
| [R1-Searcher](https://arxiv.org/abs/2503.05592) | Adapt-Search | ✓ | Real-world | GRPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer F1 | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [R1-Searcher++](https://arxiv.org/abs/2505.17005) | Search Efficiency | ✓ | Real-world | GRPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer EM<br>Std of Search Calls | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [DeepRAG](https://arxiv.org/abs/2502.01142) | Adapt-Search<br>Search Efficiency | ✓ | Real-world | GRPO | Rule-based ORM | Answer EM<br>Retrieval Cost | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [CAG](https://arxiv.org/abs/2401.08406), [PopQA](https://arxiv.org/abs/2212.10511), [WebQuestions](https://arxiv.org/abs/1309.5229), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [UR²](https://arxiv.org/abs/2508.06165) | Adapt-Search | ✓ | Real-world<br>Curriculum | Reinforce++ | Rule-based ORM | Format<br>Answer EM<br>Fallback Penalty | Single-agent | [[MATH](https://arxiv.org/abs/2103.03874), Minerva, MedQA, MMLU-Pro, [HotpotQA](https://arxiv.org/abs/1809.09600), [Bamboogle](https://arxiv.org/abs/2210.03350), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [SSRL](https://arxiv.org/abs/2508.10874) | Adapt-Search | ✓ | Simulated<br>Self-Search | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [Pangu DeepDiver](https://arxiv.org/abs/2505.24332) | Adapt-Search<br>Search Intensity | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Extra Search | Single-agent | [[Pangu](https://arxiv.org/abs/2505.24332), [Bamboogle](https://arxiv.org/abs/2210.03350), WebWalkerQA, [FRAMES](https://aclanthology.org/2024.acl-long.716/)] |
| [ReZero](https://arxiv.org/abs/2504.11001) | Search Intensity | ✗ | Real-world | GRPO | ORM+PRM | Format<br>Answer LLM-Judge<br>Retry | Step-level | [Apollo-3] |
| [StepSearch](https://arxiv.org/abs/2505.15107) | Adapt-Search<br>Search Intensity | ✗ | Real-world | PPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Search Key<br>Information Gain<br>Redundancy Penalty | Step-level | [[HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [VERITAS](https://arxiv.org/abs/2510.13272) | Adapt-Search<br>R-Aware Opt. | ✗ | Real-world | PPO | ORM+PRM | Answer EM<br>Enhancing Faithfulness | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [ReasonRAG](https://arxiv.org/abs/2505.14069) | Search Efficiency<br>R-S Inter. | ✗ | Real-world<br>MCTS | DPO | PRM | Shortest Path | Step-level | [[PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [Web-Sailor](https://arxiv.org/abs/2507.02592) | Adapt-Search<br>Ctx-Mem. | ✓ | Real-world | DUPO | ORM | Format<br>Answer F1 | Single-agent | [[li2025sailorfogqa](https://arxiv.org/abs/2507.02592), [BrowseComp-en](https://arxiv.org/abs/2504.12516), [BrowseComp-zh](https://arxiv.org/abs/2504.19314), [GAIA](https://arxiv.org/abs/2311.12983), [XBench](https://xbench.org/)] |
| [WebSailor-V2](https://arxiv.org/abs/2509.13305) | Multi-tool<br>Ctx-Mem. | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Single-agent | [[li2025sailorfogqav2](https://arxiv.org/abs/2509.13305), [BrowseComp-en](https://arxiv.org/abs/2504.12516), [BrowseComp-zh](https://arxiv.org/abs/2504.19314), [GAIA](https://arxiv.org/abs/2311.12983), [XBench](https://xbench.org/), [HLE](https://arxiv.org/abs/2501.14249), [DeepResearchBench](https://arxiv.org/abs/2506.11763)] |
| [Search Wisely](https://arxiv.org/abs/2505.17281) | Search Efficiency | ✗ | Real-world | β-GRPO | Rule-based ORM | Confidence-based Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [HotpotQA](https://arxiv.org/abs/1809.09600), [TriviaQA](https://arxiv.org/abs/1705.03551), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [ZeroSearch](https://arxiv.org/abs/2505.04588) | Search Efficiency | ✓ | Simulated<br>Curriculum | PPO<br>GRPO<br>Reinforce | Rule-based ORM | Answer F1 | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [ParallelSearch](https://arxiv.org/abs/2508.09303) | Search Efficiency | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Query Decomopse<br>Search count | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [RAG-R1](https://arxiv.org/abs/2507.02962) | Search Efficiency<br>Conv-Reform. | ✓ | Real-world | PPO | ORM | Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [PopQA](https://arxiv.org/abs/2212.10511), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [ConvSearch-R1](https://arxiv.org/abs/2505.15776) | Conv-Reform. | ✓ | Real-world | GRPO | ORM | Format<br>Rank-Incentive | Step-level | [TopiOCQA], [QReCC] |
| [MaskSearch](https://arxiv.org/abs/2505.20285) | Conver. Reform.<br>R–S Inter. | ✓ | Real-world<br>Curriculum<br>RAMP | DAPO | Rule-based ORM | Format<br>Answer Recall<br>Length penalty | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), FANOUTQA, [MuSiQue](https://arxiv.org/abs/2108.00573), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), FreshQA] |
| [DeepRetrieval](https://arxiv.org/abs/2503.00223) | R-Aware Opt. | ✓ | Simulated | PPO | ORM | Format<br>Answer Recall | Single-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), SQuAD, FEVER, FactoidQA] |
| [WebThinker](https://arxiv.org/abs/2504.21776) | Search Efficiency | ✗ | Real-world | DPO | PRM | Answer EM<br>Tool Calls<br>Length penalty | Single-agent | [GPQA], [GAIA](https://arxiv.org/abs/2311.12983), WebWalkerQA, [HLE](https://arxiv.org/abs/2501.14249), [SuperGPQA](https://arxiv.org/abs/2502.14739), OpenThoughts, NaturalReasoning, NuminaMath |
| [s3](https://arxiv.org/abs/2505.14146) | R-Aware Opt. | ✓ | Simulated | PPO | Rule-based ORM | Gain Beyond RAG | Module-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573)] |
| [R-Search](https://arxiv.org/abs/2506.04185) | R–S Inter. | ✗ | Real-world | PPO<br>GRPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Evidence Quality | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [AutoRefine](https://arxiv.org/abs/2505.11277) | R–S Inter. | ✗ | Real-world | GRPO | ORM+PRM | Answer F1<br>Retrieval Reward | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| [EvolveSearch](https://arxiv.org/abs/2505.22501) | R–S Inter. | ✓ | Real-world<br>Self-evolving | GRPO | ORM | Format<br>Answer LLM-Judge | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| [O²-Searcher](https://arxiv.org/abs/2505.16582) | R–S Inter. | ✓ | Simulated | GRPO | Rule-based ORM | Format<br>Diversity reward<br>Factual reward | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [HotpotQA](https://arxiv.org/abs/1809.09600), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [Atom-Searcher](https://arxiv.org/abs/2508.12800) | R–S Inter. | ✓ | Real-world<br>Curriculum | GRPO | PRM+Rule-based ORM | Format<br>Answer F1<br>Atomic thought reward | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| [ReSum](https://arxiv.org/abs/2509.13313) | Ctx-Mem. | ✗ | Real-world | Resume-GRPO | ORM | Answer LLM-Judge | Single-agent | [[GAIA](https://arxiv.org/abs/2311.12983), [BrowseComp-en](https://arxiv.org/abs/2504.12516), [BrowseComp-zh](https://arxiv.org/abs/2504.19314), WebWalkerQA, [XBench](https://xbench.org/)] |
| [SFR-DeepResearch](https://arxiv.org/abs/2509.06283) | Ctx-Mem.<br>Multi-tool | ✗ | Real-world | REINFORCE | ORM | Answer LLM-Judge | Single-agent | [[FRAMES](https://aclanthology.org/2024.acl-long.716/), [GAIA](https://arxiv.org/abs/2311.12983), [HLE](https://arxiv.org/abs/2501.14249)] |
| [MAO-ARAG](https://arxiv.org/abs/2508.01005) | P–E Orches. | ✓ | Real-world | PPO | ORM | Format<br>Cost Penalty<br>Answer F1 | Multi-agent | [[NQ](https://aclanthology.org/Q19-1026/), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511), AmbigQA] |
| [OPERA](https://arxiv.org/abs/2508.16438) | P–E Orches. | ✓ | Real-world | MAPGRPO | PRM+ORM | Answerer Reward<br>Planer Reward<br>Rewriter Reward | Multi-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [NQ](https://aclanthology.org/Q19-1026/), [Multihop-rag](https://arxiv.org/abs/2401.15391)] |
| [AI-SearchPlanner](https://arxiv.org/abs/2508.20368) | P–E Orches. | ✗ | Real-world | PPO | ORM | Answer LLM-Judge<br>Trajectory Rationality | Module-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| [AgentFlow](https://arxiv.org/abs/2510.05592) | P–E Orches. | ✗ | Real-world | Flow-GRPO | Rule-based ORM | EM<br>LLM Judge | Module-level | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [AIME24](), [AMC23](), [Gameof24](), [GPQA](), [MedQA]()] |
| [SIRAG](https://arxiv.org/abs/2509.18167) | Cooperative Multi-Agent Systems | ✗ | Real-world | PPO | PRM | Process LLM-Judge | Multi-agent | [[2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [HotpotQA](https://arxiv.org/abs/1809.09600), [NQ](https://aclanthology.org/Q19-1026/), [PopQA](https://arxiv.org/abs/2212.10511)] |
| [MMOA-RAG](https://arxiv.org/abs/2501.15228) | Cooperative Multi-Agent Systems<br>R-aware Opt. | ✗ | Real-world | MA-PPO | Rule-based ORM | Answer F1<br>Efficiency penalty | Multi-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), AmbigQA] |
| [Tool-Star](https://arxiv.org/abs/2505.16410) | Multi tool | ✓ | Real-world | REINFORCE++<br>GRPO<br>DPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [LTMS, [MATH](https://arxiv.org/abs/2103.03874), GSM8K, WebWalkerQA, [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| [WebWatcher](https://arxiv.org/abs/2508.05748) | Multi tool<br>Multi-modal | ✓ | Real-world | GRPO | ORM | Format<br>Answer LLM-Judge | Single-agent | [[HLE](https://arxiv.org/abs/2501.14249), [Wu2025mm](https://arxiv.org/abs/2503.08495), [LiveVQA](https://arxiv.org/abs/2504.05288), [MMSearch](https://arxiv.org/abs/2409.12959), [SimpleVQA](https://arxiv.org/abs/2502.13059)] |
| [Visual-ARFT](https://arxiv.org/abs/2505.14246) | Multi-modal<br>Multi-tool<br>Adapt-Search | ✓ | Real-world | GRPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Query Semantic Sim. | Single-agent | [MATSearch] |
| [VRAG-RL](https://arxiv.org/abs/2505.22019) | Multi-modal<br>Search Efficiency | ✓ | Simulated | GRPO | ORM | Format<br>Answer LLM-Judge<br>Retrieval Efficiency | Single-agent | [SlideVQA, VidORAG, MMLongBench] |
| [MMSearch-R1](https://arxiv.org/abs/2506.20670) | Multi-modal<br>Search Efficiency | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Search Penalty | Single-agent | [[MMSearch](https://arxiv.org/abs/2506.20670), [Chen2023can](https://arxiv.org/abs/2305.00733), [MMSearch](https://arxiv.org/abs/2409.12959), [SimpleVQA](https://arxiv.org/abs/2502.13059), [LiveVQA](https://arxiv.org/abs/2504.05288)] |
| [GRAIL](https://arxiv.org/abs/2508.05498) | Adapt-Search<br>Struct-Nav. | ✓ | Real-world<br>Graph Env. | GRPO | PRM | Process LLM-Judge | Single-agent | [[WebQuestions](https://arxiv.org/abs/1309.5229), MetaQA, WebQSP] |
| [DynaSearcher](https://arxiv.org/abs/2507.17365) | Struct-Nav. | ✗ | Real-world<br>Graph Env.<br>KG+Doc Search | GRPO | Rule-based ORM | Format<br>Answer F1<br>Information Gain<br>Retrieval Penalty | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [FRAMES](https://aclanthology.org/2024.acl-long.716/)] |
| [HARIS](https://arxiv.org/abs/2506.07528) | R-S Inter. | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer Accuracy<br>Decision Accuracy | Multi-agent | [M3, HoVer, CheckWhy] |
| [DeepNote](https://arxiv.org/abs/2410.08821) | Adapt-Search<br>Conv-Reform. | ✗ | Real-world | DPO | - | - | Single-agent | [[HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), StrategyQA, ASQA] |
| [DeepResearcher](https://arxiv.org/abs/2504.03160) | Adapt-Search<br>Search Efficiency<br>Ctx-Mem. | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Module-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060)] |
| [SWiRL](https://arxiv.org/abs/2504.04736) | Adapt-Search<br>R-S Inter. | ✗ | Simulated<br>Offline | Policy Gradient | PRM | Step-wise LLM-Judge (Gemini 1.5 Pro) | Step-level | [[HotpotQA](https://arxiv.org/abs/1809.09600), [MuSiQue](https://arxiv.org/abs/2108.00573), CoFCA, [GSM8K](https://arxiv.org/abs/2110.14168), Qasper, [BeerQA](https://aclanthology.org/2021.emnlp-main.292/)] |
| [WebDancer](https://arxiv.org/abs/2505.22648) ([Code](https://github.com/Alibaba-NLP/DeepResearch)) | Multi tool | ✓ | Real-world | DAPO | ORM | Answer EM | Single-agent | [[GAIA](https://arxiv.org/abs/2311.12983), WebWalkerQA, [BrowseComp-zh](https://arxiv.org/abs/2504.19314), [BrowseComp-en](https://arxiv.org/abs/2504.12516)] |
| [MedResearcher-R1](https://arxiv.org/abs/2508.14880) | Adpt-Search<br>Multi-Tool | ✓ | Real-world<br>Medical Tool | GRPO | ORM | Answer Acc<br>Response Quality<br>Efficiency penalty | Single-agent | [[XBench](https://xbench.org/), [GAIA](https://arxiv.org/abs/2311.12983), [MedBrowseComp](https://arxiv.org/abs/2505.14963)] |
| [Lucy](https://arxiv.org/abs/2508.00360) | Search Efficiency<br>R–S Inter. | ✓ | Real-world<br>SLMs | DAPO | Rule-based ORM | Format/XML validity<br>Answer EM<br>Tool exec. success<br>Visit/Search ratio<br>Efficient thinking | Single-agent | [WebWalkerQA] |
| [ASearcher](https://arxiv.org/abs/2508.07976) | R-S Inter.<br>Ctx-Mem.<br>Multi-tool | ✓ | Real-world<br>Browser Env.<br>Asynchronous | GRPO | ORM | Answer LLM-Judge | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [FRAMES](https://aclanthology.org/2024.acl-long.716/), [GAIA](https://arxiv.org/abs/2311.12983), [XBench](https://xbench.org/)] |
| [WebExplorer](https://arxiv.org/abs/2509.06501) | Ctx-Mem.<br>Conv-Reform. | ✓ | Real-world<br>Curriculum | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [[BrowseComp-zh](https://arxiv.org/abs/2504.19314), [BrowseComp-en](https://arxiv.org/abs/2504.12516), [GAIA](https://arxiv.org/abs/2311.12983), WebWalkerQA, [FRAMES](https://aclanthology.org/2024.acl-long.716/), [XBench](https://xbench.org/), [HLE](https://arxiv.org/abs/2501.14249)] |
| [WebResearcher](https://arxiv.org/abs/2509.13309) | Multi-tool | ✓ | Real-world<br>Curriculum | GSPO | Rule-based ORM | Answer EM | Single-agent | [[HLE](https://arxiv.org/abs/2501.14249), [GAIA](https://arxiv.org/abs/2311.12983), [BrowseComp-en](https://arxiv.org/abs/2504.12516), [BrowseComp-zh](https://arxiv.org/abs/2504.19314), [XBench](https://xbench.org/), [FRAMES](https://aclanthology.org/2024.acl-long.716/)] |
| [RECON](https://arxiv.org/abs/2510.10448) | Ctx-Mem. | ✓ | Real-world | PPO | Rule-based ORM | Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Bamboogle](https://arxiv.org/abs/2210.03350), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [PopQA](https://arxiv.org/abs/2212.10511)] |
| [AgentGym-RL](https://arxiv.org/abs/2509.08755) | Cooperative Multi-Agent Systems<br>Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| [Chain-of-Agents](https://arxiv.org/abs/2508.13167) | Cooperative Multi-Agent Systems<br>Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| [Verl](https://github.com/verl-project/verl) | Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| [VerlTool](https://arxiv.org/abs/2509.01055) | Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |

</div>
</details>


### What RL is for: Functional Roles in Agentic Search

#### Retrieval Control
| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.3 | [APEX-Searcher: Augmenting LLMs' Search Capabilities through Agentic Planning and Execution](https://arxiv.org/abs/2603.13853) | Adaptive Search Decision; Planner-Executor Orchestration | *arXiv* |  |
| 2026.3 | [Meta-Reinforcement Learning with Self-Reflection for Agentic Search](https://arxiv.org/abs/2603.11327) | Adaptive Search Decision; Self-Reflection | *arXiv* | [Code](https://github.com/tengxiao1/MR-Search) |
| 2026.2 | [Search More, Think Less: Rethinking Long-Horizon Agentic Search for Efficiency and Generalization](https://arxiv.org/abs/2602.22675) | Adaptive Search Decision; Search Efficiency | *arXiv* | [Code](https://github.com/OPPO-PersonalAI/SMTL) |
| 2026.2 | [How to Train Your Deep Research Agent? Prompt, Reward, and Policy Optimization in Search-R1](https://arxiv.org/abs/2602.19526) | Adaptive Search Decision; Search Efficiency | *arXiv* |  |
| 2026.2 | [REDSearcher: A Scalable and Cost-Efficient Framework for Long-Horizon Search Agents](https://arxiv.org/abs/2602.14234) | Adaptive Search Decision; Search Efficiency | *arXiv* |  |
| 2026.2 | [Agent-Omit: Training Efficient LLM Agents for Adaptive Thought and Observation Omission via Agentic Reinforcement Learning](https://arxiv.org/abs/2602.04284) | Search Efficiency | *arXiv* |  |
| 2026.2 | [IntentRL: Training Proactive User-intent Agents for Open-ended Deep Research via Reinforcement Learning](https://arxiv.org/abs/2602.03468) | Adaptive Search Decision; User-intent / Autonomy–Interaction | *arXiv* |  |
| 2026.2 | [Training Multi-Turn Search Agent via Contrastive Dynamic Branch Sampling](https://arxiv.org/abs/2602.03719) | Adaptive Search Decision; Search Efficiency | *arXiv* |  |
| 2026.1 | [BAPO: Boundary-Aware Policy Optimization for Reliable Agentic Search](https://arxiv.org/abs/2601.11037) | Adaptive Search Decision; Reliability / IDK Boundary | *arXiv* | [Code](https://github.com/Liushiyu-0709/BAPO-Reliable-Search) |
| 2026.1 | [Agentic-R: Learning to Retrieve for Agentic Search](https://arxiv.org/abs/2601.11888) | Retriever‑Aware Optimization; Adaptive Search Decision | *arXiv* | [Code](https://github.com/8421BCD/Agentic-R) |
| 2026.1 | [Agentic Conversational Search with Contextualized Reasoning via Reinforcement Learning](https://arxiv.org/abs/2601.13115) | Conversational Reformulation; Adaptive Search Decision | *arXiv* |  |
| 2026.1 | [OffSeeker: Online Reinforcement Learning Is Not All You Need for Deep Research Agents](https://arxiv.org/abs/2601.18467) | Search Efficiency; Offline Training | *arXiv* |  |
| 2025.11 | [Thinker: Training LLMs in Hierarchical Thinking for Deep Search via Multi-Turn Interaction](https://arxiv.org/abs/2511.07943) | Adaptive Search Decision; Search Intensity | *AAAI 2026* | [Code](https://github.com/OpenSPG/KAG-Thinker) |
| 2025.11 | [MemSearcher: Training LLMs to Reason, Search and Manage Memory via End-to-End Reinforcement Learning](https://arxiv.org/abs/2511.02805) | Adaptive Search Decision; Context & Memory Management | *arXiv* | [Code](https://github.com/icip-cas/MemSearcher) |
| 2025.10 | [Towards Agentic Self-Learning LLMs in Search Environment](https://arxiv.org/abs/2510.14253) | Adaptive Search Decision; Self-Learning | *arXiv* |  |
| 2025.09 | [DeepDive: Advancing Deep Search Agents with Knowledge Graphs and Multi-Turn RL](https://arxiv.org/abs/2509.10446) | Adaptive Search Decision; Search Efficiency; Structured Knowledge Navigation | *arXiv* | [Code](https://github.com/THUDM/DeepDive) |
| 2025.09 | [WebSailor‑V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable Reinforcement Learning](https://arxiv.org/abs/2509.13305) | Multi‑Tool; Context & Memory Management | *arXiv* | [Code](https://github.com/Alibaba-NLP/DeepResearch) |
| 2025.08 | [MedResearcher‑R1: Expert‑Level Medical Deep Researcher via a Knowledge‑Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) | Adaptive Search Decision; Multi‑Tool | *arXiv* | [Code](https://github.com/AQ-MedAI/MedResearcher-R1) |
| 2025.08 | [ParallelSearch: Train Your LLMs to Decompose Query and Search Sub‑Queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) | Search Efficiency | *arXiv* |  |
| 2025.08 | [SSRL: Self‑Search Reinforcement Learning](https://arxiv.org/abs/2508.10874) | Adaptive Search Decision | *arXiv* | [Code](https://github.com/TsinghuaC3I/SSRL) |
| 2025.08 | [UR²: Unify RAG and Reasoning through Reinforcement Learning](https://arxiv.org/abs/2508.06165) | Adaptive Search Decision | *arXiv* | [Code](https://github.com/Tsinghua-dhy/UR2) |
| 2025.07 | [RAG‑R1: Incentivizing the Search and Reasoning Capabilities of LLMs through Multi‑Query Parallelism](https://arxiv.org/abs/2507.02962) | Search Efficiency; Convsational Reformulation | *arXiv* | [Code](https://github.com/inclusionAI/AWorld-RL/tree/main/RAG-R1) |
| 2025.05 | [DeepDiver: Adaptive Search Intensity Scaling via Open‑Web Reinforcement Learning](https://arxiv.org/abs/2505.24332) | Adaptive Search Decision; Search Intensity | *NeurIPS 2025 (Spotlight)* |  |
| 2025.05 | [Process vs. Outcome Reward: Which Is Better for Agentic RAG Reinforcement Learning](https://arxiv.org/abs/2505.14069) | Retriever‑Aware Optimization | *NeurIPS 2025* | [Code](https://github.com/Applied-Machine-Learning-Lab/ReasonRAG) |
| 2025.05 | [Search Wisely: Mitigating Sub‑Optimal Agentic Searches by Reducing Uncertainty](https://arxiv.org/abs/2505.17281) | Search Efficiency | *EMNLP 2025 (Main)* |  |
| 2025.05 | [SimpleDeepSearcher: Deep Information Seeking via Web-Powered Reasoning Trajectory Synthesis](https://arxiv.org/abs/2505.16834) | Adaptive Search Decision | *EMNLP 2025 (Findings)* | [Code](https://github.com/RUCAIBox/SimpleDeepSearcher) |
| 2025.05 | [StepSearch: Igniting LLMs’ Search Ability via Step‑Wise Proximal Policy Optimization](https://arxiv.org/abs/2505.15107) | Adaptive Search Decision; Search Intensity | *EMNLP 2025 (Main)* | [Code](https://github.com/Zillwang/StepSearch) |
| 2025.05 | [R1‑Searcher++: Incentivizing the Dynamic Knowledge Acquisition of LLMs via Reinforcement Learning](https://arxiv.org/abs/2505.17005) | Search Efficiency | *arXiv* | [Code](https://github.com/RUCAIBox/R1-Searcher-plus) |
| 2025.05 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) | Search Efficiency | *arXiv* | [Code](https://github.com/Alibaba-NLP/ZeroSearch) |
| 2025.04 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) | Search Efficiency | *NeurIPS 2025* | [Code](https://github.com/RUC-NLPIR/WebThinker) |
| 2025.04 | [ReZero: Enhancing LLM Search Ability by Trying One‑More‑Time](https://arxiv.org/abs/2504.11001) | Search Intensity | *arXiv* | [Code](https://github.com/janhq/ReZero) |
| 2025.04 | [DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real‑World Environments](https://arxiv.org/abs/2504.03160) | Adaptive Search Decision; Search Efficiency; Context & Memory Management | *arXiv* | [Code](https://github.com/GAIR-NLP/DeepResearcher) |
| 2025.04 | [Synthetic Data Generation & Multi-Step RL for Reasoning & Tool Use](https://arxiv.org/abs/2504.04736) | Adaptive Search Decision; Reasoning-Search Interaction | *arXiv* |  |
| 2025.03 | [Learning to Reason with Search for LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.19470) | Adaptive Search Decision | *NeurIPS 2025* |  |
| 2025.03 | [Search‑R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](https://arxiv.org/abs/2503.09516) | Adaptive Search Decision | *COLM 2025* | [Code](https://github.com/PeterGriffinJin/Search-R1) |
| 2025.03 | [R1‑Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.05592) | Adaptive Search Decision | *arXiv* | [Code](https://github.com/RUCAIBox/R1-Searcher) |
| 2025.02 | [DeepRAG: Thinking to Retrieve Step by Step for Large Language Models](https://arxiv.org/abs/2502.01142) | Adaptive Search Decision; Search Efficiency | *arXiv* |  |


#### Query Optimization
| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.1 | [SmartSearch: Process Reward-Guided Query Refinement for Search Agents](https://arxiv.org/abs/2601.04888) | Retriever‑Aware Optimization; Query Refinement | *arXiv* | [Code](https://github.com/RUC-NLPIR/SmartSearch) |
| 2026.1 | [When should I search more: Adaptive Complex Query Optimization with Reinforcement Learning](https://arxiv.org/abs/2601.21208) | Retriever‑Aware Optimization; Query Reformulation | *arXiv* |  |
| 2025.11 | [CriticSearch: Fine-Grained Credit Assignment for Search Agents via a Retrospective Critic](https://arxiv.org/abs/2511.12159) | Retriever‑Aware Optimization | *arXiv* |  |
| 2025.09 | [WebExplorer: Explore and Evolve for Training Long‑Horizon Web Agents](https://arxiv.org/abs/2509.06501) | Context & Memory Management; Convsational Reformulation | *arXiv* |  |
| 2025.08 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner‑Executor Architecture for Reasoning‑Oriented Multi‑Hop Retrieval](https://arxiv.org/abs/2508.16438) | Planner-Executor Orchestration | *arXiv* |  |
| 2025.08 | [ParallelSearch: Train Your LLMs to Decompose Query and Search Sub‑Queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) | Search Efficiency | *arXiv* |  |
| 2025.07 | [RAG‑R1: Incentivizing the Search and Reasoning Capabilities of LLMs through Multi‑Query Parallelism](https://arxiv.org/abs/2507.02962) | Search Efficiency; Convsational Reformulation | *arXiv* | [Code](https://github.com/inclusionAI/AWorld-RL/tree/main/RAG-R1) |
| 2025.05 | [ConvSearch‑R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning](https://arxiv.org/abs/2505.15776) | Convsational Reformulation | *arXiv* |  |
| 2025.05 | [MaskSearch: A Universal Pre‑Training Framework to Enhance Agentic Search Capability](https://arxiv.org/abs/2505.20285) | Convsational Reformulation; Reasoning-Search Interaction | *arXiv* |  |
| 2025.05 | [s3: You Don’t Need That Much Data to Train a Search Agent via RL](https://arxiv.org/abs/2505.14146) | Retriever‑Aware Optimization | *EMNLP 2025 (Main)* | [code](https://github.com/pat-jj/s3) |
| 2025.05 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) | Search Efficiency | *arXiv* | [Code](https://github.com/Alibaba-NLP/ZeroSearch) |
| 2025.04 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) | Search Efficiency | *NeurIPS 2025* | [Code](https://github.com/RUC-NLPIR/WebThinker) |
| 2025.03 | [DeepRetrieval: Hacking Real Search Engines and Retrievers with Large Language Models via Reinforcement Learning](https://arxiv.org/abs/2503.00223) | Retriever‑Aware Optimization | *COLM 2025* | [Code](https://github.com/pat-jj/DeepRetrieval) |
| 2025.01 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | Cooperative Multi-Agent Systems | *NeurIPS 2025* | [Code](https://github.com/chenyiqun/MMOA-RAG) |
| 2024.10 | [DeepNote: Note-Centric Deep Retrieval-Augmented Generation](https://arxiv.org/abs/2410.08821) | Conversational Reformulation; Context & Memory Management | *EMNLP 2025 (Findings)* |  |

#### Reasoning–Retrieval Integration
| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.3 | [Evaluate-as-Action: Self-Evaluated Process Rewards for Retrieval-Augmented Agents](https://arxiv.org/abs/2603.09203) | Reasoning-Search Interaction; Process Supervision | *arXiv* |  |
| 2026.3 | [SE-Search: Self-Evolving Search Agent via Memory and Dense Reward](https://arxiv.org/abs/2603.03293) | Reasoning-Search Interaction; Context & Memory Management | *arXiv* |  |
| 2026.2 | [Search-P1: Path-Centric Reward Shaping for Stable and Efficient Agentic RAG Training](https://arxiv.org/abs/2602.22576) | Reasoning-Search Interaction; Reward Shaping | *arXiv* |  |
| 2026.1 | [ProRAG: Process-Supervised Reinforcement Learning for Retrieval-Augmented Generation](https://arxiv.org/abs/2601.21912) | Reasoning-Search Interaction; Process Supervision | *arXiv* | [Code](https://github.com/lilinwz/ProRAG) |
| 2026.1 | [Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards](https://arxiv.org/abs/2601.06021) | Reasoning-Search Interaction; Faithfulness / Citation Reward | *arXiv* | [Code](https://github.com/THUDM/CaRR) |
| 2026.1 | [D$^2$Plan: Dual-Agent Dynamic Global Planning for Complex Retrieval-Augmented Reasoning](https://arxiv.org/abs/2601.08282) | Reasoning-Search Interaction; Context Condensation (Purifier) | *arXiv* |  |
| 2026.1 | [TreePS-RAG: Tree-based Process Supervision for Reinforcement Learning in Agentic RAG](https://arxiv.org/abs/2601.06922) | Reasoning-Search Interaction; Process Supervision | *arXiv* |  |
| 2025.11 | [TeaRAG: A Token-Efficient Agentic Retrieval-Augmented Generation Framework](https://arxiv.org/abs/2511.05385) | Search Efficiency; Reasoning-Search Interaction | *arXiv* | [Code](https://github.com/Applied-Machine-Learning-Lab/TeaRAG) |
| 2025.10 | [GlobalRAG: Enhancing Global Reasoning in Multi-hop Question Answering via Reinforcement Learning](https://arxiv.org/abs/2510.20548) | Reasoning-Search Interaction; Retriever‑Aware Optimization | *arXiv* | [Code](https://github.com/CarnegieBin/GlobalRAG) |
| 2025.10 | [RECON: Reasoning with Condensation for Efficient Retrieval‑Augmented Generation](https://arxiv.org/abs/2510.10448) | Context & Memory Management | *arXiv* |  |
| 2025.10 | [Search Self-play: Pushing the Frontier of Agent Capability without Supervision](https://arxiv.org/abs/2510.18821) | Adaptive Search Decision; Self-Play Training | *arXiv* | [Code](https://github.com/Alibaba-Quark/SSP) |
| 2025.09 | [AceSearcher: Bootstrapping Reasoning and Search for LLMs via Reinforced Self-Play](https://arxiv.org/abs/2509.24193) | Reasoning-Search Interaction; Self-Play Training | *arXiv* | [Code](https://github.com/ritaranx/AceSearcher) |
| 2025.09 | [ReSum: Unlocking Long‑Horizon Search Intelligence via Context Summarization](https://arxiv.org/abs/2509.13313) | Context & Memory Management | *arXiv* |  |
| 2025.09 | [SFR‑DeepResearch: Towards Effective Reinforcement Learning for Autonomously Reasoning Single Agents](https://arxiv.org/abs/2509.06283) | Context & Memory Management; Multi‑Tool | *arXiv* |  |
| 2025.08 | [Atom‑Searcher: Enhancing Agentic Deep Research via Fine‑Grained Atomic Thought Reward](https://arxiv.org/abs/2508.12800) | Reasoning-Search Interaction | *arXiv* | [Code](https://github.com/antgroup/Research-Venus) |
| 2025.08 | [Beyond Ten Turns: Unlocking Long‑Horizon Agentic Search with Large‑Scale Asynchronous RL](https://arxiv.org/abs/2508.07976) | Reasoning-Search Interaction; Retriever‑Aware Optimization | *arXiv* |  |
| 2025.07 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) | Structured Knowledge Navigation | *arXiv* |  |
| 2025.07 | [WebSailor: Navigating Super‑Human Reasoning for Web Agent](https://arxiv.org/abs/2507.02592) | Adaptive Search Decision; Context & Memory Management | *arXiv* |  |
| 2025.06 | [R‑Search: Empowering LLM Reasoning with Search via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2506.04185) | Reasoning-Search Interaction | *arXiv* |  |
| 2025.05 | [Search and Refine During Think: Facilitating Knowledge Refinement for Improved Retrieval-Augmented Reasoning](https://arxiv.org/abs/2505.11277) | Reasoning-Search Interaction | *NeurIPS 2025* | [Code](https://github.com/syr-cn/AutoRefine) |
| 2025.05 | [EvolveSearch: An Iterative Self‑Evolving Search Agent](https://arxiv.org/abs/2505.22501) | Reasoning-Search Interaction | *arXiv* |  |
| 2025.05 | [O²‑Searcher: A Searching‑Based Agent Model for Open‑Domain Open‑Ended Question Answering](https://arxiv.org/abs/2505.16582) | Reasoning-Search Interaction | *arXiv* | [Code](https://github.com/KnowledgeXLab/O2-Searcher) |
| 2025.05 | [Process vs. Outcome Reward: Which Is Better for Agentic RAG Reinforcement Learning](https://arxiv.org/abs/2505.14069) | Reasoning‑Search Interaction; Retriever‑Aware Optimization | *NeurIPS 2025* | [Code](https://github.com/Applied-Machine-Learning-Lab/ReasonRAG) |
| 2025.04 | [DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real‑World Environments](https://arxiv.org/abs/2504.03160) | Context & Memory Management | *arXiv* |  |
| 2025.04 | [Synthetic Data Generation & Multi-Step RL for Reasoning & Tool Use](https://arxiv.org/abs/2504.04736) | Reasoning‑Search Interaction | *arXiv* |  |
#### Multi‑Agent Collaboration
| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.1 | [PRISMA: Reinforcement Learning Guided Two-Stage Policy Optimization in Multi-Agent Architecture for Open-Domain Multi-Hop Question Answering](https://arxiv.org/abs/2601.05465) | Planner-Executor Orchestration | *arXiv* |  |
| 2025.10 | [In-the-Flow Agentic System Optimization for Effective Planning and Tool Use](https://arxiv.org/abs/2510.05592) | Planner-Executor Orchestration; Multi‑Tool | *arXiv* | [Code](https://github.com/lupantech/AgentFlow) [Project page](https://agentflow.stanford.edu/) |
| 2025.09 | [AgentGym‑RL: Training LLM Agents for Long‑Horizon Decision Making through Multi‑Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755) | Cooperative Multi-Agent Systems; Multi‑Tool | *arXiv* |  |
| 2025.09 | [SIRAG: Towards Stable and Interpretable RAG with a Process‑Supervised Multi‑Agent Framework](https://arxiv.org/abs/2509.18167) | Cooperative Multi-Agent Systems | *arXiv* |  |
| 2025.09 | [WebExplorer: Explore and Evolve for Training Long‑Horizon Web Agents](https://arxiv.org/abs/2509.06501) | Context & Memory Management; Convsational Reformulation | *arXiv* |  |
| 2025.08 | [AI‑SearchPlanner: Modular Agentic Search via Pareto‑Optimal Multi‑Objective Reinforcement Learning](https://arxiv.org/abs/2508.20368) | Planner-Executor Orchestration | *arXiv* |  |
| 2025.08 | [Chain‑of‑Agents: End‑to‑End Agent Foundation Models via Multi‑Agent Distillation and Agentic RL](https://arxiv.org/abs/2508.13167) | Cooperative Multi-Agent Systems; Multi‑Tool | *arXiv* |  |
| 2025.08 | [MAO‑ARAG: Multi‑Agent Orchestration for Adaptive Retrieval‑Augmented Generation](https://arxiv.org/abs/2508.01005) | Planner-Executor Orchestration | *arXiv* |  |
| 2025.08 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner‑Executor Architecture for Reasoning‑Oriented Multi‑Hop Retrieval](https://arxiv.org/abs/2508.16438) | Planner-Executor Orchestration | *arXiv* |  |
| 2025.05 | [Advancing Multi-Agent RAG Systems with Minimalist Reinforcement Learning](https://arxiv.org/abs/2505.17086) | Cooperative Multi-Agent Systems | *arXiv* |  |
| 2025.01 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | Cooperative Multi-Agent Systems | *NeurIPS 2025* | [Code](https://github.com/chenyiqun/MMOA-RAG) |

#### Tool and Knowledge Integration
| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.3 | [SynPlanResearch-R1: Encouraging Tool Exploration for Deep Research with Synthetic Plans](https://arxiv.org/abs/2603.07853) | Multi‑Tool; Adaptive Search Decision | *arXiv* | [Code](https://github.com/HansiZeng/syn-plan-research) |
| 2026.3 | [VSearcher: Long-Horizon Multimodal Search Agent via Reinforcement Learning](https://arxiv.org/abs/2603.02795) | Multi‑Tool; Multi‑Modal | *arXiv* |  |
| 2026.3 | [MM-DeepResearch: A Simple and Effective Multimodal Agentic Search Baseline](https://arxiv.org/abs/2603.01050) | Multi‑Tool; Multi‑Modal | *arXiv* | [Code](https://github.com/HJYao00/MM-DeepResearch) |
| 2026.2 | [ARLArena: A Unified Framework for Stable Agentic Reinforcement Learning](https://arxiv.org/abs/2602.21534) | Unified Agentic RL Framework; Stability | *arXiv* |  |
| 2026.2 | [Reasoning and Tool-use Compete in Agentic RL:From Quantifying Interference to Disentangled Tuning](https://arxiv.org/abs/2602.00994) | Agentic RL Training Dynamics (Reasoning–Tool Interference) | *arXiv* |  |
| 2026.1 | [OpenTinker: Separating Concerns in Agentic Reinforcement Learning](https://arxiv.org/abs/2601.07376) | Unified Agentic RL Framework | *arXiv* |  |
| 2026.1 | [SCRIBE: Structured Mid-Level Supervision for Tool-Using Language Models](https://arxiv.org/abs/2601.03555) | Multi‑Tool; Mid‑Level Reward Modeling (Skill Prototypes) | *arXiv* |  |
| 2026.1 | [AT$^2$PO: Agentic Turn-based Policy Optimization via Tree Search](https://arxiv.org/abs/2601.04767) | Multi‑Turn Agentic RL; Credit Assignment | *arXiv* | [Code](https://github.com/zzfoutofspace/ATPO) |
| 2026.1 | [PEARL: Plan Exploration and Adaptive Reinforcement Learning for Multihop Tool Use](https://arxiv.org/abs/2601.20439) | Multi‑Tool; Planner‑Executor Orchestration | *PRICAI 2025* |  |
| 2025.12 | [CARL: Focusing Agentic Reinforcement Learning on Critical Actions](https://arxiv.org/abs/2512.04949) | Credit Assignment for Multi‑Step Tool Use | *arXiv* |  |
| 2025.12 | [On Group Relative Policy Optimization Collapse in Agent Search: The Lazy Likelihood-Displacement](https://arxiv.org/abs/2512.04220) | Training Stability (GRPO) | *arXiv* |  |
| 2025.12 | [RouteRAG: Efficient Retrieval-Augmented Generation from Text and Graph via Reinforcement Learning](https://arxiv.org/abs/2512.09487) | Structured Knowledge Navigation; Multi‑Tool | *arXiv* | [Code](https://github.com/YucanGuo/RouteRAG) |
| 2025.12 | [CuES: A Curiosity-driven and Environment-grounded Synthesis Framework for Agentic RL](https://arxiv.org/abs/2512.01311) | Task / Curriculum Synthesis for Agentic RL (tool environments) | *arXiv* | [Code](https://github.com/modelscope/AgentEvolver/tree/main/research/CuES) |
| 2025.12 | [SenseNova-MARS: Empowering Multimodal Agentic Reasoning and Search via Reinforcement Learning](https://arxiv.org/abs/2512.24330) | Multi‑Tool; Multi‑Modal | *arXiv* |  |
| 2025.11 | [Agent‑R1: Training Powerful LLM Agents with End‑to‑End Reinforcement Learning](https://arxiv.org/abs/2511.14460) | Multi‑Tool | *arXiv* | [Code (community)](https://github.com/AgentR1/Agent-R1) |
| 2025.10 | [MARAG-R1: Beyond Single Retriever via Reinforcement-Learned Multi-Tool Agentic Retrieval](https://arxiv.org/abs/2510.27569) | Multi‑Tool; Retriever‑Aware Optimization | *arXiv* |  |
| 2025.09 | [Empowering LLM Tool Invocation with Tool-call Reward Model](https://openreview.net/forum?id=LnBEASInVr) | Multi‑Tool | *ICLR 2026 Submission* |  |
| 2025.09 | [VerlTool: Towards Holistic Agentic Reinforcement Learning with Tool Use](https://arxiv.org/abs/2509.01055) | Multi‑Tool | *arXiv* | [Code](https://github.com/TIGER-AI-Lab/verl-tool) |
| 2025.09 | [WebResearcher: Unleashing unbounded reasoning capability in Long‑Horizon Agents](https://arxiv.org/abs/2509.13309) | Multi‑Tool | *arXiv* | [Code](https://github.com/Alibaba-NLP/DeepResearch) |
| 2025.08 | [GRAIL: Learning to Interact with Large Knowledge Graphs for Retrieval‑Augmented Reasoning](https://arxiv.org/abs/2508.05498) | Adaptive Search Decision; Structured Knowledge Navigation | *arXiv* | [Code](https://github.com/Changgeww/GRAIL) |
| 2025.08 | [MedResearcher‑R1: Expert‑Level Medical Deep Researcher via a Knowledge‑Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) | Adaptive Search Decision; Multi‑Tool | *arXiv* | [Code](https://github.com/AQ-MedAI/MedResearcher-R1) |
| 2025.08 | [WebWatcher: Breaking New Frontier of Vision‑Language Deep Research Agent](https://arxiv.org/abs/2508.05748) | Multi‑Tool; Multi‑Modal | *arXiv* |  |
| 2025.07 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) | Structured Knowledge Navigation | *arXiv* |  |
| 2025.06 | [MMSearch‑R1: Incentivizing LMMs to Search](https://arxiv.org/abs/2506.20670) | Multi‑Modal; Search Efficiency | *arXiv* | [Code](https://github.com/EvolvingLMMs-Lab/multimodal-search-r1) |
| 2025.05 | [VRAG‑RL: Empower Vision‑Perception‑Based RAG for Visually Rich Information Understanding via Iterative Reasoning with RL](https://arxiv.org/abs/2505.22019) | Multi‑Modal; Search Efficiency | *arXiv* |  |
| 2025.05 | [Tool‑Star: Empowering LLM‑Brained Multi‑Tool Reasoner via Reinforcement Learning](https://arxiv.org/abs/2505.16410) | Multi‑Tool | *arXiv* | [Code](https://github.com/RUC-NLPIR/Tool-Star) |
| 2025.05 | [Visual Agentic Reinforcement Fine‑Tuning](https://arxiv.org/abs/2505.14246) | Multi‑Modal; Multi‑Tool; Adaptive Search Decision | *arXiv* | [Code](https://github.com/Liuziyu77/Visual-RFT/tree/main/Visual-ARFT) |

### Where RL is Applied: Optimization Scopes

#### Agent-level
<details>
<summary>📊 Click to expand long table (scrollable). </summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">

| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.3 | [APEX-Searcher: Augmenting LLMs' Search Capabilities through Agentic Planning and Execution](https://arxiv.org/abs/2603.13853) | Single-agent Optimization | *arXiv* |  |
| 2026.3 | [Meta-Reinforcement Learning with Self-Reflection for Agentic Search](https://arxiv.org/abs/2603.11327) | Single-agent Optimization | *arXiv* | [Code](https://github.com/tengxiao1/MR-Search) |
| 2026.3 | [Search More, Think Less: Rethinking Long-Horizon Agentic Search for Efficiency and Generalization](https://arxiv.org/abs/2602.22675) | Single-agent Optimization | *arXiv* | [Code](https://github.com/OPPO-PersonalAI/SMTL) |
| 2026.3 | [SynPlanResearch-R1: Encouraging Tool Exploration for Deep Research with Synthetic Plans](https://arxiv.org/abs/2603.07853) | Single-agent Optimization | *arXiv* | [Code](https://github.com/HansiZeng/syn-plan-research) |
| 2026.3 | [VSearcher: Long-Horizon Multimodal Search Agent via Reinforcement Learning](https://arxiv.org/abs/2603.02795) | Single-agent Optimization | *arXiv* |  |
| 2026.3 | [MM-DeepResearch: A Simple and Effective Multimodal Agentic Search Baseline](https://arxiv.org/abs/2603.01050) | Single-agent Optimization | *arXiv* | [Code](https://github.com/HJYao00/MM-DeepResearch) |
| 2025.11 | [Thinker: Training LLMs in Hierarchical Thinking for Deep Search via Multi-Turn Interaction](https://arxiv.org/abs/2511.07943) | Single-agent Optimization | *AAAI 2026* | [Code](https://github.com/OpenSPG/KAG-Thinker) |
| 2025.11 | [MemSearcher: Training LLMs to Reason, Search and Manage Memory via End-to-End Reinforcement Learning](https://arxiv.org/abs/2511.02805) | Single-agent Optimization | *arXiv* | [Code](https://github.com/icip-cas/MemSearcher) |
| 2025.09 | [DeepDive: Advancing Deep Search Agents with Knowledge Graphs and Multi-Turn RL](https://arxiv.org/abs/2509.10446) | Single-agent Optimization | *arXiv* | [Code](https://github.com/THUDM/DeepDive) |
| 2025.09 | [SFR-DeepResearch: Towards Effective Reinforcement Learning for Autonomously Reasoning Single Agents](https://arxiv.org/abs/2509.06283) | Single-agent Optimization | *arXiv* |  |
| 2025.09 | [WebExplorer: Explore and evolve for training long-horizon web agents](https://arxiv.org/abs/2509.06501) | Single-agent Optimization | *arXiv* |  |
| 2025.09 | [WebResearcher: Unleashing unbounded reasoning capability in Long-Horizon Agents](https://arxiv.org/abs/2509.13309) | Single-agent Optimization | *arXiv* |  |
| 2025.09 | [AgentGym-RL: Training LLM Agents for Long-Horizon Decision Making through Multi-Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755) | Single-agent Optimization | *arXiv* |  |
| 2025.09 | [WebSailor-V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable Reinforcement Learning](https://arxiv.org/abs/2509.13305) | Single-agent Optimization | *arXiv* | [Code](https://github.com/Alibaba-NLP/DeepResearch) |
| 2025.6 | [MMSearch-R1: Incentivizing LMMs to Search](https://arxiv.org/abs/2506.20670) | Single-agent Optimization | *arXiv* | [Code](https://github.com/EvolvingLMMs-Lab/multimodal-search-r1) |
| 2025.08 | [MedResearcher-R1: Expert-Level Medical Deep Researcher via A Knowledge-Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) | Single-agent Optimization | *arXiv* | [Code](https://github.com/AQ-MedAI/MedResearcher-R1) |
| 2025.08 | [WebWatcher: Breaking New Frontier of Vision-Language Deep Research Agent](https://arxiv.org/abs/2508.05748) | Single-agent Optimization | *arXiv* |  |
| 2025.08 | [GRAIL: Learning to interact with large knowledge graphs for retrieval-augmented reasoning](https://arxiv.org/abs/2508.05498) | Single-agent Optimization | *arXiv* | [Code](https://github.com/Changgeww/GRAIL) |
| 2025.5 | [VRAG-RL: Empower Vision-Perception-Based RAG for Visually Rich Information Understanding via Iterative Reasoning with Reinforcement Learning](https://arxiv.org/abs/2505.22019) | Single-agent Optimization | *arXiv* |  |
| 2025.5 | [Visual Agentic Reinforcement Fine-Tuning](https://arxiv.org/abs/2505.14246) | Single-agent Optimization | *arXiv* | [Code](https://github.com/Liuziyu77/Visual-RFT/tree/main/Visual-ARFT) |
| 2025.7 | [WebSailor: Navigating Super-Human Reasoning for Web Agent](https://arxiv.org/abs/2507.02592) | Single-agent Optimization | *arXiv* |  |
| 2025.08 | [ParallelSearch: Train your LLMs to Decompose Query and Search Sub-queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) | Single-agent Optimization | *arXiv* |  |
| 2025.08 | [UR2: Unify RAG and Reasoning through Reinforcement Learning](https://arxiv.org/abs/2508.06165) | Single-agent Optimization | *arXiv* | [Code](https://github.com/Tsinghua-dhy/UR2) |
| 2025.08 | [SSRL: Self-Search Reinforcement Learning](https://arxiv.org/abs/2508.10874) | Single-agent Optimization | *arXiv* | [Code](https://github.com/TsinghuaC3I/SSRL) |
| 2025.7 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi-Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) | Single-agent Optimization | *arXiv* |  |
| 2025.6 | [R-Search: Empowering LLM Reasoning with Search via Multi-Reward Reinforcement Learning](https://arxiv.org/abs/2506.04185) | Single-agent Optimization | *arXiv* |  |
| 2025.5 | [EvolveSearch: An Iterative Self-Evolving Search Agent](https://arxiv.org/abs/2505.22501) | Single-agent Optimization | *arXiv* |  |
| 2025.5 | [O2-Searcher: a searching-based agent model for open-domain open-ended question answering](https://arxiv.org/abs/2505.16582) | Single-agent Optimization | *arXiv* | [Code](https://github.com/KnowledgeXLab/O2-Searcher) |
| 2025.5 | [DeepDiver: Adaptive Search Intensity Scaling via Open-Web Reinforcement Learning](https://arxiv.org/abs/2505.24332) | Single-agent Optimization | *NeurIPS 2025 (Spotlight)* |  |
| 2025.05 | [Reinforced Internal-External Knowledge Synergistic Reasoning for Efficient Adaptive Search Agent](https://arxiv.org/abs/2505.07596) | Single-agent Optimization | *arXiv* |  |
| 2025.5 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) | Single-agent Optimization | *arXiv* | [Code](https://github.com/Alibaba-NLP/ZeroSearch) |
| 2025.5 | [MaskSearch: A Universal Pre-Training Framework to Enhance Agentic Search Capability](https://arxiv.org/abs/2505.20285) | Single-agent Optimization | *arXiv* |  |
| 2025.4 | [ReZero: Enhancing LLM Search Ability by Trying One-More-Time](https://arxiv.org/abs/2504.11001) | Single-agent Optimization | *arXiv* | [Code](https://github.com/janhq/ReZero) |
| 2025.5 | [Tool-Star: Empowering LLM-Brained Multi-Tool Reasoner via Reinforcement Learning](https://arxiv.org/abs/2505.16410) | Single-agent Optimization | *arXiv* | [Code](https://github.com/RUC-NLPIR/Tool-Star) |
| 2025.3 | [DeepRetrieval: Hacking Real Search Engines and Retrievers with Large Language Models via Reinforcement Learning](https://arxiv.org/abs/2503.00223) | Single-agent Optimization | *COLM 2025* | [Code](https://github.com/pat-jj/DeepRetrieval) |
| 2025.4 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) | Single-agent Optimization | *NeurIPS 2025* | [Code](https://github.com/RUC-NLPIR/WebThinker) |
| 2025.05 | [Search Wisely: Mitigating Sub-optimal Agentic Searches By Reducing Uncertainty](https://arxiv.org/abs/2505.17281) | Single-agent Optimization | *EMNLP 2025 (Main)* |  |
| 2025.4 | [DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments](https://arxiv.org/abs/2504.03160) | Single-agent Optimization | *arXiv* | [Code](https://github.com/GAIR-NLP/DeepResearcher) |
| 2025.3 | [Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](https://arxiv.org/abs/2503.09516) | Single-agent Optimization | *COLM 2025* | [Code](https://github.com/PeterGriffinJin/Search-R1) |
| 2025.3 | [ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.19470) | Single-agent Optimization | *NeurIPS 2025* |  |
| 2025.05 | [R1-Searcher++: Incentivizing the dynamic knowledge acquisition of llms via reinforcement learning](https://arxiv.org/abs/2505.17005) | Single-agent Optimization | *arXiv* | [Code](https://github.com/RUCAIBox/R1-Searcher-plus) |
| 2025.3 | [Agent models: Internalizing Chain-of-Action Generation into Reasoning models](https://arxiv.org/abs/2503.06580) | Single-agent Optimization | *arXiv* | [Code](https://github.com/ADaM-BJTU/AutoCoA) |
| 2025.08 | [Lucy: edgerunning agentic web search on mobile with machine generated task vectors](https://arxiv.org/abs/2508.00360) | Single-agent Optimization | *arXiv* |  |
| 2025.2 | [DeepRAG: Thinking to Retrieve Step by Step for Large Language Models](https://arxiv.org/abs/2502.01142) | Single-agent Optimization | *arXiv* |  |
| 2025.5 | [StepSearch: Igniting LLMs Search Ability via Step-Wise Proximal Policy Optimization](https://arxiv.org/abs/2505.15107) | Single-agent Optimization | *EMNLP 2025 (Main)* | [Code](https://github.com/Zillwang/StepSearch) |
| 2025.1 | [Improving Retrieval-Augmented Generation through Multi-Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | Multi-agent Coordination | *NeurIPS 2025* | [Code](https://github.com/chenyiqun/MMOA-RAG) |
| 2025.06 | [Coordinating Search-Informed Reasoning and Reasoning-Guided Search in Claim Verification](https://arxiv.org/abs/2506.07528) | Multi-agent Coordination | *arXiv* |  |
| 2025.9 | [SIRAG: Towards Stable and Interpretable RAG with a Process-Supervised Multi-Agent Framework](https://arxiv.org/abs/2509.18167) | Multi-agent Coordination | *arXiv* |  |
| 2025.8 | [MAO-ARAG: Multi-Agent Orchestration for Adaptive Retrieval-Augmented Generation](https://arxiv.org/abs/2508.01005) | Multi-agent Coordination | *arXiv* |  |
| 2025.1 | [MMOA-RAG: Improving Retrieval-Augmented Generation through Multi-Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | Multi-agent Coordination | *NeurIPS 2025* | [Code](https://github.com/chenyiqun/MMOA-RAG) |
| 2025.8 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner-Executor Architecture for Reasoning-Oriented Multi-Hop Retrieval](https://arxiv.org/abs/2508.16438) | Multi-agent Coordination | *arXiv* |  |
| 2025.02 | [DeepRAG: Thinking to Retrieval Step by Step for Large Language Models](https://arxiv.org/abs/2502.01142) | Single‑agent Optimization | *arXiv* |  |
| 2025.01 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | Multi‑agent Coordination | *NeurIPS 2025* | [Code](https://github.com/chenyiqun/MMOA-RAG) |
| 2024.10 | [DeepNote: Note-Centric Deep Retrieval-Augmented Generation](https://arxiv.org/abs/2410.08821) | Single‑agent Optimization | *EMNLP 2025 (Findings)* |  |
</div>
</details>

#### Step-level
<details>
<summary>📊 Click to expand long table (scrollable). </summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">

| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2026.3 | [Evaluate-as-Action: Self-Evaluated Process Rewards for Retrieval-Augmented Agents](https://arxiv.org/abs/2603.09203) | Step‑level Optimization | *arXiv* |  |
| 2026.2 | [Search-P1: Path-Centric Reward Shaping for Stable and Efficient Agentic RAG Training](https://arxiv.org/abs/2602.22576) | Step‑level Optimization | *arXiv* |  |
| 2025.10 | [Beyond Correctness: Rewarding Faithful Reasoning in Retrieval‑Augmented Generation](https://arxiv.org/abs/2510.13272) | Step‑level Optimization | *arXiv* |  |
| 2025.08 | [Atom‑Searcher: Enhancing Agentic Deep Research via Fine‑Grained Atomic Thought Reward](https://arxiv.org/abs/2508.12800) | Step‑level Optimization | *arXiv* | [Code](https://github.com/antgroup/Research-Venus) |
| 2025.05 | [StepSearch: Igniting LLMs Search Ability via Step-Wise Proximal Policy Optimization](https://arxiv.org/abs/2505.15107) | Step‑level Optimization | *EMNLP 2025* | [Code](https://github.com/Zillwang/StepSearch) |
| 2025.05 | [Process vs. Outcome Reward: Which Is Better for Agentic RAG Reinforcement Learning](https://arxiv.org/abs/2505.14069) | Step‑level Optimization | *NeurIPS 2025* | [Code](https://github.com/Applied-Machine-Learning-Lab/ReasonRAG) |
| 2025.05 | [Search and Refine During Think: Facilitating Knowledge Refinement for Improved Retrieval-Augmented Reasoning](https://arxiv.org/abs/2505.11277) | Step‑level Optimization | *NeurIPS 2025* | [Code](https://github.com/syr-cn/AutoRefine) |
| 2025.05 | [ConvSearch‑R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning](https://arxiv.org/abs/2505.15776) | Step‑level Optimization | *arXiv* |  |
| 2025.05 | [Reinforced Internal‑External Knowledge Synergistic Reasoning for Efficient Adaptive Search Agent](https://arxiv.org/abs/2505.07596) | Step‑level Optimization | *arXiv* |  |
| 2025.04 | [ReZero: Enhancing LLM Search Ability by Trying One‑More‑Time](https://arxiv.org/abs/2504.11001) | Step‑level Optimization | *arXiv* | [Code](https://github.com/janhq/ReZero) |
| 2025.04 | [Synthetic Data Generation & Multi-Step RL for Reasoning & Tool Use](https://arxiv.org/abs/2504.04736) | Step‑level Optimization | *arXiv* |  |
</div>
</details>

#### Module-level
<details>
<summary>📊 Click to expand long table (scrollable). </summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">

| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2025.08 | [AI-SearchPlanner: Modular Agentic Search via Pareto-Optimal Multi-Objective Reinforcement Learning](https://arxiv.org/abs/2508.20368) | Module-level Optimization | *arXiv* |  |
| 2025.05 | [s3: You Don’t Need That Much Data to Train a Search Agent via RL](https://arxiv.org/abs/2505.14146) | Module-level Optimization | *arXiv* |  |
| 2025.04 | [Deepresearcher: Scaling deep research via reinforcement learning in real-world environments](https://arxiv.org/abs/2504.03160) | Module-level Optimization | *arXiv* | [Code](https://github.com/GAIR-NLP/DeepResearcher) |
</div>
</details>

#### System-level
<details>
<summary>📊 Click to expand long table (scrollable). </summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">
  
| Time | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2025.09 | [AgentGym‑RL: Training LLM Agents for Long‑Horizon Decision Making through Multi‑Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755) | Unified RL‑based Agentic Framework | *arXiv* |  |
| 2025.09 | [VerlTool: Towards Holistic Agentic Reinforcement Learning with Tool Use](https://arxiv.org/abs/2509.01055) | Unified RL‑based Agentic Framework | *arXiv* |  |
| 2025.08 | [Chain‑of‑Agents: End‑to‑End Agent Foundation Models via Multi‑Agent Distillation and Agentic RL](https://arxiv.org/abs/2508.13167) | Unified RL‑based Agentic Framework | *arXiv* |  |
| 2025.02 | [RAG‑Gym: Systematic Optimization of Language Agents for Retrieval‑Augmented Generation](https://arxiv.org/abs/2502.13957) | Unified RL‑based Agentic Framework | *arXiv* |  |
| 2024.09 | [HybridFlow: A Flexible and Efficient RLHF Framework](https://arxiv.org/abs/2409.19256) | Unified RL‑based Agentic Framework (Verl) | *arXiv* |  |
</div>
</details>

## Evaluation
### Metrics
Below is a compact checklist of commonly used evaluation signals for RL-based agentic search (see the survey for details):

- **Answer quality (final output)**: Exact Match (EM), token-level F1, and *LLM-as-a-judge* scores for open-ended outputs (e.g., used by [Search-R1](https://arxiv.org/abs/2503.09516), [ReZero](https://arxiv.org/abs/2504.11001)).  
  - Similarity-based metrics (e.g., [BERTScore](https://arxiv.org/abs/1904.09675)) are also used for more free-form generations.
- **Search effectiveness (retrieval / evidence)**: retrieval relevance/coverage metrics (e.g., Recall@k / Precision@k / nDCG) and evidence usefulness; some works explicitly optimize or evaluate retrieval behavior (e.g., [DeepRetrieval](https://arxiv.org/abs/2503.00223)).
- **Search efficiency (cost / budget)**: number of search/tool calls, token/latency cost, and other explicit penalties/rewards (e.g., [Pangu DeepDiver](https://arxiv.org/abs/2505.24332), [MAO-ARAG](https://arxiv.org/abs/2508.01005), [R1-Searcher++](https://arxiv.org/abs/2505.17005)).
- **Process / trajectory quality (intermediate steps)**: step-wise correctness, information gain, redundancy penalties, and other process-level signals (often combined with a PRM or heuristic shaping; e.g., [StepSearch](https://arxiv.org/abs/2505.15107), [VERITAS](https://arxiv.org/abs/2510.13272), [ReasonRAG](https://arxiv.org/abs/2505.14069), [ConvSearch-R1](https://arxiv.org/abs/2505.15776)).
- **System-level benchmarks**: some benchmarks are designed specifically to evaluate deep-research style agents (e.g., [RAG-Gym](https://arxiv.org/abs/2502.13957)).

### Recent Evaluation / Benchmarking Papers (Deep Research / Agentic Search)
| Time | Paper Title | Focus | Venue |
| :---- | :----------- | :---- | :---- |
| 2026.3 | [DeepResearch-9K: A Challenging Benchmark Dataset of Deep-Research Agent](https://arxiv.org/abs/2603.01152) | Benchmark Dataset + Open Training Framework | *arXiv* |
| 2026.2 | [Revisiting Text Ranking in Deep Research](https://arxiv.org/abs/2602.21456) | Retriever / Ranker Analysis for Deep Research | *arXiv* |
| 2026.2 | [SAGE: Benchmarking and Improving Retrieval for Deep Research Agents](https://arxiv.org/abs/2602.05975) | Retrieval Benchmark + Strong Baselines | *arXiv* |
| 2026.2 | [W&D: Scaling Parallel Tool Calling for Efficient Deep Research Agents](https://arxiv.org/abs/2602.07359) | Parallel Tool Calling (Width) vs Turns (Depth) | *arXiv* |
| 2026.1 | [Agentic Search in the Wild: Intents and Trajectory Dynamics from 14M+ Real Search Requests](https://arxiv.org/abs/2601.17617) | Real‑World Agentic Search Logs / Trajectory Analysis | *arXiv* |

### Datasets
<!-- The survey groups evaluation datasets by the knowledge source and interaction setting:

<details>
<summary>📚 Click to expand dataset taxonomy table (from the survey). </summary> -->

| Category | Datasets |
|---|---|
| Knowledge Source | [wiki-dump](https://dumps.wikimedia.org/backup-index.html), [Common Crawl](https://commoncrawl.org/overview), [KILT](https://arxiv.org/abs/2009.02252), [PubMed](https://pubmed.ncbi.nlm.nih.gov/about/), [arXiv](https://info.arxiv.org/about/index.html) |
| Knowledge-Intensive QA | [NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [HotpotQA](https://arxiv.org/abs/1809.09600), [2WikiMultiHopQA](https://arxiv.org/abs/2011.01060), [MuSiQue](https://arxiv.org/abs/2108.00573), [PopQA](https://arxiv.org/abs/2212.10511), [CAG](https://aclanthology.org/2024.emnlp-main.1109/), [C-SimpleQA](https://arxiv.org/abs/2411.07140), [SuperGPQA](https://arxiv.org/abs/2502.14739)<br>[BRIGHT](https://arxiv.org/abs/2407.12883), [SealQA](https://arxiv.org/abs/2506.01062), [BLUR](https://arxiv.org/abs/2503.19193), [NaturalReasoning](https://arxiv.org/abs/2502.13124)<br>[FEVER](https://aclanthology.org/N18-1074/), [EX-FEVER](https://aclanthology.org/2024.findings-acl.556/), [FEVEROUS](https://arxiv.org/abs/2106.05707), [FactBench](https://arxiv.org/abs/2410.22257), [RealFactBench](https://arxiv.org/abs/2506.12538), [LongFact](https://arxiv.org/abs/2403.18802), [FRAMES](https://arxiv.org/abs/2409.12941), [RAG-Bench](https://arxiv.org/abs/2407.11005)<br>[BEIR](https://arxiv.org/abs/2104.08663), [AmbigQA](https://arxiv.org/abs/2004.10645), [MetaQA](https://arxiv.org/abs/1709.04071), [WebQuestions](https://aclanthology.org/D13-1160/), [CWQ](https://arxiv.org/abs/1803.06643), [CheckWhy](https://aclanthology.org/2024.acl-long.835/), [BeerQA](https://aclanthology.org/2021.emnlp-main.292/) |
| Web-based Search | [WebQA](https://arxiv.org/abs/2109.00590), [Bamboogle](https://arxiv.org/abs/2210.03350), [Mind2Web](https://arxiv.org/abs/2306.06070), [WebArena](https://arxiv.org/abs/2307.13854), [WebWalkerQA](https://arxiv.org/abs/2501.07572), [AgentBench](https://arxiv.org/abs/2308.03688)<br>[BrowseComp-en](https://arxiv.org/abs/2504.12516), [BrowseComp-zh](https://arxiv.org/abs/2504.19314), [GAIA](https://arxiv.org/abs/2311.12983), [GAIA-2](https://arxiv.org/abs/2602.11964), [XbenchDeepSearch](https://xbench.org/agi/aisearch)<br>[WebPuzzle](https://arxiv.org/abs/2505.24332), [InfoDeepSeek](https://arxiv.org/abs/2505.15872), [ORION](https://arxiv.org/abs/2505.18105), [WebShaperQA](https://arxiv.org/abs/2507.15061) |
| Multi-modal | [InfoSeek](https://arxiv.org/abs/2302.11713), [MMSearch](https://arxiv.org/abs/2409.12959), [MMSearch-Plus](https://arxiv.org/abs/2508.21475), [SimpleVQA](https://arxiv.org/abs/2502.13059), [LiveVQA](https://arxiv.org/abs/2504.05288), [MM-BrowseComp](https://arxiv.org/abs/2508.13186)<br>[MAT-Search](https://arxiv.org/abs/2505.14246), [Mocheg](https://arxiv.org/abs/2205.12487), [MFC-Bench](https://arxiv.org/abs/2406.11288), [ViDoSeek](https://arxiv.org/abs/2502.18017), [SlideVQA](https://arxiv.org/abs/2301.04883), [MMLongBench](https://arxiv.org/abs/2505.10610) |
| Conversational | [CoQA](https://arxiv.org/abs/1808.07042), [QuAC](https://arxiv.org/abs/1808.07036), [MSMarco](https://arxiv.org/abs/1611.09268), [TopiOCQA](https://aclanthology.org/2022.tacl-1.27/), [QReCC](https://aclanthology.org/2021.naacl-main.44/), [OR-QuAC](https://arxiv.org/abs/2005.11364), [NarrativeQA](https://aclanthology.org/Q18-1023/), [Doc2Dial](https://arxiv.org/abs/2011.06623) |
| Domain-specific | [MATH](https://arxiv.org/abs/2103.03874), [MATH500](https://huggingface.co/datasets/math-ai/math500), [AIME24](https://huggingface.co/datasets/AI-MO/aimo-validation-aime), [AIME25](https://huggingface.co/datasets/math-ai/aime25), [GSM8K](https://arxiv.org/abs/2110.14168), [MinervaMath](https://huggingface.co/datasets/math-ai/minervamath)<br>[MMLU](https://arxiv.org/abs/2009.03300), [MMLU-Pro](https://arxiv.org/abs/2406.01574), [NuminaMath](https://faculty.bicmr.pku.edu.cn/~dongbin/Publications/numina_dataset.pdf)<br>[MedQA](https://arxiv.org/abs/2009.13081), [MedMCQA](https://arxiv.org/abs/2203.14371), [MedBrowseComp](https://arxiv.org/abs/2505.14963)<br>[OlympiadBench](https://openreview.net/forum?id=OOCRYJIAMS7), [USACO](https://arxiv.org/abs/2404.10952), [HLE](https://arxiv.org/abs/2501.14249)<br>[FinSearchBench-24](https://arxiv.org/abs/2502.15684), [FinAgentBench](https://arxiv.org/abs/2508.14052), [xbench](https://xbench.org/)<br>[MIRAGE](https://arxiv.org/abs/2506.20100), [SolutionBench](https://arxiv.org/abs/2502.20730), [DQA](https://aclanthology.org/2024.naacl-long.364/), [AirQA](https://arxiv.org/abs/2509.16952), [HERB](https://arxiv.org/abs/2506.23139)<br>[SciQ](https://arxiv.org/abs/1707.06209), [SciFact](https://arxiv.org/abs/2004.14974), [ARC](https://arxiv.org/abs/1803.05457), [ScIRGen-Geo](https://arxiv.org/abs/2506.11117), [DeepShop](https://arxiv.org/abs/2506.02839), [NFCorpus](https://ir-datasets.com/nfcorpus.html), [OpenThoughts](https://arxiv.org/abs/2506.04178) |

<!-- </details> -->
