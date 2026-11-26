# Contributing to Awesome MLSys Security

Thank you for helping maintain this curated list. This document defines paper eligibility, venue priorities, submission formatting, and the manual review workflow.

## 1. Scope & Eligibility

Every proposed paper must meet **both** requirements:

1. **Venue quality and publication status.** The paper must be accepted to or published in a peer-reviewed conference ranked **CORE/ICORE A* or A** in the applicable ranking edition, or in another **high-quality peer-reviewed conference or journal explicitly approved by the maintainers**. Use the [official CORE/ICORE rankings](https://portal.core.edu.au/conf-ranks/) to check conferences; these rankings do **not** rate journals. Verify publication status through official proceedings, publisher records, or an official conference acceptance announcement. Priority venues are discovery sources, **not automatic acceptance**.
2. **Direct MLSys Security relevance.** The paper must study a concrete security or privacy issue tied to an ML system component, such as KV caches, inference runtimes, scheduling, serving isolation, model compression, distributed ML, GPU/accelerator execution, model serialization, or deployment frameworks. Performance-only papers and generic jailbreak/alignment papers without an explicit system-level attack surface or defense are out of scope.

**Do not include:** arXiv-only preprints, under-review submissions, unverifiable acceptance claims, or workshop-only papers (unless the maintainer expressly approves an exception). Papers with independently verified acceptance but no published proceedings may be labeled **[Venue Year, to appear]**. An arXiv full-text link is permitted only after acceptance is verified and when no official full-text link is available.

**Current curation priority:** Emphasize attacks, vulnerabilities, integrity, availability, memory safety, side channels, and defenses involving ML systems. **Privacy-preserving ML is not a priority for new discovery at present**, including general-purpose MPC, differential privacy, federated learning, confidential inference, and ZKP systems. This is a *search priority*, not a retroactive exclusion: keep existing entries, and allow relevant privacy research when explicitly approved by the maintainer (e.g., CompLeak).

## 2. Priority Venues

These are priority sources to search during **manually triggered** updates. Ranking and publication eligibility must still be verified for every proposed paper.

| Area | Priority conferences |
| --- | --- |
| Security & Privacy | IEEE Symposium on Security and Privacy (IEEE S&P), USENIX Security, ACM CCS, NDSS |
| Operating & General Systems | SOSP, OSDI, EuroSys, ASPLOS, USENIX ATC |
| ML & Distributed Systems | MLSys, NSDI, SoCC, PPoPP |
| Computer Architecture | ISCA, MICRO, HPCA |

Other conferences and journals may qualify if they pass the venue-quality requirement or receive explicit maintainer approval.

## 3. Submission Guidelines

- Search the latest `main` branch and open PRs before proposing additions; do not duplicate a paper across categories.
- Place each paper in its **primary topic category** in `README.md`. Propose a new category only when existing headings do not fit.
- Prefer official publisher, proceedings, or conference links. Add code links when available.
- Follow the README entry style:

  ```markdown
  - **[Venue Year]** *Paper Title* [[Paper](https://official-paper-url)] [[Code](https://code-url)]
    - `Target: System component` | `Attack: Threat` | `Defense: Mitigation`
  ```

- Metadata lines are optional; keep them concise and factual. Include only applicable labels (e.g., `Target`, `Attack`, `Defense`, `System`).
- For an accepted but unpublished paper, use **[Venue Year, to appear]**, supported by independent acceptance evidence.
- Paper selection, titles, venues, links, and category placement must be checked before merging.

## 4. Maintenance Workflow

Updates are **manual**, initiated by the maintainer rather than run on an automatic schedule.

1. Read the latest `main` README and this `CONTRIBUTING.md`; inspect open PRs to prevent duplicate proposals.
2. Search priority venues and other eligible sources, focusing on papers not yet listed. Verify the venue/ranking, acceptance/publication, systems-security relevance, and authoritative links.
3. Document proposed additions and borderline/excluded candidates; obtain maintainer approval before adding papers when requested.
4. Create an isolated branch, update `README.md`, and open a **Draft Pull Request**. Never write directly to `main`.
5. In the PR description, summarize additions, their categories, verification sources, and any maintainer-approved exceptions.
6. Leave review, final approval, and merging to the maintainer. Do **not** auto-merge.

For policy changes, use a separate PR from paper additions where practical.
