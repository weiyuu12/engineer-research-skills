# Search and Citation

Use this reference for frontier scans, latest literature, citation support, and any
request where exact sources matter.

## Source priority

Prefer primary or stable sources:

1. Publisher article pages and PDFs.
2. arXiv, IEEE Xplore, ACM Digital Library, SpringerLink, ScienceDirect, Wiley, MDPI,
   PubMed when biomedical engineering is relevant.
3. Crossref, Semantic Scholar, OpenAlex, Google Scholar snippets only as discovery aids.
4. Official project pages, code repositories, benchmark leaderboards, and dataset pages.

Do not rely on secondary blog summaries unless the user asks for non-academic context.

## Verification rules

- Verify title, authors, year, venue, DOI/arXiv ID, and publication status before giving
  a citation-ready recommendation.
- For "latest", "frontier", "recent", or "state of the art", search the web or academic
  sources because this changes over time.
- If a paper is a preprint, say it is a preprint unless a peer-reviewed version is found.
- If venue or DOI cannot be verified, label the entry as unverified instead of guessing.

## Literature scan output

For a topic scan, produce:

- **检索口径**: keywords, time window, domains, and inclusion/exclusion logic.
- **主线分类**: group papers by technical route rather than by year only.
- **代表文献表**: paper, year, venue/status, method, evidence, limitation, why it matters.
- **可写进中文论文的判断**: background trend, unresolved gap, and how the user's work can
  position itself.
- **下一轮检索词**: English keywords and neighboring concepts to continue searching.

## Citation support

When the user gives a Chinese claim and asks for references:

1. Split the claim into citable subclaims.
2. Search or verify sources for each subclaim.
3. Prefer recent high-quality sources for frontier claims and foundational sources for
   definitions or classic methods.
4. Return a claim-to-source map with short Chinese notes explaining why each source fits.

