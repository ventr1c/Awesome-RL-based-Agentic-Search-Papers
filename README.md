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
### How RL is Used: Optimization Strategies
The below table summarizes representative works with corresponding optimization strategies. Specifically, ORM and PRM denote the Outcome Reward Model and the Process Reward Model, respectively. “Rule-based” indicates that the reward function is entirely computed from predefined rules; otherwise, an LLM is involved as a reward judge.
<details>
<summary>📊 Click to expand long table (scrollable). </summary>

<div style="overflow-x: auto; white-space: nowrap; font-size: 90%;">

| Method | RL Func. Role | Cold Start? | Training Env. | RL Alg. | Reward Type | Reward Func. | Opt. Scope | Dataset |
|---|---|---|---|---|---|---|---|---|
| Search-R1 | Adapt-Search | ✗ | Real-world | PPO<br>GRPO | Rule-based ORM | Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| ReSearch | Adapt-Search | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| AutoCoA | Adapt-Search | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| SimpleDeep-<br>Searcher | Adapt-Search | ✓ | Real-world | DPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer F1 | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), tang2024multihop, krishna2024frames, [Bamboogle](https://arxiv.org/abs/2210.03350), mialon2023gaia, zhou2025browsecomp, wei2025browsecomp] |
| ExSearch | Adapt-Search | ✗ | Real-world | GEM | PRM | Trajectory Quality | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573)] |
| IKEA | Search Efficiency | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Knowledge-boundary | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060)] |
| R1-Searcher | Adapt-Search | ✓ | Real-world | GRPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer F1 | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [Musique](https://arxiv.org/abs/2108.00573)] |
| R1-Searcher++ | Search Efficiency | ✓ | Real-world | GRPO<br>Reinforce++ | Rule-based ORM | Format<br>Answer EM<br>Std of Search Calls | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [Musique](https://arxiv.org/abs/2108.00573)] |
| DeepRAG | Adapt-Search<br>Search Efficiency | ✓ | Real-world | GRPO | Rule-based ORM | Answer EM<br>Retrieval Cost | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), pan2024cag, [PopQA](https://arxiv.org/abs/2212.10511), berant2013webquestions, [Musique](https://arxiv.org/abs/2108.00573)] |
| UR² | Adapt-Search | ✓ | Real-world<br>Curriculum | Reinforce++ | Rule-based ORM | Format<br>Answer EM<br>Fallback Penalty | Single-agent | [hendrycks2021measuring, lewkowycz2022solving, jin2021disease, wang2024mmlu, [Hotpot](https://arxiv.org/abs/1809.09600), [Bamboogle](https://arxiv.org/abs/2210.03350), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573)] |
| SSRL | Adapt-Search | ✓ | Simulated<br>Self-Search | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| Pangu DeepDiver | Adapt-Search<br>Search Intensity | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Extra Search | Single-agent | [shi2025pangu, [Bamboogle](https://arxiv.org/abs/2210.03350), wei2024measuring, krishna2024frames] |
| ReZero | Search Intensity | ✗ | Real-world | GRPO | ORM+PRM | Format<br>Answer LLM-Judge<br>Retry | Step-level | [menlo2025apollo3] |
| StepSearch | Adapt-Search<br>Search Intensity | ✗ | Real-world | PPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Search Key<br>Information Gain<br>Redundancy Penalty | Step-level | [[Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| VERITAS | Adapt-Search<br>R-Aware Opt. | ✗ | Real-world | PPO | ORM+PRM | Answer EM<br>Enhancing Faithfulness | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| ReasonRAG | Search Efficiency<br>R-S Inter. | ✗ | Real-world<br>MCTS | DPO | PRM | Shortest Path | Step-level | [[PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [Musique](https://arxiv.org/abs/2108.00573)] |
| Web-Sailor | Adapt-Search<br>Ctx-Mem. | ✓ | Real-world | DUPO | ORM | Format<br>Answer F1 | Single-agent | [li2025sailorfogqa, wei2025browsecomp, zhou2025browsecomp, mialon2023gaia, xbench] |
| WebSailor-V2 | Multi-tool<br>Ctx-Mem. | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Single-agent | [li2025sailorfogqav2, wei2025browsecomp, zhou2025browsecomp, mialon2023gaia, xbench, phan2025humanity, du2025deepresearch] |
| Search Wisely | Search Efficiency | ✗ | Real-world | β-GRPO | Rule-based ORM | Confidence-based Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [Hotpot](https://arxiv.org/abs/1809.09600), [TriviaQA](https://arxiv.org/abs/1705.03551), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), [Musique](https://arxiv.org/abs/2108.00573)] |
| ZeroSearch | Search Efficiency | ✓ | Simulated<br>Curriculum | PPO<br>GRPO<br>Reinforce | Rule-based ORM | Answer F1 | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| ParallelSearch | Search Efficiency | ✓ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Query Decomopse<br>Search count | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| RAG-R1 | Search Efficiency<br>Conv-Reform. | ✓ | Real-world | PPO | ORM | Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [PopQA](https://arxiv.org/abs/2212.10511), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| ConvSearch-R1 | Conv-Reform. | ✓ | Real-world | GRPO | ORM | Format<br>Rank-Incentive | Step-level | [adlakha2022topiocqa, anantha2021open] |
| MaskSearch | Conver. Reform.<br>R–S Inter. | ✓ | Real-world<br>Curriculum<br>RAMP | DAPO | Rule-based ORM | Format<br>Answer Recall<br>Length penalty | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), zhu2024fanoutqa, [Musique](https://arxiv.org/abs/2108.00573), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Bamboogle](https://arxiv.org/abs/2210.03350), vu2024freshqa] |
| DeepRetrieval | R-Aware Opt. | ✓ | Simulated | PPO | ORM | Format<br>Answer Recall | Single-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), rajpurkar2016squad, thorne2018fever, wadden2020fact] |
| WebThinker | Search Efficiency | ✗ | Real-world | DPO | PRM | Answer EM<br>Tool Calls<br>Length penalty | Single-agent | [rein2024gpqa, mialon2023gaia, wu2025webwalker, phan2025humanity, du2025supergpqa, openthoughts2025open, yuan2025naturalreasoning, li2024numinamath] |
| s3 | R-Aware Opt. | ✓ | Simulated | PPO | Rule-based ORM | Gain Beyond RAG | Module-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573)] |
| R-Search | R–S Inter. | ✗ | Real-world | PPO<br>GRPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Evidence Quality | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| AutoRefine | R–S Inter. | ✗ | Real-world | GRPO | ORM+PRM | Answer F1<br>Retrieval Reward | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| EvolveSearch | R–S Inter. | ✓ | Real-world<br>Self-evolving | GRPO | ORM | Format<br>Answer LLM-Judge | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| O²-Searcher | R–S Inter. | ✓ | Simulated | GRPO | Rule-based ORM | Format<br>Diversity reward<br>Factual reward | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [Hotpot](https://arxiv.org/abs/1809.09600), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| Atom-Searcher | R–S Inter. | ✓ | Real-world<br>Curriculum | GRPO | PRM+Rule-based ORM | Format<br>Answer F1<br>Atomic thought reward | Step-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| ReSum | Ctx-Mem. | ✗ | Real-world | Resume-GRPO | ORM | Answer LLM-Judge | Single-agent | [mialon2023gaia, wei2025browsecomp, zhou2025browsecomp, wei2024measuring, wu2025webwalker, xbench] |
| SFR-DeepResearch | Ctx-Mem.<br>Multi-tool | ✗ | Real-world | REINFORCE | ORM | Answer LLM-Judge | Single-agent | [krishna2024frames, mialon2023gaia, phan2025humanity] |
| MAO-ARAG | P–E Orches. | ✓ | Real-world | PPO | ORM | Format<br>Cost Penalty<br>Answer F1 | Multi-agent | [[NQ](https://aclanthology.org/Q19-1026/), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511), min2020ambigqa] |
| OPERA | P–E Orches. | ✓ | Real-world | MAPGRPO | PRM+ORM | Answerer Reward<br>Planer Reward<br>Rewriter&nbsp;Reward | Multi-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [NQ](https://aclanthology.org/Q19-1026/), tang2024multihop] |
| AI-SearchPlanner | P–E Orches. | ✗ | Real-world | PPO | ORM | Answer LLM-Judge<br>Trajectory Rationality | Module-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), [PopQA](https://arxiv.org/abs/2212.10511)] |
| SIRAG | Cooperative | ✗ | Real-world | PPO | PRM | Process LLM-Judge | Multi-agent | [[2WikiMQA](https://arxiv.org/abs/2011.01060), [Hotpot](https://arxiv.org/abs/1809.09600), [NQ](https://aclanthology.org/Q19-1026/), [PopQA](https://arxiv.org/abs/2212.10511)] |
| MMOA-RAG | Cooperative<br>R-aware Opt. | ✗ | Real-world | MA-PPO | Rule-based ORM | Answer F1<br>Efficiency penalty | Multi-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), min2020ambigqa] |
| Tool-Star | Multi tool | ✓ | Real-world | REINFORCE++<br>GRPO<br>DPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [lightman2023let, hendrycks2021measuring, cobbe2021training, wu2025webwalker, [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350)] |
| WebWatcher | Multi tool<br>Multi-modal | ✓ | Real-world | GRPO | ORM | Format<br>Answer LLM-Judge | Single-agent | [phan2025humanity, li2025mm, fu2025livevqa, jiang2024mmsearch, cheng2025simplevqa] |
| Visual-ARFT | Multi-modal<br>Multi-tool<br>Adapt-Search | ✓ | Real-world | GRPO | Rule-based ORM+PRM | Format<br>Answer F1<br>Query Semantic Sim. | Single-agent | [liu2025matsearch] |
| VRAG-RL | Multi-modal<br>Search Efficiency | ✓ | Simulated | GRPO | ORM | Format<br>Answer LLM-Judge<br>Retrieval Efficiency | Single-agent | [tanaka2023slidevqa, wang2025vidorag, ma2024mmlongbench] |
| MMSearch-R1 | Multi-modal <br>Search Efficiency | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer EM<br>Search Penalty | Single-agent | [wu2025mmsearch, chen2023can, jiang2024mmsearch, cheng2025simplevqa, fu2025livevqa] |
| GRAIL | Adapt-Search<br>Struct-Nav. | ✓ | Real-world<br>Graph Env. | GRPO | PRM | Process LLM-Judge | Single-agent | [berant2013webquestions, puerto2021metaqa, talmor2018web] |
| DynaSearcher | Struct-Nav. | ✗ | Real-world<br>Graph Env.<br>KG+Doc Search | GRPO | Rule-based ORM | Format<br>Answer F1<br>Information Gain<br>Retrieval Penalty | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), krishna2024frames] |
| HARIS | R-S Inter. | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer Accuracy<br>Decision Accuracy | Multi-agent | [ma2024ex, jiang2020hover, si2024checkwhy] |
| DeepNote | Adapt-Search<br>Conv-Reform. | ✗ | Real-world | DPO | - | - | Single-agent | [[Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), geva2021strategyqa, stelmakh2022asqa] |
| DeepResearcher | Adapt-Search<br>Search Efficiency<br>Ctx-Mem. | ✗ | Real-world | GRPO | Rule-based ORM | Format<br>Answer F1 | Module-level | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060)] |
| SWiRL | Adapt-Search<br>R-S Inter. | ✓ | Real-world | PPO | PRM | Step LLM-Judge | Step-level | [[Hotpot](https://arxiv.org/abs/1809.09600), [Musique](https://arxiv.org/abs/2108.00573), wu2024cofca, cobbe2021training, qi2021answering] |
| WebDancer | Multi tool | ✓ | Real-world | DAPO | ORM | Answer EM | Single-agent | [mialon2023gaia, wu2025webwalker, zhou2025browsecomp, wei2025browsecomp] |
| MedResearcher-R1 | Adpt-Search<br>Multi-Tool | ✓ | Real-world<br>Medical Tool | GRPO | ORM | Answer Acc<br>Response Quality<br>Efficiency penalty | Single-agent | [xbench, mialon2023gaia, chen2025medbrowsecomp] |
| Lucy | Search Efficiency<br>R–S Inter. | ✓ | Real-world<br>SLMs | DAPO | Rule-based ORM | Format/XML validity<br>Answer EM<br>Tool exec. success<br>Visit/Search ratio<br>Efficient thinking | Single-agent | [wei2024measuring] |
| ASearcher | R-S Inter.<br>Ctx-Mem.<br>Multi-tool | ✓ | Real-world<br>Browser Env.<br>Asynchronous | GRPO | ORM | Answer LLM-Judge | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [PopQA](https://arxiv.org/abs/2212.10511), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [Bamboogle](https://arxiv.org/abs/2210.03350), krishna2024frames, mialon2023gaia, xbench] |
| WebExplorer | Ctx-Mem.<br>Conv-Reform. | ✓ | Real-world<br>Curriculum | GRPO | Rule-based ORM | Format<br>Answer EM | Single-agent | [zhou2025browsecomp, wei2025browsecomp, mialon2023gaia, wu2025webwalker, krishna2024frames, xbench, phan2025humanity] |
| WebResearcher | Multi-tool | ✓ | Real-world<br>Curriculum | GSPO | Rule-based ORM | Answer EM | Single-agent | [phan2025humanity, mialon2023gaia, wei2025browsecomp, zhou2025browsecomp, xbench, krishna2024frames] |
| RECON | Ctx-Mem. | ✓ | Real-world | PPO | Rule-based ORM | Answer EM | Single-agent | [[NQ](https://aclanthology.org/Q19-1026/), [TriviaQA](https://arxiv.org/abs/1705.03551), [Bamboogle](https://arxiv.org/abs/2210.03350), [Hotpot](https://arxiv.org/abs/1809.09600), [2WikiMQA](https://arxiv.org/abs/2011.01060), [Musique](https://arxiv.org/abs/2108.00573), [PopQA](https://arxiv.org/abs/2212.10511)] |
| AgentGym-RL | Cooperative<br>Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| Chain-of-Agents | Cooperative<br>Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| Verl | Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |
| VerlTool | Multi tool | - | - | - | - | - | Unified RL Agentic Framework | - |

</div>
</details>


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

### Where RL is Applied: Optimization Scopes
#### Agent-level
#### Step-level
#### Module-level
#### System-level

## Evaluation
### Metrics

### Datasets