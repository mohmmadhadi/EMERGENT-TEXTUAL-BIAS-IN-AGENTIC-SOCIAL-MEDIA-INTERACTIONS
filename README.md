# Emergent Textual Bias in Agentic Social Media Interactions

MSc thesis project investigating whether the identity of the underlying foundation model acts as a latent social attractor in multi-agent polarization dynamics — i.e. whether LLM-driven social media agents built on different base models drift into distinguishable textual "echo chambers" through interaction alone.

## Overview

This repository holds the analysis pipeline for a thesis on emergent textual bias in agentic social media workflows. Multi-agent simulations were run on the [YSocial](https://ysocial.app/) platform, seeding populations of LLM-driven agents on a simulated social network and observing how their posting behavior evolves over time. The core question is whether agents built on different foundation models naturally segregate into distinct stylistic/stance clusters — an echo-chamber effect emerging purely from agent-agent interaction, without any explicit polarization being engineered into the simulation.

**Experimental setup:**
- 29 multi-agent simulation runs
- 100 agents per run
- 11,063 posts collected in total
- 3 foundation models compared as agent backbones

## Repository Contents

| File | Description |
|---|---|
| `Echo_chamber_analysis_temporal.ipynb` | Core analysis pipeline: SBERT sentence embeddings of posts, ensemble stance scoring, Louvain community detection over agent interaction/similarity graphs, and a composite echo chamber score tracked over time. |
| `Visualizations.ipynb` | Generates the figures and plots summarizing echo chamber formation, stance drift, and cross-model comparisons used in the thesis write-up. |

## Methodology

1. **Simulation** — Agent populations are instantiated on YSocial, each agent backed by one of three foundation models, and left to interact (post, reply, follow) over a simulated timeline.
2. **Embedding & stance scoring** — Posts are embedded with SBERT; a stance score is computed per post using an ensemble scoring approach.
3. **Community detection** — Agent-level similarity/interaction graphs are clustered with the Louvain algorithm to identify emergent communities.
4. **Echo chamber scoring** — A composite echo chamber score combines stance homogeneity within communities and separation between them, tracked across the simulation timeline to capture *temporal* emergence rather than a single end-state snapshot.


## Citation

If you reference this work, please cite the thesis:

> Emergent Textual Bias in Agentic Social Media Workflows, M.Sc. Thesis, University of Milan, 2026.
