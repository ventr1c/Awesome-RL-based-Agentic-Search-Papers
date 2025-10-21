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
* [Survey](#survey)
* [Method](#method)
* [Evaluation](#evaluation)


## Survey
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
### Functional Roles of RL in Agentic Search
#### Retrieval Control
| Time  | Paper Title | Venue |
| :---- | :----------- | :---- |
| 2025.03 | [Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](https://arxiv.org/pdf/2503.09516) | *COLM 2025* |
| 2025.3 | [Learning to Reason with Search for LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.19470) | *arXiv* |
| 2025.2 | [DeepRAG: Thinking to Retrieval Step by Step for Large Language Models](https://arxiv.org/abs/2502.01142) | *arXiv* |
| 2025.8 | [UR²: Unify RAG and Reasoning through Reinforcement Learning](https://arxiv.org/abs/2508.06165) | *arXiv* |
| 2025.8 | [SSRL: Self‑Search Reinforcement Learning](https://arxiv.org/abs/2508.10874) | *arXiv* |
| 2025.3 | [R1‑Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2503.05592) | *arXiv* |
| 2025.4 | [DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real‑World Environments](https://arxiv.org/abs/2504.03160) | *arXiv* |
| 2025.8 | [MedResearcher‑R1: Expert‑Level Medical Deep Researcher via a Knowledge‑Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) | *arXiv* |
| 2025.5 | [Pangu DeepDiver: Adaptive Search Intensity Scaling via Open‑Web Reinforcement Learning](https://arxiv.org/abs/2505.24332) | *arXiv* |
| 2025.4 | [ReZero: Enhancing LLM Search Ability by Trying One‑More‑Time](https://arxiv.org/abs/2504.11001) | *arXiv* |
| 2025.5 | [StepSearch: Igniting LLMs’ Search Ability via Step‑Wise Proximal Policy Optimization](https://arxiv.org/abs/2505.15107) | *arXiv* |
| 2025.5 | [Process vs. Outcome Reward: Which Is Better for Agentic RAG Reinforcement Learning](https://arxiv.org/abs/2505.14069) | *arXiv* |
| 2025.9 | [WebSailor‑V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable Reinforcement Learning](https://arxiv.org/abs/2509.13305) | *arXiv* |
| 2025.5 | [R1‑Searcher++: Incentivizing the Dynamic Knowledge Acquisition of LLMs via Reinforcement Learning](https://arxiv.org/abs/2505.17005) | *arXiv* |
| 2025.5 | [Search Wisely: Mitigating Sub‑Optimal Agentic Searches by Reducing Uncertainty](https://arxiv.org/abs/2505.17281) | *arXiv* |
| 2025.5 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) | *arXiv* |
| 2025.8 | [ParallelSearch: Train Your LLMs to Decompose Query and Search Sub‑Queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) | *arXiv* |
| 2025.7 | [RAG‑R1: Incentivize the Search and Reasoning Capabilities of LLMs through Multi‑Query Parallelism](https://arxiv.org/abs/2507.02962) | *arXiv* |
| 2025.4 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) | *arXiv* |

#### Query Optimization
| Time   | Paper Title | Venue |
| :----- | :----------- | :---- |
| 2025.5 | [ConvSearch‑R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning](https://arxiv.org/abs/2505.15776) | *arXiv* |
| 2025.5 | [MaskSearch: A Universal Pre‑Training Framework to Enhance Agentic Search Capability](https://arxiv.org/abs/2505.20285) | *arXiv* |
| 2025.8 | [ParallelSearch: Train Your LLMs to Decompose Query and Search Sub‑Queries in Parallel with Reinforcement Learning](https://arxiv.org/abs/2508.09303) | *arXiv* |
| 2025.7 | [RAG‑R1: Incentivize the Search and Reasoning Capabilities of LLMs through Multi‑Query Parallelism](https://arxiv.org/abs/2507.02962) | *arXiv* |
| 2025.8 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner‑Executor Architecture for Reasoning‑Oriented Multi‑Hop Retrieval](https://arxiv.org/abs/2508.16438) | *arXiv* |
| 2025.9 | [WebExplorer: Explore and Evolve for Training Long‑Horizon Web Agents](https://arxiv.org/abs/2509.06501) | *arXiv* |
| 2025.3 | [DeepRetrieval: Hacking Real Search Engines and Retrievers with Large Language Models via Reinforcement Learning](https://arxiv.org/abs/2503.00223) | *arXiv* |
| 2025.5 | [s3: You Don’t Need That Much Data to Train a Search Agent via RL](https://arxiv.org/abs/2505.14146) | *arXiv* |
| 2025.5 | [ZeroSearch: Incentivize the Search Capability of LLMs without Searching](https://arxiv.org/abs/2505.04588) | *arXiv* |
| 2025.4 | [WebThinker: Empowering Large Reasoning Models with Deep Research Capability](https://arxiv.org/abs/2504.21776) | *arXiv* |
| 2025.1 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | *arXiv* |

#### Reasoning–Retrieval Integration
| Time   | Paper Title | Venue |
| :----- | :----------- | :---- |
| 2025.6 | [R‑Search: Empowering LLM Reasoning with Search via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2506.04185) | *arXiv* |
| 2025.5 | [Search and Refine During Think: Autonomous Retrieval‑Augmented Reasoning of LLMs](https://arxiv.org/abs/2505.11277) | *arXiv* |
| 2025.5 | [EvolveSearch: An Iterative Self‑Evolving Search Agent](https://arxiv.org/abs/2505.22501) | *arXiv* |
| 2025.5 | [O²‑Searcher: A Searching‑Based Agent Model for Open‑Domain Open‑Ended Question Answering](https://arxiv.org/abs/2505.16582) | *arXiv* |
| 2025.8 | [Atom‑Searcher: Enhancing Agentic Deep Research via Fine‑Grained Atomic Thought Reward](https://arxiv.org/abs/2508.12800) | *arXiv* |
| 2025.9 | [ReSum: Unlocking Long‑Horizon Search Intelligence via Context Summarization](https://arxiv.org/abs/2509.13313) | *arXiv* |
| 2025.9 | [SFR‑DeepResearch: Towards Effective Reinforcement Learning for Autonomously Reasoning Single Agents](https://arxiv.org/abs/2509.06283) | *arXiv* |
| 2025.10 | [RECON: Reasoning with Condensation for Efficient Retrieval‑Augmented Generation](https://arxiv.org/abs/2510.10448) | *arXiv* |
| 2025.7 | [WebSailor: Navigating Super‑Human Reasoning for Web Agents](https://arxiv.org/abs/2507.02592) | *arXiv* |
| 2025.7 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) | *arXiv* |
| 2025.8 | [Beyond Ten Turns: Unlocking Long‑Horizon Agentic Search with Large‑Scale Asynchronous RL](https://arxiv.org/abs/2508.07976) | *arXiv* |

#### Multi‑Agent Collaboration
| Time   | Paper Title | Venue |
| :----- | :----------- | :---- |
| 2025.8 | [MAO‑ARAG: Multi‑Agent Orchestration for Adaptive Retrieval‑Augmented Generation](https://arxiv.org/abs/2508.01005) | *arXiv* |
| 2025.8 | [OPERA: A Reinforcement Learning–Enhanced Orchestrated Planner‑Executor Architecture for Reasoning‑Oriented Multi‑Hop Retrieval](https://arxiv.org/abs/2508.16438) | *arXiv* |
| 2025.8 | [AI‑SearchPlanner: Modular Agentic Search via Pareto‑Optimal Multi‑Objective Reinforcement Learning](https://arxiv.org/abs/2508.20368) | *arXiv* |
| 2025.9 | [SIRAG: Towards Stable and Interpretable RAG with a Process‑Supervised Multi‑Agent Framework](https://arxiv.org/abs/2509.18167) | *arXiv* |
| 2025.1 | [Improving Retrieval‑Augmented Generation through Multi‑Agent Reinforcement Learning](https://arxiv.org/abs/2501.15228) | *arXiv* |
| 2025.9 | [AgentGym‑RL: Training LLM Agents for Long‑Horizon Decision Making through Multi‑Turn Reinforcement Learning](https://arxiv.org/abs/2509.08755) | *arXiv* |
| 2025.8 | [Chain‑of‑Agents: End‑to‑End Agent Foundation Models via Multi‑Agent Distillation and Agentic RL](https://arxiv.org/abs/2508.13167) | *arXiv* |
| 2025.9 | [WebExplorer: Explore and Evolve for Training Long‑Horizon Web Agents](https://arxiv.org/abs/2509.06501) | *arXiv* |

#### Tool and Knowledge Integration
| Time   | Paper Title | Venue |
| :----- | :----------- | :---- |
| 2025.5 | [Tool‑Star: Empowering LLM‑Brained Multi‑Tool Reasoner via Reinforcement Learning](https://arxiv.org/abs/2505.16410) | *arXiv* |
| 2025.9 | [VerlTool: Towards Holistic Agentic Reinforcement Learning with Tool Use](https://arxiv.org/abs/2509.01055) | *arXiv* |
| 2025.8 | [WebWatcher: Breaking New Frontier of Vision‑Language Deep Research Agent](https://arxiv.org/abs/2508.05748) | *arXiv* |
| 2025.9 | [WebResearcher: Unleashing Unbounded Reasoning Capability in Long‑Horizon Agents](https://arxiv.org/abs/2509.13309) | *arXiv* |
| 2025.8 | [MedResearcher‑R1: Expert‑Level Medical Deep Researcher via a Knowledge‑Informed Trajectory Synthesis Framework](https://arxiv.org/abs/2508.14880) | *arXiv* |
| 2025.5 | [Visual Agentic Reinforcement Fine‑Tuning](https://arxiv.org/abs/2505.14246) | *arXiv* |
| 2025.5 | [VRAG‑RL: Empower Vision‑Perception‑Based RAG for Visually Rich Information Understanding via Iterative Reasoning with RL](https://arxiv.org/abs/2505.22019) | *arXiv* |
| 2025.6 | [MMSearch‑R1: Incentivizing LMMs to Search](https://arxiv.org/abs/2506.20670) | *arXiv* |
| 2025.8 | [GRAIL: Learning to Interact with Large Knowledge Graphs for Retrieval‑Augmented Reasoning](https://arxiv.org/abs/2508.05498) | *arXiv* |
| 2025.7 | [DynaSearcher: Dynamic Knowledge Graph Augmented Search Agent via Multi‑Reward Reinforcement Learning](https://arxiv.org/abs/2507.17365) | *arXiv* |

### Optimization Scope
#### Agent-level
#### Step-level
#### Module-level
#### System-level

## Evaluation
### Metrics

### Datasets