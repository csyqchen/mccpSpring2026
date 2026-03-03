# Writing Feedback — CHEN Yuqi (陳鈺淇)

## Feedback on CHEN Yuqi's First Draft: Introduction and Literature Review

**Student:** CHEN Yuqi (陳鈺淇)
**Topic:** Community Search in Public-Private and Dynamic Graph Settings
**Date:** 2 March 2026
**Reviewer:** Simon Wang (with AI-assisted analysis)

**Your draft:** writing/writingSampleCollection/firstDraft.md
**Your reflection:** writing/writingSampleCollection/reflection.md
**Assessment rubric:** writing/assessment/writing_instructions_formatted.md

---

## Overall Assessment

Your draft covers a well-defined research topic (community search under public-private and dynamic graph settings) and demonstrates clear awareness of the move structure. The Introduction follows a logical Move 1 → Move 2 → Move 3 progression, and the Literature Review is organized thematically with a clear transition from structural to attributed community search. You have also correctly identified the research gap (most methods assume static, fully accessible graphs). However, the draft needs improvement in three key areas: (1) the Introduction is a single long paragraph without clear move boundaries; (2) the Literature Review tends toward description rather than critical analysis — it summarizes what papers do but rarely evaluates their limitations; and (3) citations are present but need to be more specific about what each paper contributes. Your reflection shows excellent self-awareness — you identify "critical analysis rather than just summarization" as your biggest challenge, which is exactly the area that needs the most work.

**Estimated current level:** Satisfactory to Good (7 range) — The structure and topic identification are solid. Deepening the critical analysis and improving move visibility will push this to Good or above.

---

## Part 1: Introduction Feedback

### What Works Well

- The topic is clearly defined: "community search under public-private and dynamic graph settings"
- Move 1 effectively establishes community search as an important research area
- Move 2 identifies a genuine gap: existing methods assume static, fully accessible graphs
- Move 3 states the research direction clearly

### Issue 1: The Introduction Is a Single Paragraph

Your entire Introduction is one long paragraph containing Moves 1, 2, and 3 compressed together. This makes it hard for readers to follow the argument progression.

**Action:** Split into three clearly separated paragraphs:
- **Paragraph 1 (Move 1):** Establish the territory — what is community search, why does it matter, what has been achieved so far. Include 3–5 citations.
- **Paragraph 2 (Move 2):** Identify the gap — most existing work assumes static, globally accessible graphs. Real-world networks are complex (public-private data, dynamic structure). This is explicit and well-stated but should be its own paragraph.
- **Paragraph 3 (Move 3):** State your research purpose — what specific contribution does this work make? How does your approach differ from existing methods?

### Issue 2: Move 2 Needs Stronger Gap Language

Your gap identification is correct but could be more assertive:

**Your version:** "Although community search has been extensively studied, most existing studies still assume that the graph is static and globally accessible."

**Stronger version:** "Despite substantial progress in community search, a critical assumption underpins nearly all existing methods: the graph is static and fully observable. This assumption fails in practice for at least two reasons. First, real-world social networks contain private nodes and edges that are invisible to query users [citation], creating a public-private partition that current methods cannot handle. Second, networks evolve continuously — edges are added and removed, node attributes change — yet existing algorithms require the full graph to be available at query time [citation]."

### Issue 3: Move 3 Needs More Specificity

Your Move 3 says: "we explore how to extend existing community search models to support more realistic and complex graph networks." This is too general. What specifically do you propose?

**Suggestion:** "In this work, we propose [specific contribution], a community search framework that operates under two realistic constraints: (1) partial graph visibility, where only public edges are accessible and private subgraphs must be handled through [mechanism]; and (2) temporal graph evolution, where community membership must be maintained efficiently as the graph changes. Our framework achieves [brief result preview] on [benchmark/dataset]."

---

## Part 2: Literature Review Feedback

### What Works Well

- **Good thematic organization:** You group literature into (a) structural community search and (b) attributed community search, then identify gaps
- **Appropriate citations:** You cite Fang et al., Huang et al., Chen et al., Zhu et al., and Jiang et al. — showing engagement with key papers
- **The gap identification (Move 3) is clear:** "community search under public-private graph settings has not been systematically investigated"
- **Move 4 (conclusion) effectively summarizes** the state of the field

### Issue 4: Description Without Critical Analysis

This is the central weakness, and you already identified it in your reflection: "It is relatively easy for me to understand and summarize existing methods, but identifying deeper limitations and connecting them to meaningful future directions is more difficult."

**Your sentence (description):** "Fang et al. review community search algorithms based on structural cohesiveness metrics such as k-core, k-truss, k-clique, and k-edge-connected components, and compare them across different graph types."

**With critical analysis:** "Fang et al. provide a comprehensive survey of structural community search, comparing k-core, k-truss, k-clique, and k-edge-connected formulations across different graph types. However, their analysis is restricted to static graphs where the full topology is known. The implicit assumption — that community structure is stable and globally observable — limits the applicability of these models to real-world networks where edges are added or removed dynamically, and where privacy constraints create partial visibility."

### Issue 5: Attributed Community Search Section Needs Deeper Comparison

You list five papers on attributed community search but present them sequentially without comparing their approaches. Consider:

**Synthesis pattern:** "Approaches to attributed community search differ fundamentally in how they balance structural cohesion with attribute relevance. Huang et al. maximize attribute similarity within structurally dense subgraphs, while Fang et al. use hierarchical indexing (CL-tree) to efficiently combine k-core structure with keyword matching. Chen et al. take a different approach entirely, eliminating the need for structural parameters by using contextual keyword matching. These design choices involve tradeoffs: parameter-free methods are more flexible but may sacrifice structural guarantees, while index-based methods are efficient but require expensive preprocessing that must be repeated when the graph changes."

### Issue 6: Move 3 (Research Gaps) Could Be Expanded

You identify two gaps:
1. Public-private graph community search is unexplored
2. Dynamic graph challenges community maintenance

Consider adding a third: "Third, the interaction between privacy constraints and graph dynamics has not been studied — a particularly challenging setting where both the graph topology and its visibility change simultaneously."

---

## Part 3: Reflection and Process Feedback

### What Works Well in Your Reflection

- **Excellent self-diagnosis:** "My biggest challenge is conducting critical analysis rather than just summarization" — this is exactly right, and addressing it will significantly improve your writing
- **Good process description:** Your five-step writing process (define topic → identify concepts → outline → draft → revise) is systematic
- **Mature AI usage:** "AI cannot replace independent thinking. Determining the research direction and identifying existing research gaps still require my own analysis and judgment" — this is an important and correct observation

### Issue 7: Turn Your Self-Diagnosis into Action

You know that critical analysis is your weakness. Here's a practical technique: for every paper you cite, ask three questions:
1. **What does it assume?** (e.g., static graph, full visibility, specific cohesion metric)
2. **Where does it fail?** (e.g., dynamic networks, large-scale graphs, partial information)
3. **How does its failure connect to your research?** (e.g., your work addresses this specific limitation)

If you can answer these three questions for each cited paper, your literature review will naturally become critical rather than descriptive.

---

## Summary of Priority Actions

| Priority | Action | Impact |
|----------|--------|--------|
| 🔴 High | Split Introduction into three clearly separated move paragraphs | Makes argument structure visible |
| 🔴 High | Add critical analysis to literature review — evaluate limitations, not just describe methods | Transforms description into argument |
| 🔴 High | Make Move 3 more specific — what exactly does your work contribute? | Clarifies research value |
| 🟡 Medium | Add synthesis/comparison paragraphs across cited papers | Shows deeper engagement |
| 🟡 Medium | Strengthen Move 2 gap language with explicit failure examples | Makes gap more compelling |
| 🟢 Lower | Add a third research gap about privacy-dynamics interaction | Expands contribution scope |

---

## Next Steps

1. Read the [full writing instructions](https://github.com/tesolchina/mccpSpring2026/blob/main/writing/assessment/writing_instructions_formatted.md) carefully
2. Restructure the Introduction into three clear move paragraphs
3. Revise the Literature Review with critical analysis for each cited paper
4. Add synthesis paragraphs comparing approaches
5. Submit by **15 March 2026** via Moodle forum and Turnitin
