# My Final Draft

## Source Information

**Date written:** Mar 14th, 2026

**Context:** For the course assignment and my future research work.

**Status:** Final draft.

---

## Introduction
Community Search has been extensively studied in graph data analytics, aiming to identify densely connected subgraphs. It plays an important role in social network analysis and collaborative recommendation. In the past ten years, dense subgraph structures have been deeply studied. Based on these models, researchers have further introduced attribute constraints, making the community with richer semantics. 

Although community search has been extensively studied, most existing studies still assume that the graph is static and globally accessible. However, real-world networks are more complex, including public-private graphs and dynamic graphs. Therefore, it is necessary to extend community search to more realistic and complex scenarios. Motivated by this observation, we explore how to extend existing community search models to support more realistic and complex graph networks. In particular, we focus on community search under public-private and dynamic graph settings.

We mainly investigate attributed community search in two underexplored settings: public-private graphs, where not all edge information may be publicly accessible in various graph data, and dynamic graphs, where graph structure changes over time. The challenges are mainly twofold. Firstly, the community structure and shared keywords may be independent of each other in the community model, so the two-dimensional quality requirements needs to be considered simultaneously. Secondly, most related studies in attributed community search build offline index in advance for searching efficiency. But for the public-private graphs, since each user has its own private graph, it would be expensive in storage to maintain seperate indexes for all users. Similarly, it is also hard for dynamic graphs to make static indexing. To address these challenges, we aim to design a compact index for each user in public-private graphs and dynamic graphs. Our approach focuses on keeping the index lightweight while balancing community quality and querying efficiency.

---

## Literature Review
Our work is closely related to community discovery, attributed community search, and public-private network analysis, community search in dynamic graphs.
Community discovery has been widely studied in graph data analysis, particularly from a structural perspective. Existing studies are generally categorized into two main directions: community detection and community search. Community detection aims to identify cohesive subgroups throughout the entire graph, while community search is a query-based process that retrieves the most relevant community for a given node or a set of nodes. Fang et al. review community search algorithms based on structural cohesiveness metrics such as $k$-core, $k$-truss, $k$-clique, and $k$-edge-connected components, and compare them across different graph types, including keyword-based, temporal, and spatial graphs [1](#ref-1).

Beyond structural definitions, attributed community search incorporates semantic information into cohesive subgraphs. Huang et al. propose attributed truss communities that maximize attribute relevance within dense subgraphs [2](#ref-2). Fang et al. design the CL-tree, a hierarchical tree index combining $k$-core structure and keyword information for efficient attributed community search [3](#ref-3). Chen et al. introduce a parameter-free contextual model that retrieves communities using query keywords without preset structural parameters [4](#ref-4). Zhu et al. focus on cohesive attributed communities while maintaining structural connectivity [5](#ref-5), and Jiang et al. extend community search to large star-schema heterogeneous information networks [6](#ref-6).

Although these studies have greatly improved structural and attributed community search models, most of them are built on simplified assumptions. In particular, many approaches assume that the graph is static and fully accessible. Even when temporal graphs or keyword-based search are considered, the main focus remains on improving structural cohesion or attribute matching. The complexity of real-world environments, such as privacy constraints or personalized graph views, is rarely addressed. As a result, current community search methods may not be well suited for realistic and dynamic graph scenarios. Based on the existing literature, there are several research gaps. First, community search under public-private graph settings has not been systematically investigated. Second, dynamic graph introduces structural instability that challenges traditional community maintenance and query processing strategies. 
There are already some studies related to public-private graphs, and also some work on dynamic graphs aiming to update index efficiently for community search.

Existing works has explored some querying tasks on public-private graphs. Chierichetti et al. propose scalable algorithms for computing key metrics in public-private social networks [7](#ref-7), including reachability [10](#ref-10), centrality [8](#ref-8), and shortest paths [9](#ref-9). Archer et al. specifically study reachability in directed graphs with public, private, and protected nodes [10](#ref-10). Huang et al. release the PP-DBLP dataset derived from DBLP for evaluation purposes [11](#ref-11). Ebadian et al. present an efficient method for finding $k$-truss in public-private graphs [12](#ref-12). Jiang et al. introduce a three-stage public-private keyword search framework [13](#ref-13). Yu et al. define a PP-graph model and propose the pp-core number to measure user importance [14](#ref-14). Overall, these work focus on network analysis or keyword search, which means attributed community search in public-private graphs has not been explored.

For dynamic graphs, related work focuses on maintaining community search results under continuous updates. Tantipathananandh et al. study how communities evolve in dynamic social networks and propose methods to detect structural changes over time [15](#ref-15). Huang et al. examine querying $k$-truss communities in large, dynamic graphs, emphasizing efficient update handling [16](#ref-16). Jiang et al. develop Vizcs for online searching and visualizing communities in dynamic graphs [17](#ref-17). Xu et al. propose efficient triangle-connected truss community search under dynamic updates [18](#ref-18). Lu et al. study time-optimal $(k, p)$-core community search in dynamic graphs [19](#ref-19). Li et al. study reliable community search over dynamic bipartite graphs [20](#ref-20). However, these studies only focus on community search on structural models in dynamic graphs, without integrating attributes. Moreover, most of their ways to handle with dynamic graphs is to maintain the index with frequent changes, which remains relatively expensive. Thus, attributed community search under dynamic updates remains underexplored.

In summary, community search research has achieved substantial progress in structural modeling and attribute integration. However, as graph data becomes increasingly dynamic and personalized, extending community search frameworks to complex graph environments such as public-private and evolving graphs remains an important direction for future research. To the best of our knowledge, this is the first study to formulate and examine community search on attributed public-private networks and dynamic graphs. We aim to fill this gap by jointly considering attribute relevance, structural cohesiveness, and update efficiency under both settings.


---



## Declaration of Generative AI and AI-assisted technologies in the writing process
The content of the paper was not generated by generative AI, and AI tools were used only to improve the writing.

---

## References
[1] <a id="ref-1"></a> Fang Y, Huang X, Qin L, et al. A survey of community search over big graphs[J]. The VLDB Journal, 2020, 29(1): 353-392.<br>
[2] <a id="ref-2"></a> Huang X, Lakshmanan L V S. Attribute truss community search[J]. arXiv preprint arXiv:1609.00090, 2016.<br>
[3] <a id="ref-3"></a> Fang Y, Cheng C K, Luo S, et al. Effective community search for large attributed graphs[J]. Proceedings of the VLDB Endowment, 2016.<br>
[4] <a id="ref-4"></a> Chen L, Liu C, Liao K, et al. Contextual community search over large social networks[C]//2019 IEEE 35th International Conference on Data Engineering (ICDE). IEEE, 2019: 88-99.<br>
[5] <a id="ref-5"></a> Zhu Y, He J, Ye J, et al. When structure meets keywords: Cohesive attributed community search[C]//Proceedings of the 29th ACM International Conference on Information & Knowledge Management. 2020: 1913-1922.<br>
[6] <a id="ref-6"></a> Jiang Y, Fang Y, Ma C, et al. Effective community search over large star-schema heterogeneous information networks[J]. Proceedings of the VLDB Endowment, 2022, 15(11): 2307-2320.<br>
[7] <a id="ref-7"></a> Chierichetti F, Epasto A, Kumar R, et al. Efficient algorithms for public-private social networks[C]//Proceedings of the 21th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. 2015: 139-148.<br>
[8] <a id="ref-8"></a> Boldi P, Vigna S. In-core computation of geometric centralities with hyperball: A hundred billion nodes and beyond[C]//2013 IEEE 13th International Conference on Data Mining Workshops. IEEE, 2013: 621-628.<br>
[9] <a id="ref-9"></a> Das Sarma A, Gollapudi S, Najork M, et al. A sketch-based distance oracle for web-scale graphs[C]//Proceedings of the third ACM international conference on Web search and data mining. 2010: 401-410.<br>
[10] <a id="ref-10"></a> Archer A, Lattanzi S, Likarish P, et al. Indexing public-private graphs[C]//Proceedings of the 26th International Conference on World Wide Web. 2017: 1461-1470.<br>
[11] <a id="ref-11"></a> Huang X, Jiang J, Choi B, et al. Pp-dblp: Modeling and generating attributed public-private networks with dblp[C]//2018 IEEE International Conference on Data Mining Workshops (ICDMW). IEEE, 2018: 986-989.<br>
[12] <a id="ref-12"></a> Ebadian S, Huang X. Fast algorithm for K-truss discovery on public-private graphs[C]//Proceedings of the 28th International Joint Conference on Artificial Intelligence. 2019: 2258-2264.<br>
[13] <a id="ref-13"></a> Jiang J, Huang X, Choi B, et al. PPKWS: An efficient framework for keyword search on public-private networks[C]//2020 IEEE 36th International Conference on Data Engineering (ICDE). IEEE, 2020: 457-468.<br>
[14] <a id="ref-14"></a> Yu D, Zhang X, Luo Q, et al. Public-private-core maintenance in public-private-graphs[J]. Intelligent and Converged Networks, 2021, 2(4): 306-319.<br>
[15] <a id="ref-15"></a> Tantipathananandh C, Berger-Wolf T Y. Finding communities in dynamic social networks[C]//2011 IEEE 11th International Conference on Data Mining. IEEE, 2011: 1236-1241.<br>
[16] <a id="ref-16"></a> Huang X, Cheng H, Qin L, et al. Querying k-truss community in large and dynamic graphs[C]//Proceedings of the 2014 ACM SIGMOD International Conference on Management of Data. 2014: 1311-1322.<br>
[17] <a id="ref-17"></a> Jiang Y, Huang X, Cheng H, et al. Vizcs: Online searching and visualizing communities in dynamic graphs[C]//2018 IEEE 34th International Conference on Data Engineering (ICDE). IEEE Computer Society, 2018: 1585-1588.<br>
[18] <a id="ref-18"></a> Xu T, Lu Z, Zhu Y. Efficient triangle-connected truss community search in dynamic graphs[J]. Proceedings of the VLDB Endowment, 2022, 16(3): 519-531.<br>
[19] <a id="ref-19"></a> Lu Z, Zhu Y, Zhong M, et al. On time-optimal (k, p)-core community search in dynamic graphs[C]//2022 IEEE 38th International Conference on Data Engineering (ICDE). IEEE, 2022: 1396-1407.<br>
[20] <a id="ref-20"></a> Li M, Xie Z, Ding L. Reliable Community Search over Dynamic Bipartite Graphs[C]//International Conference on Web Information Systems and Applications. Singapore: Springer Nature Singapore, 2024: 298-307.<br>
