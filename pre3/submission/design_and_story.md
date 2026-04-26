# Pre3 (3MT) — Design & Story Notes

This submission reuses the core story from `pre2/poster.html` (Public–Private graph setting, challenges, and the three-phase method overview), but compresses it into a **single 3MT-style slide** plus **audio** for a non-specialist audience.

---

## 1) Slide design (what I did and why)

- **Machine-readable format**: The slide is written in **HTML** with real text (headings, paragraphs, lists). Images are supportive only.
- **One-slide rule**: The layout is a single 16:9 canvas (`1280×720`) with a clear hierarchy: title → background → motivation → method (brief).
- **Visual focus**:
  - **Network illustration** (`network.png`) to show the idea of a social graph quickly.
  - **Platform logos** (`social_logos.png`) to anchor the story in familiar apps (Weibo / Xiaohongshu / TikTok / Facebook).
  - **Naïve vs desired** diagram (`naive_vs_desired.png`) to communicate the motivation in one glance (costly vs efficient integration).
- **No “image-only” content**: Instead of embedding screenshots of definitions, the slide **extracts the key points into text** (e.g., what community search is; what public-private graphs are). This keeps it machine-readable and easier to follow.
- **Low jargon**: I avoid formal definitions and equations. The method section keeps only **one sentence per phase**.
- **Accessibility**: All images include `alt` text. The slide remains understandable even if an image fails to load.

---

## 2) Storytelling choices (how I explain to non-specialists)

- **Everyday framing**:
  - **Public vs private**: “Some relationships are visible to everyone; some are only visible to you.”
  - **Different views**: “Each user sees a different version of the same network.”
- **Problem in plain language**: “Find a tightly connected group around a person in that person’s view.”
- **Motivation via contrast**: Use the slide’s **naïve vs desired** diagram to explain why a straightforward solution becomes slow/costly.
- **Examples**: Mention familiar platforms (from the logos) as examples of private relationships (e.g., hidden followers / hidden friend lists).
- **Method kept brief**: I do **not** expand definitions (e.g., PP-FP-tree, coreness). I keep it as three “moves” (select → expand → validate).
- **Close with significance**: Emphasize that the goal is to enable **fast, personalized** community search that reflects realistic public/private visibility.

---

## 3) What I will say (not a script)

During recording I will speak from key points only:

- Background: public + private edges/attributes → different user views
- Motivation: naïve approach is slow/costly → need efficient integration
- Method: Phase-I / II / III (one sentence each, matching the slide)
- Wrap-up: personalized community search that is efficient and practical

Note: I will use note cards and avoid reading a full script, as required.

