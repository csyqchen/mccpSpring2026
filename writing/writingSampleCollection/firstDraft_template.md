# My First Draft

## Source Information

**Date written:** Feb 14th, 2026

**Context:** For the course assignment and my future research work.

**Status:** Partial draft.

---

## Introduction
Community Search has been extensively studied in graph data analytics, aiming to identify densely connected subgraphs. It plays an important role in social network analysis and collaborative recommendation. In the past ten years, dense subgraph structures have been deeply studied. Based on these models, researchers have further introduced attribute constraints, making the community with richer semantics. Although community search has been extensively studied, most existing studies still assume that the graph is static and globally accessible. However, real-world networks are more complex, including public-private graphs and dynamic graphs. Therefore, it is necessary to extend community search to more realistic and complex scenarios. Motivated by this observation, we explore how to extend existing community search models to support more realistic and complex graph networks. In particular, we focus on community search under public-private and dynamic graph settings.


---

## Literature Review
Community discovery has been widely studied in graph data analysis, particularly from a structural perspective. Existing studies are generally categorized into two main directions: community detection and community search. Community detection aims to identify cohesive subgroups throughout the entire graph, while community search is a query-based process that retrieves the most relevant community for a given node or a set of nodes. Fang et al. review community search algorithms based on structural cohesiveness metrics such as $k$-core, $k$-truss, $k$-clique, and $k$-edge-connected components, and compare them across different graph types, including keyword-based, temporal, and spatial graphs.

Beyond structural definitions, attributed community search incorporates semantic information into cohesive subgraphs. Huang et al. propose attributed truss communities that maximize attribute relevance within dense subgraphs. Fang et al. design the CL-tree, a hierarchical tree index combining $k$-core structure and keyword information for efficient attributed community search. Chen et al. introduce a parameter-free contextual model that retrieves communities using query keywords without preset structural parameters. Zhu et al. focus on cohesive attributed communities while maintaining structural connectivity, and Jiang et al. extend community search to large star-schema heterogeneous information networks.

Although these studies have greatly improved structural and attributed community search models, most of them are built on simplified assumptions. In particular, many approaches assume that the graph is static and fully accessible. Even when temporal graphs or keyword-based search are considered, the main focus remains on improving structural cohesion or attribute matching. The complexity of real-world environments, such as privacy constraints or personalized graph views, is rarely addressed. As a result, current community search methods may not be well suited for realistic and dynamic graph scenarios. Based on the existing literature, there are several research gaps. First, community search under public-private graph settings has not been systematically investigated. Second, dynamic graph introduces structural instability that challenges traditional community maintenance and query processing strategies. 

In summary, community search research has achieved substantial progress in structural modeling and attribute integration. However, as graph data becomes increasingly dynamic and personalized, extending community search frameworks to complex graph environments such as public-private and evolving graphs remains an important direction for future research.


---

## Notes

[Any additional notes about your draft, challenges you faced, questions you have, etc.]
