# Anticipated Q&A — Poster: Efficient Community Search on Attributed Public-Private Graphs

Short bullet replies you can expand orally. Mix **lay** (non-specialist) and **technical** answers as needed.

---

## Role & setting

- **Q: What is a “public-private” graph in one sentence?**  
  - **Lay:** Some friendships or attributes everyone can see; others only certain users can see—so different people literally see different versions of the same network.  
  - **Technical:** A graph with globally visible **public** edges plus user-specific **private** edges/attributes; each user has a **personalized view** \(G_u\).

- **Q: Why not model everything as one big public graph?**  
  - **Lay:** That ignores information users actually rely on privately, and makes community search less realistic for social platforms.  
  - **Technical:** Ignoring private structure/attributes biases cohesiveness and attribute correlation; **ACS-PP** is defined on the **querier’s view**.

---

## Problem & formulation

- **Q: What exactly are you trying to find?**  
  - **Lay:** A tight-knit group around a “query person” that makes sense **for that person’s own view** of the network—not only what strangers see.  
  - **Technical:** A **community containing query vertex** under the user’s view, satisfying **k-core** and **maximizing shared attributes** (ACS-PP).

- **Q: What does k-core mean here?**  
  - **Lay:** Everyone in the group is “well-connected” inside the group—each member has at least *k* neighbors **within** the community.  
  - **Technical:** Induced subgraph where every vertex has degree ≥ *k* inside the subgraph (under the relevant edge set for that view).

---

## Challenges (poster)

- **Q: Challenge I — structure vs. attributes?**  
  - **Lay:** You can have a “clique-like” group that still doesn’t share interests, or shared labels without strong wiring—both matter for a good community.  
  - **Technical:** **Structural cohesiveness** and **homogeneous attributes** need not align; the model must **jointly** enforce both.

- **Q: Challenge II — heterogeneous personalized graphs?**  
  - **Lay:** Every user’s “private corner” of the graph is different, so you cannot assume one template fits all.  
  - **Technical:** Private edges/attributes vary across users → many distinct **personalized views**; query algorithms must respect **per-user** topology/labels.

- **Q: Challenge III — why is indexing expensive?**  
  - **Lay:** If you rebuilt a heavy index for every user’s private view, big networks would choke.  
  - **Technical:** Per-user full indexing is **O(\#users × work)** and not scalable; we need **compact structures** (PP-FP-tree + public coreness index) and **shared** public-graph preprocessing.

---

## Method

- **Q: What is a PP-FP-tree?**  
  - **Lay:** A compact tree that summarizes **which attribute combinations show up often** in a user’s private neighborhood—so we don’t scan everything blindly.  
  - **Technical:** A **public–private frequent pattern tree** built on the query node’s **private** graph to mine frequent attribute sets for **Phase-I** selection.

- **Q: What does Phase-I do?**  
  - **Lay:** Pick the “largest plausible” set of shared attributes that could still form a **k-person** pattern worth expanding.  
  - **Technical:** Extract the **largest common attribute set** from constructed PP-FP-trees such that a **k-node** candidate with those attributes may exist.

- **Q: What does Phase-II do?**  
  - **Lay:** Grow the candidate using **public** connections, but only bring in nodes that are “strong enough” in the public skeleton.  
  - **Technical:** Expand in the **public graph** using **coreness ≥ k** to add nodes that can participate in a **k-core** with the Phase-I attribute pattern.

- **Q: What does Phase-III do?**  
  - **Lay:** Final check: does the group really satisfy the **k-core** rule **and** share the promised attributes, once public and private parts are combined?  
  - **Technical:** **Core decomposition / validation** on the peeled candidate to meet **k-core** and **common-attribute** constraints.

- **Q: Why separate public coreness tree and private PP-FP-tree?**  
  - **Lay:** Public structure is shared by everyone—index once; private patterns are personal—summarize per query node’s private side.  
  - **Technical:** **Amortize** public-graph **coreness** work globally; use **PP-FP-tree** for **attribute-centric** pruning on the private side.

---

## Experiments & case study

- **Q: What do the DBLP2016 / Orkut plots show?**  
  - **Lay:** Your method finds communities **faster** (or with less work) than strong competitors on real network snapshots.  
  - **Technical:** **Community search efficiency** vs. baselines on **DBLP2016** and **Orkut** (see poster panels (a)(b)).

- **Q: What is varied in the scalability tests?**  
  - **Lay:** We make the “private” part of the data **bigger**—more private labels or more private links—and check the method still scales.  
  - **Technical:** **Private attribute cardinality** and **private edge count** vs. runtime/space (panels (a)(b) under scalability).

- **Q: What does the ablation tell us?**  
  - **Lay:** Removing parts of your pipeline hurts **speed** and/or **answer quality**—so each component earns its keep.  
  - **Technical:** Compare **efficiency** and **quality** with components/phases removed (poster ablation row).

- **Q: What is the DBLP2017 case study about?**  
  - **Lay:** Same query, but compare “only what the public sees” versus “public + private view”—the communities can differ a lot.  
  - **Technical:** **Case study on DBLP2017** contrasting **public-only** vs **public-private** communities (poster caption).

---

## Limitations & future work (honest, often asked)

- **Q: What are the main limitations?**  
  - **Lay:** Real platforms change constantly; assumptions about what is “private” may simplify reality; very huge graphs still need engineering care.  
  - **Technical:** Dynamic updates, **approximate** variants for stricter latency, privacy guarantees, and **distribution** (parallel/sharded) are natural extensions.

- **Q: How does this differ from classic community detection?**  
  - **Lay:** Classic methods often assume **one** graph everyone shares; here the graph **depends on who is asking**.  
  - **Technical:** **Personalized views**, **query-dependent** community, and explicit **k-core + attribute** objective (ACS-PP), not modularity-only detection.

---
