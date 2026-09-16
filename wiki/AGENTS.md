# Wiki maintenance instructions

## Scope and working style

Maintain a student research wiki for a 45-minute interview with Dana and subsequent interview follow-up. Follow the [approved specification](../docs/superpowers/specs/2026-09-11-meridian-research-wiki-design.md), [implementation plan](../docs/superpowers/plans/2026-09-11-meridian-research-wiki.md), and existing repository instructions. The user's current authorization determines which tasks may be executed.

Before changing files, explain the proposed change and its purpose in plain language. Afterward, explain what changed and what the user should review or decide. Ask before resolving choices left open by the approved design and plan. Keep Markdown simple and readable.

Treat Pasadena as a candidate to evaluate, not a conclusion to substantiate. Keep Dana's business questions and Marcus's technical questions separate. Do not extend maintenance beyond interview follow-up without agreement.

## Data handling comes first

Follow the [data-handling checklist](../docs/data-handling-checklist.md). These instructions govern the wiki maintainer's handling of sources in `raw/` as well as wiki pages. A file's location does not establish permission to read it with AI.

- Students receive aggregated summaries only. Customer and employee data, including excerpts, must never enter AI tools.
- The brief permits AI use of sales totals by store and week and store attributes. Aggregation of other data does not automatically authorize AI use. Obtain written Meridian clarification before using other project data categories with AI.
- Screen research documents and project narrative for prohibited contents; permission to use a narrative does not authorize underlying restricted records.
- Before opening interview notes, obtain confirmation that a student has checked accuracy, removed restricted information, and approved the notes for AI processing. Confirm the approved source location; do not scan for or open unreviewed notes.
- Student approval cannot override Meridian's restrictions. If unexpected restricted data appears, stop using it and follow the checklist's stop-and-notify procedure. Do not copy restricted contents into logs or notifications. Do not send notifications through tools without explicit authorization.
- Keep the working wiki within the approved project environment. Do not publish it or the repository. Dana receives reviewed interview materials; apply Meridian's approval requirements to every release outside the project team.
- Apply agreed access, retention, and deletion rules to sources, pages, notes, and exports. Unresolved owners, systems, transfer methods, aggregation rules, or deadlines do not authorize data transfer or access.

## Files and source preservation

Use relative Markdown links and descriptive lowercase filenames. Organize future content into `topics/`, `sources/`, and `interview/`. Create only files within the currently authorized task.

Preserve original approved source notes in `raw/` without rewriting them. Record corrections or new versions as distinct sources linked to the earlier version. Keep evolving synthesis and review history in the wiki and log.

Use sequential external source IDs such as `S001`; use the same ID for the raw note and its wiki summary, with filenames such as `raw/s001.md` and `wiki/sources/s001.md`. Assign IDs only when incorporating approved sources. Preserve source notes by default; retain full documents only when needed and permitted.

Begin each external source note with a simple metadata table containing these fields:

| Field | What to record |
|---|---|
| Source ID | The assigned stable ID |
| Title | The source's title |
| Publisher or author | The identified organization or author |
| Original URL | A direct link to the source |
| Publication date | The stated date, or `Not provided by source` |
| Access date | The actual date accessed |
| Review status | The actual status when the note is preserved |
| Approval reference | The conversation or other record approving incorporation |

Never guess missing dates or fabricate approvals. Separate clearly labeled excerpts from student or AI summaries. Record access limitations and relevant limits of the evidence. Put later changes to review status in the wiki and append-only log, preserving the approved raw note.

## Topic pages and evidence

Use these four sections on every topic page:

1. **Meridian statements:** Attribute statements to the brief or an approved interview source. These establish what Meridian said, not independent verification of every claim.
2. **External findings:** Cite the original source and linked source summary. Explain relevance and limits for Meridian; do not present industry findings as Meridian-specific facts.
3. **Team interpretations and hypotheses:** Label reasoning explicitly and link its supporting evidence. Do not turn a plausible interpretation into an established fact.
4. **Open questions:** State each question, why it matters, and its intended respondent. Do not invent decisions, owners, deadlines, or interview answers.

Place citations beside substantive claims so readers can trace them. Link related topics and source summaries instead of duplicating authoritative content. If evidence conflicts, retain the attributed claims, explain the disagreement, and identify the clarification needed.

## Incorporating a source

When source research is authorized, aim for approximately 6–8 strong external sources across grocery performance, expansion criteria, and the regional market. Prefer primary evidence; supplement with credible industry analysis when useful. A smaller evidence set requires user approval. Do not pad the count with weak sources.

For each source individually:

1. Assess relevance, provenance, currency, limitations, and suitability for AI processing. Do not expose confidential Meridian details in public search queries.
2. Read the accessible source and discuss takeaways, limitations, and proposed wiki updates with the user. If inaccessible, disclose the limitation and propose an alternative; never claim verification without access.
3. Wait for user approval before incorporating the source or its findings into the wiki. Silence is not approval.
4. Preserve the approved source note and write its linked wiki summary. Update affected topics and questions, keeping evidence categories distinct.
5. Update the index, cross-references, and log. Check the changed links and summarize the changes for the user.

Treat screened interview notes as a new source: screening must precede AI access, and approval of proposed updates must precede incorporation. Preserve explicit stakeholder decisions separately from student interpretations and keep unanswered questions visible.

## Answering questions

Start with the [index](index.md), then read relevant pages and their sources. Answer with citations and distinguish evidence, interpretation, and unknowns. Say when the wiki does not support an answer.

If an answer would be useful as a lasting page or revision, propose the content and affected files to the user. Obtain approval before saving it; do not silently convert chat answers into wiki knowledge. Update navigation and append a log entry for approved saved answers.

## Navigation, logging, and maintenance

The [index](index.md) is the entry point. List every other wiki page with a relative link and one-line description, grouped by purpose. Link only to existing files; add entries as pages are created.

The [log](log.md) is chronological and append-only. Each dated entry records activity, affected pages, the reason for the change, supporting sources, and actual approvals. Append corrections rather than rewriting earlier entries. Git history supplements the log; it does not replace it.

After approved updates, check affected links and index entries. Before interview readiness and after follow-up, review the wiki for:

- Broken local links and heading anchors; external links requiring manual checks.
- Pages absent from the index or missing useful cross-references.
- Substantive claims without supporting citations or clear claim labels.
- Contradictions, stale claims, and limitations concealed by summaries.
- Unapproved sources, restricted contents, or unsupported approval claims.
- Questions that lack rationale or a respondent, and interpretations presented as decisions.

Use the implementation plan's read-only link check and manual review; do not add a testing framework. A passing file-link check does not establish factual accuracy, safe handling, or valid external links. Record what was checked and unresolved gaps honestly in the log. Discuss proposed substantive changes before making them.
