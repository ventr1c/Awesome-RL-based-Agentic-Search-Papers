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

## Note
We will update our repository quickly!

## Contents
* [Overview of RL-based Agentic Search](#overview-of-rl-based-agentic-search)
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
| 2025.10 | [A Comprehensive Survey on Reinforcement Learning-based Agentic Search: Foundations, Roles, Optimizations, Evaluations, and Applications](https://arxiv.org/abs/2510.16724) | *arXiv* |
| 2025.9 | [Reinforcement Learning Foundations for Deep Research Systems: A Survey](https://arxiv.org/abs/2509.06733) | *arXiv* |
| 2025.8 | [A Survey of LLM-based Deep Search Agents: Paradigm, Optimization, Evaluation, and Challenges](https://arxiv.org/abs/2508.05668) | *arXiv* |
| 2025.6 | [Reasoning RAG via System 1 or System 2: A Survey on Reasoning Agentic Retrieval-Augmented Generation for Industry Challenges](https://arxiv.org/abs/2506.10408) | *arXiv* |
| 2025.4 | [Synergizing RAG and Reasoning: A Systematic Review](https://arxiv.org/abs/2504.15909) | *arXiv* |
| 2025.1 | [Agentic Retrieval-Augmented Generation: A Survey on Agentic RAG](https://arxiv.org/abs/2501.09136) | *arXiv* |

---

## Method
### What RL is for: Functional Roles in Agentic Search
#### Retrieval Control
| Time  | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2025.03 | [Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](https://arxiv.org/pdf/2503.09516) | | *COLM 2025* | |
| 2025.3 | [Learning to Reason with Search for LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.19470) | | *NeurIPS 2025* | |
| 2025.2 | [DeepRAG: Thinking to Retrieval Step by Step for Large Language Models](https://arxiv.org/abs/2502.01142) |  | *arXiv* |  |
| 2025.8 | [UR²: Unify RAG and Reasoning through Reinforcement Learning](https://arxiv.org/abs/2508.06165) |  | *arXiv* |  |
| 2025.8 | [SSRL: Self‑Search Reinforcement Learning](https://arxiv.org/abs/2508.10874) |  | *arXiv* |  |
| 2025.3 | [R1‑Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.05592) |  | *arXiv* |  |
| 2025.4 | [DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real‑World Environments](https://arxiv.org/abs/2504.03160) |  | *arXiv* |  |
| 2025.8 | [MedResearcher‑R1: Expert‑Level Medical Deep Researcher via a Knowledge‑Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) |  | *arXiv* |  |
| 2025.5 | [Pangu DeepDiver: Adaptive Search Intensity Scaling via Open‑Web Reinforcement Learning](https://arxiv.org/abs/2505.24332) |  | *arXiv* |  |
| 2025.4 | [ReZero: Enhancing LLM Search Ability by Trying One‑More‑Time](https://arxiv.org/abs/2504.11001) |  | *arXiv* |  |
| 2025.5 | [StepSearch: Igniting LLMs’ Search Ability via Step‑Wise Proximal Policy Optimization](https://arxiv.org/abs/2505.15107) |  | *EMNLP 2025* |  |
| 2025.5 | [Process vs. Outcome Reward: Which Is Better for Agentic RAG Reinforcement Learning](https://arxiv.org/abs/2505.14069) |  | *arXiv* |  |
| 2025.9 | [WebSailor‑V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable Reinforcement Learning](https://arxiv.org/abs/2509.13305) |  | *arXiv* |  |
| 2025.5 | [R1‑Searcher++: Incentivizing the Dynamic Knowledge Acquisition of LLMs via Reinforcement Learning](https://arxiv.org/abs/2505.17005) |  | *arXiv* |  |
| 2025.5 | [Search Wisely: Mitigating Sub‑Optimal Agentic Searches by Reducing Uncertainty](https://arxiv.org/abs/2505.17281) |  | *arXiv* |  |
| 2025.5 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) |  | *arXiv* |  |
| 2025.8 | [ParallelSearch: Train Your LLMs to Decompose Query and Search Sub‑Queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) |  | *arXiv* |  |
| 2025.7 | [RAG‑R1: Incentivize the Search and Reasoning Capabilities of LLMs through Multi‑Query Parallelism](https://arxiv.org/abs/2507.02962) |  | *arXiv* |  |
| 2025.4 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) |  | *arXiv* |  |

#### Query Optimization
| Time   | Paper Title | Role | Venue | Code |
| :----- | :----------- | :---- | :---- | :---- |
| 2025.5 | [ConvSearch‑R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning](https://arxiv.org/abs/2505.15776) |  | *arXiv* |  |
| 2025.5 | [MaskSearch: A Universal Pre‑Training Framework to Enhance Agentic Search Capability](https://arxiv.org/abs/2505.20285) |  | *arXiv* |  |
| 2025.8 | [ParallelSearch: Train Your LLMs to Decompose Query and Search Sub‑Queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) |  | *arXiv* |  |
| 2025.7 | [RAG‑R1: Incentivize the Search and Reasoning Capabilities of LLMs through Multi‑Query Parallelism](https://arxiv.org/abs/2507.02962) |  | *arXiv* |  |
| 2025.8 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner‑Executor Architecture for Reasoning‑Oriented Multi‑Hop Retrieval](https://arxiv.org/abs/2508.16438) |  | *arXiv* |  |
| 2025.9 | [WebExplorer: Explore and Evolve for Training Long‑Horizon Web Agents](https://arxiv.org/abs/2509.06501) |  | *arXiv* |  |
| 2025.3 | [DeepRetrieval: Hacking Real Search Engines and Retrievers with Large Language Models via Reinforcement Learning](https://arxiv.org/abs/2503.00223) |  | *arXiv* |  |
| 2025.5 | [s3: You Don’t Need That Much Data to Train a Search Agent via RL](https://arxiv.org/abs/2505.14146) |  | *arXiv* |  |
| 2025.5 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) |  | *arXiv* |  |
| 2025.4 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) |  | *arXiv* |  |
| 2025.1 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) |  | *arXiv* |  |

#### Reasoning–Retrieval Integration
| Time  | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2025.6 | [R‑Search: Empowering LLM Reasoning with Search via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2506.04185) |  | *arXiv* |  |
| 2025.5 | [Search and Refine During Think: Autonomous Retrieval‑Augmented Reasoning of LLMs](https://arxiv.org/abs/2505.11277) |  | *arXiv* |  |
| 2025.5 | [EvolveSearch: An Iterative Self‑Evolving Search Agent](https://arxiv.org/abs/2505.22501) |  | *arXiv* |  |
| 2025.5 | [O²‑Searcher: A Searching‑Based Agent Model for Open‑Domain Open‑Ended Question Answering](https://arxiv.org/abs/2505.16582) |  | *arXiv* |  |
| 2025.8 | [Atom‑Searcher: Enhancing Agentic Deep Research via Fine‑Grained Atomic Thought Reward](https://arxiv.org/abs/2508.12800) |  | *arXiv* |  |
| 2025.9 | [ReSum: Unlocking Long‑Horizon Search Intelligence via Context Summarization](https://arxiv.org/abs/2509.13313) |  | *arXiv* |  |
| 2025.9 | [SFR‑DeepResearch: Towards Effective Reinforcement Learning for Autonomously Reasoning Single Agents](https://arxiv.org/abs/2509.06283) |  | *arXiv* |  |
| 2025.10 | [RECON: Reasoning with Condensation for Efficient Retrieval‑Augmented Generation](https://arxiv.org/abs/2510.10448) |  | *arXiv* |  |
| 2025.7 | [WebSailor: Navigating Super‑Human Reasoning for Web Agents](https://arxiv.org/abs/2507.02592) |  | *arXiv* |  |
| 2025.7 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) |  | *arXiv* |  |
| 2025.8 | [Beyond Ten Turns: Unlocking Long‑Horizon Agentic Search with Large‑Scale Asynchronous RL](https://arxiv.org/abs/2508.07976) |  | *arXiv* |  |

#### Multi‑Agent Collaboration
| Time  | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2025.8 | [MAO‑ARAG: Multi‑Agent Orchestration for Adaptive Retrieval‑Augmented Generation](https://arxiv.org/abs/2508.01005) |  | *arXiv* |  |
| 2025.8 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner‑Executor Architecture for Reasoning‑Oriented Multi‑Hop Retrieval](https://arxiv.org/abs/2508.16438) |  | *arXiv* |  |
| 2025.8 | [AI‑SearchPlanner: Modular Agentic Search via Pareto‑Optimal Multi‑Objective Reinforcement Learning](https://arxiv.org/abs/2508.20368) |  | *arXiv* |  |
| 2025.9 | [SIRAG: Towards Stable and Interpretable RAG with a Process‑Supervised Multi‑Agent Framework](https://arxiv.org/abs/2509.18167) |  | *arXiv* |  |
| 2025.1 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) |  | *arXiv* |  |
| 2025.9 | [AgentGym‑RL: Training LLM Agents for Long‑Horizon Decision Making through Multi‑Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755) |  | *arXiv* |  |
| 2025.8 | [Chain‑of‑Agents: End‑to‑End Agent Foundation Models via Multi‑Agent Distillation and Agentic RL](https://arxiv.org/abs/2508.13167) |  | *arXiv* |  |
| 2025.9 | [WebExplorer: Explore and Evolve for Training Long‑Horizon Web Agents](https://arxiv.org/abs/2509.06501) |  | *arXiv* |  |

#### Tool and Knowledge Integration
| Time  | Paper Title | Role | Venue | Code |
| :---- | :----------- | :---- | :---- | :---- |
| 2025.5 | [Tool‑Star: Empowering LLM‑Brained Multi‑Tool Reasoner via Reinforcement Learning](https://arxiv.org/abs/2505.16410) |  | *arXiv* |  |
| 2025.9 | [VerlTool: Towards Holistic Agentic Reinforcement Learning with Tool Use](https://arxiv.org/abs/2509.01055) |  | *arXiv* |  |
| 2025.8 | [WebWatcher: Breaking New Frontier of Vision‑Language Deep Research Agent](https://arxiv.org/abs/2508.05748) |  | *arXiv* |  |
| 2025.9 | [WebResearcher: Unleashing Unbounded Reasoning Capability in Long‑Horizon Agents](https://arxiv.org/abs/2509.13309) |  | *arXiv* |  |
| 2025.8 | [MedResearcher‑R1: Expert‑Level Medical Deep Researcher via a Knowledge‑Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) |  | *arXiv* |  |
| 2025.5 | [Visual Agentic Reinforcement Fine‑Tuning](https://arxiv.org/abs/2505.14246) |  | *arXiv* |  |
| 2025.5 | [VRAG‑RL: Empower Vision‑Perception‑Based RAG for Visually Rich Information Understanding via Iterative Reasoning with RL](https://arxiv.org/abs/2505.22019) |  | *arXiv* |  |
| 2025.6 | [MMSearch‑R1: Incentivizing LMMs to Search](https://arxiv.org/abs/2506.20670) |  | *arXiv* |  |
| 2025.8 | [GRAIL: Learning to Interact with Large Knowledge Graphs for Retrieval‑Augmented Reasoning](https://arxiv.org/abs/2508.05498) |  | *arXiv* |  |
| 2025.7 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) |  | *arXiv* |  |

### How RL is Used: Optimization Strategies
The below table summarizes representative works with corresponding optimization strategies.
<details>
<summary>📊 Click to expand long table (scrollable)</summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">

| Method | RL Func. Role | Cold Start? | Training Env. | RL Alg. | Reward Type | Reward Func. | Opt. Scope | Dataset |
|---|---|---|---|---|---|---|---|---|
| Search-R1 [jin2025searchr1] | Adapt-Search | ✗ | Real-world | PPO<br>GRPO | Rule-based ORM | Answer EM | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, trivedi2022musique, ho2020constructing, press2022measuring] |
| ReSearch [chen2025learning] | Adapt-Search | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Single-agent | [yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring] |
| AutoCoA [zhang2025agent] | Adapt-Search | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, trivedi2022musique, ho2020constructing, press2022measuring] |
| SimpleDeep-<br>Searcher<br>[sun2025simpledeepsearcher] | Adapt-Search | ✓ | Real-world | DPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer F1 | Single-agent | [yang2018hotpotqa, ho2020constructing, trivedi2022musique, tang2024multihop, krishna2024frames, press2022measuring, mialon2023gaia, zhou2025browsecomp, wei2025browsecomp] |
| ExSearch [shi2025iterative] | Adapt-Search | ✗ | Real-world | GEM | PRM | Trajectory Quality | Single-agent | [kwiatkowski2019natural, yang2018hotpotqa, trivedi2022musique] |
| IKEA [huang2025reinforced] | Search Efficiency | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Knowledge-boundary | Step-level | [kwiatkowski2019natural, mallen2022not, yang2018hotpotqa, ho2020constructing] |
| R1-Searcher [song2025r1] | Adapt-Search | ✓ | Real-world | GRPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer F1 | Single-agent | [yang2018hotpotqa, ho2020constructing, press2022measuring, trivedi2022musique] |
| R1-Searcher++ [song2025r1++] | Search Efficiency | ✓ | Real-world | GRPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer EM<br>Std of Search Calls | Single-agent | [yang2018hotpotqa, ho2020constructing, press2022measuring, trivedi2022musique] |
| DeepRAG [guan2025deeprag] | Adapt-Search<br>Search Efficiency | ✓ | Real-world | GRPO | Rule-based ORM | Answer EM<br>Retrieval Cost | Single-agent | [yang2018hotpotqa, ho2020constructing, pan2024cag, mallen2022not, berant2013webquestions, trivedi2022musique] |
| UR² [li2025ur] | Adapt-Search | ✓ | Real-world<br>Curriculum | Reinforce++ | Rule-based ORM | Format<br>Answer EM<br>Fallback Penalty | Single-agent | [hendrycks2021measuring, lewkowycz2022solving, jin2021disease, wang2024mmlu, yang2018hotpotqa, press2022measuring, ho2020constructing, trivedi2022musique] |
| SSRL [fan2025ssrl] | Adapt-Search | ✓ | Simulated<br>Self-Search | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, yang2018hotpotqa, trivedi2022musique, ho2020constructing, press2022measuring] |
| Pangu DeepDiver [shi2025pangu] | Adapt-Search<br>Search Intensity | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Extra Search | Single-agent | [shi2025pangu, press2022measuring, wei2024measuring, krishna2024frames] |
| ReZero [dao2025rezero] | Search Intensity | ✗ | Real-world | GRPO | ORM+PRM | Format<br>Answer LLM-Judge<br>Retry | Step-level | [menlo2025apollo3] |
| StepSearch [wang2025stepsearch] | Adapt-Search<br>Search Intensity | ✗ | Real-world | PPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Search Key<br>Information Gain<br>Redundancy Penalty | Step-level | [yang2018hotpotqa, trivedi2022musique, ho2020constructing, press2022measuring] |
| VERITAS [xu2025VERITAS] | Adapt-Search<br>R-Aware Opt. | ✗ | Real-world | PPO | ORM+PRM | Answer EM<br>Enhancing Faithfulness | Step-level | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, trivedi2022musique, ho2020constructing, press2022measuring] |
| ReasonRAG [zhang2025process] | Search Efficiency<br>R-S Inter. | ✗ | Real-world<br>MCTS | DPO | PRM | Shortest Path | Step-level | [mallen2022not, yang2018hotpotqa, ho2020constructing, press2022measuring, trivedi2022musique] |
| Web-Sailor [li2025websailor] | Adapt-Search<br>Ctx-Mem. | ✓ | Real-world | DUPO | ORM | Format<br>Answer F1 | Single-agent | [li2025sailorfogqa, wei2025browsecomp, zhou2025browsecomp, mialon2023gaia, xbench] |
| WebSailor-V2 [li2025websailorv2] | Multi-tool<br>Ctx-Mem. | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Single-agent | [li2025sailorfogqav2, wei2025browsecomp, zhou2025browsecomp, mialon2023gaia, xbench, phan2025humanity, du2025deepresearch] |
| Search Wisely [wu2025search] | Search Efficiency | ✗ | Real-world | β-GRPO | Rule-based ORM | Confidence-based Answer EM | Single-agent | [kwiatkowski2019natural, yang2018hotpotqa, joshi2017triviaqa, ho2020constructing, press2022measuring, trivedi2022musique] |
| ZeroSearch [sun2025zerosearch] | Search Efficiency | ✓ | Simulated<br>Curriculum | PPO<br>GRPO<br>Reinforce | Rule-based ORM | Answer F1 | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring] |
| ParallelSearch [zhao2025parallelsearch] | Search Efficiency | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Query Decomopse<br>Search count | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring] |
| RAG-R1 [tan2025ragr1] | Search Efficiency<br>Conv-Reform. | ✓ | Real-world | PPO | ORM | Answer EM | Single-agent | [kwiatkowski2019natural, mallen2022not, joshi2017triviaqa, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring] |
| ConvSearch-R1 [zhu2025convsearch] | Conv-Reform. | ✓ | Real-world | GRPO | ORM | Format<br>Rank-Incentive | Step-level | [adlakha2022topiocqa, anantha2021open] |
| MaskSearch [wu2025masksearch] | Conver. Reform.<br>R–S Inter. | ✓ | Real-world<br>Curriculum<br>RAMP | DAPO | Rule-based ORM | Format<br>Answer Recall<br>Length penalty | Single-agent | [yang2018hotpotqa, zhu2024fanoutqa, trivedi2022musique, ho2020constructing, press2022measuring, vu2024freshqa] |
| DeepRetrieval [jiang2025deepretrieval] | R-Aware Opt. | ✓ | Simulated | PPO | ORM | Format<br>Answer Recall | Single-level | [kwiatkowski2019natural, joshi2017triviaqa, rajpurkar2016squad, thorne2018fever, wadden2020fact] |
| WebThinker [li2025webthinker] | Search Efficiency | ✗ | Real-world | DPO | PRM | Answer EM<br>Tool Calls<br>Length penalty | Single-agent | [rein2024gpqa, mialon2023gaia, wu2025webwalker, phan2025humanity, du2025supergpqa, openthoughts2025open, yuan2025naturalreasoning, li2024numinamath] |
| s3 [jiang2025s3] | R-Aware Opt. | ✓ | Simulated | PPO | Rule-based ORM | Gain Beyond RAG | Module-level | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, ho2020constructing, trivedi2022musique] |
| R-Search [zhao2025r] | R–S Inter. | ✗ | Real-world | PPO<br>GRPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Evidence Quality | Single-agent | [yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring] |
| AutoRefine [shi2025search] | R–S Inter. | ✗ | Real-world | GRPO | ORM plus PRM | Answer F1<br>Retrieval Reward | Step-level | [kwiatkowski2019natural, joshi2017triviaqa, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, mallen2022not] |
| EvolveSearch [zhang2025evolvesearch] | R–S Inter. | ✓ | Real-world<br>Self-evolving | GRPO | ORM | Format<br>Answer LLM-Judge | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, mallen2022not] |
| O²-Searcher [mei2025o2] | R–S Inter. | ✓ | Simulated | GRPO | Rule-based ORM | Format<br>Diversity reward<br>Factual reward | Single-agent | [kwiatkowski2019natural, yang2018hotpotqa, joshi2017triviaqa, mallen2022not, ho2020constructing, trivedi2022musique, press2022measuring] |
| Atom-Searcher [deng2025atom] | R–S Inter. | ✓ | Real-world<br>Curriculum | GRPO | PRM+Rule-based ORM | Format<br>Answer F1<br>Atomic thought reward | Step-level | [kwiatkowski2019natural, joshi2017triviaqa, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, mallen2022not] |
| ReSum [wu2025resum] | Ctx-Mem. | ✗ | Real-world | Resume-GRPO | ORM | Answer LLM-Judge | Single-agent | [mialon2023gaia, wei2025browsecomp, zhou2025browsecomp, wei2024measuring, wu2025webwalker, xbench] |
| SFR-DeepResearch [nguyen2025sfr] | Ctx-Mem.<br>Multi-tool | ✗ | Real-world | REINFORCE | ORM | Answer LLM-Judge | Single-agent | [krishna2024frames, mialon2023gaia, phan2025humanity] |
| MAO-ARAG [chen2025mao] | P–E Orches. | ✓ | Real-world | PPO | ORM | Format<br>Cost Penalty<br>Answer F1 | Multi-agent | [kwiatkowski2019natural, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, mallen2022not, min2020ambigqa] |
| OPERA [liu2025opera] | P–E Orches. | ✓ | Real-world | MAPGRPO | PRM+ORM | Answerer Reward<br>Planer Reward<br>Rewriter&nbsp;Reward | Multi-agent | [yang2018hotpotqa, ho2020constructing, trivedi2022musique, kwiatkowski2019natural, tang2024multihop] |
| AI-SearchPlanner [mei2025ai] | P–E Orches. | ✗ | Real-world | PPO | ORM | Answer LLM-Judge<br>Trajectory Rationality | Module-level | [kwiatkowski2019natural, joshi2017triviaqa, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, mallen2022not] |
| SIRAG [wang2025sirag] | Cooperative | ✗ | Real-world | PPO | PRM | Process LLM-Judge | Multi-agent | [ho2020constructing, yang2018hotpotqa, kwiatkowski2019natural, mallen2022not] |
| MMOA-RAG [chen2025improving] | Cooperative<br>R-aware Opt. | ✗ | Real-world | MA-PPO | Rule-based ORM | Answer F1<br>Efficiency penalty | Multi-agent | [yang2018hotpotqa, ho2020constructing, min2020ambigqa] |
| Tool-Star [dong2025tool] | Multi tool | ✓ | Real-world | REINFORCE++<br>GRPO<br>DPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [lightman2023let, hendrycks2021measuring, cobbe2021training, wu2025webwalker, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring] |
| WebWatcher [geng2025webwatcher] | Multi tool<br>Multi-modal | ✓ | Real-world | GRPO | ORM | Format<br>Answer LLM-Judge | Single-agent | [phan2025humanity, li2025mm, fu2025livevqa, jiang2024mmsearch, cheng2025simplevqa] |
| Visual-ARFT [liu2025visual] | Multi-modal<br>Multi-tool<br>Adapt-Search | ✓ | Real-world | GRPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Query Semantic Sim. | Single-agent | [liu2025matsearch] |
| VRAG-RL [wang2025vrag] | Multi-modal<br>Search Efficiency | ✓ | Simulated | GRPO | ORM | Format<br>Answer LLM-Judge<br>Retrieval Efficiency | Single-agent | [tanaka2023slidevqa, wang2025vidorag, ma2024mmlongbench] |
| MMSearch-R1 [wu2025mmsearch] | Multi-modal <br>Search Efficiency | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Search Penalty | Single-agent | [wu2025mmsearch, chen2023can, jiang2024mmsearch, cheng2025simplevqa, fu2025livevqa] |
| GRAIL [chang2025grail] | Adapt-Search<br>Struct-Nav. | ✓ | Real-world<br>Graph Env. | GRPO | PRM | Process LLM-Judge | Single-agent | [berant2013webquestions, puerto2021metaqa, talmor2018web] |
| DynaSearcher [hao2025dynasearcher] | Struct-Nav. | ✗ | Real-world<br>Graph Env.<br>KG+Doc Search | GRPO | Rule-based ORM | Format<br>Answer F1<br>Information Gain<br>Retrieval Penalty | Single-agent | [yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, krishna2024frames] |
| HARIS [hu2025coordinating] | R-S Inter. | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer Accuracy<br>Decision Accuracy | Multi-agent | [ma2024ex, jiang2020hover, si2024checkwhy] |
| DeepNote [wang2024retriever] | Adapt-Search<br>Conv-Reform. | ✗ | Real-world | DPO | - | - | Single-agent | [yang2018hotpotqa, ho2020constructing, trivedi2022musique, geva2021strategyqa, stelmakh2022asqa] |
| DeepResearcher [zheng2025deepresearcher] | Adapt-Search<br>Search Efficiency<br>Ctx-Mem. | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Module-level | [kwiatkowski2019natural, joshi2017triviaqa, yang2018hotpotqa, ho2020constructing] |
| SWiRL [goldie2025synthetic] | Adapt-Search<br>R-S Inter. | ✓ | Real-world | PPO | PRM | Step LLM-Judge | Step-level | [yang2018hotpotqa, trivedi2022musique, wu2024cofca, cobbe2021training, qi2021answering] |
| WebDancer [wu2025webdancer] | Multi tool | ✓ | Real-world | DAPO | ORM | Answer EM | Single-agent | [mialon2023gaia, wu2025webwalker, zhou2025browsecomp, wei2025browsecomp] |
| MedResearcher-R1 [yu2025medresearcher] | Adpt-Search<br>Multi-Tool | ✓ | Real-world<br>Medical Tool | GRPO | ORM | Answer Acc<br>Response Quality<br>Efficiency penalty | Single-agent | [xbench, mialon2023gaia, chen2025medbrowsecomp] |
| Lucy [dao2025lucy] | Search Efficiency<br>R–S Inter. | ✓ | Real-world<br>SLMs | DAPO | Rule-based ORM | Format/XML validity<br>Answer EM<br>Tool exec. success<br>Visit/Search ratio<br>Efficient thinking | Single-agent | [wei2024measuring] |
| ASearcher [gao2025beyond] | R-S Inter.<br>Ctx-Mem.<br>Multi-tool | ✓ | Real-world<br>Browser Env.<br>Asynchronous | GRPO | ORM | Answer LLM-Judge | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, mallen2022not, yang2018hotpotqa, ho2020constructing, trivedi2022musique, press2022measuring, krishna2024frames, mialon2023gaia, xbench] |
| WebExplorer [liu2025webexplorer] | Ctx-Mem.<br>Conv-Reform. | ✓ | Real-world<br>Curriculum | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [zhou2025browsecomp, wei2025browsecomp, mialon2023gaia, wu2025webwalker, krishna2024frames, xbench, phan2025humanity] |
| WebResearcher [qiao2025webresearcher] | Multi-tool | ✓ | Real-world<br>Curriculum | GSPO | Rule-based ORM | Answer EM | Single-agent | [phan2025humanity, mialon2023gaia, wei2025browsecomp, zhou2025browsecomp, xbench, krishna2024frames] |
| RECON [xu2025reconreasoningcondensationefficient] | Ctx-Mem. | ✓ | Real-world | PPO | Rule-based ORM | Answer EM | Single-agent | [kwiatkowski2019natural, joshi2017triviaqa, press2022measuring, yang2018hotpotqa, ho2020constructing, trivedi2022musique, mallen2022not] |
| AgentGym-RL [xi2025agentgym] | Cooperative<br>Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| Chain-of-Agents [li2025chain] | Cooperative<br>Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| Verl [sheng2024hybridflow] | Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| VerlTool [jiang2025verltool] | Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |

</div>
</details>


### Where RL is Applied: Optimization Scopes
#### Agent-level
#### Step-level
#### Module-level
#### System-level

## Evaluation
### Metrics

### Datasets