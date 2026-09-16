# Meridian stakeholder interview research wiki specification

Status: Draft for user review. The design is approved; this specification awaits approval.

## Purpose and scope

Create a student research wiki to prepare for a 45-minute stakeholder interview with Dana Okafor, Meridian Markets’ VP of Operations. Give equal attention to external industry research and gaps in the client brief. Connect both to questions that clarify business priorities, expansion criteria, success measures, and project constraints.

Keep the wiki active through interview follow-up: incorporate approved notes, update answers, and track remaining questions. Continued maintenance throughout the capstone is outside this scope.

Treat Pasadena as a candidate to evaluate, not a conclusion to substantiate. Prepare technical questions for Marcus separately from the main interview with Dana.

## Design references

- [Client brief](../../../raw/client-brief.md)
- [Data-handling checklist](../../data-handling-checklist.md)
- [Karpathy’s LLM wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)

The wiki adapts the pattern’s separation of original sources, synthesized knowledge, and maintenance instructions. It uses Markdown, cross-references, an index, and a chronological log. It does not require a website, Obsidian, a database, or a search service.

## Readers and outputs

Students use the working wiki to examine evidence, develop interpretations, and prepare questions. Dana receives reviewed interview materials rather than the whole working wiki.

The main output is a concise interview pack containing:

1. A briefing on Meridian’s stated situation, relevant research, and uncertainties.
2. Prioritized questions for a 45-minute interview with Dana, with concise supporting context and links to relevant wiki pages.
3. A template for capturing answers, decisions, and follow-up questions.

A separate question list captures technical issues for Marcus. The pack prioritizes consequential uncertainties so essential questions are addressed first. Research should inform neutral questions rather than presume Dana’s answers.

## Information structure

### Original sources

Approved source material belongs in `raw/` and remains unchanged during wiki maintenance. Existing source files are not rewritten to match later interpretations. Corrections or later versions are recorded as distinct sources and linked to the earlier material.

Only material permitted for AI processing may enter the AI-maintained workflow. The raw-source directory is not a destination for restricted customer or employee records.

Each external source has a stable identifier, title, publisher or author, original URL, publication date when available, access date, and review status. Preserve an appropriate source note or permitted copy; do not require full copies of copyrighted publications. Clearly distinguish excerpts from student or AI summaries.

### Knowledge pages

The `wiki/` directory contains linked Markdown pages organized around these decision topics:

- Business priorities: the decisions the project should support, stakeholder needs, and scope.
- Store performance: candidate measures, fair comparisons, and data-quality questions.
- Expansion criteria: factors for assessing prospective locations, with Pasadena treated as a hypothesis.
- Data constraints: available data, known limitations, handling requirements, and questions requiring clarification.

Supporting pages include source summaries, the interview pack, Marcus’s technical questions, and reviewed interview follow-up. Avoid creating pages that merely repeat existing material; link to the authoritative page instead.

Each topic page distinguishes:

- Meridian statements, attributed to the brief or an approved interview source.
- External findings, with citations and an explanation of their relevance and limits for Meridian.
- Team interpretations or hypotheses, explicitly labeled and linked to supporting evidence.
- Open questions, including why each matters and the intended respondent.

A statement in the brief is evidence of what Meridian has said, not independent verification of the underlying claim. Industry findings must not be presented as Meridian-specific facts.

### Navigation and history

`wiki/index.md` lists every wiki page with a link and a short description, grouped for easy navigation. Readers can reach topics, sources, interview materials, and follow-up from this index.

`wiki/log.md` records source incorporations, substantive revisions, saved answers, and maintenance reviews in chronological, append-only entries. Entries identify what changed, why, and which sources or approvals supported the change. Git history supplements this log.

### Maintenance instructions

A dedicated wiki instruction document defines page conventions, citation and claim labels, source review, question answering, update approval, and maintenance checks. It links to the data-handling checklist and operates alongside existing repository instructions.

## Research and update workflow

Start with approximately 6–8 strong external sources across grocery performance, expansion criteria, and the regional market. Prefer primary sources such as official statistics, company reports, and original research. Supplement with credible industry analysis where it adds useful context. The source count is a target, not a reason to include weak or redundant evidence.

Process one source at a time:

1. Identify the candidate and assess relevance, provenance, currency, and suitability for AI processing.
2. Present its key takeaways, limitations, and proposed wiki changes to the user.
3. Wait for approval before incorporating it into the wiki.
4. Preserve the approved source material or source note; create or update its summary and affected topic pages.
5. Update cross-references, the index, and the log.

Do not invent access to an unavailable source or use it as verified evidence. Record the limitation and propose an accessible alternative. If sources conflict, retain and attribute both claims, explain the disagreement, and identify what clarification is needed.

When answering questions, use the index to locate relevant pages, cite the supporting sources, and distinguish evidence from interpretation. Propose useful answers for inclusion in the wiki rather than silently making them persistent. Explain proposed edits before making them and summarize completed changes in plain language afterward.

## Interview preparation and follow-up

The interview pack draws from the topic pages and remains concise enough to use during a 45-minute meeting. Questions cover business priorities, expansion assumptions and criteria, success measures, scope, and constraints. Link each major question to the evidence or uncertainty that motivates it.

Keep questions about extracts, field definitions, and POS migration details in Marcus’s separate list, while raising their business implications with Dana when relevant.

After the interview, a student checks notes for accuracy and restricted information before approving them for AI processing. This review must happen before the AI reads the notes. If restricted contents are discovered, follow the checklist’s stop-and-notify procedure.

Review approved notes as a new source before incorporating them. Update relevant topics and distinguish explicit stakeholder decisions from student interpretations. Preserve unresolved questions and record follow-up ownership when agreed; do not invent owners or deadlines.

## Data handling and sharing

The existing data-handling checklist governs this wiki. In particular:

- Students receive aggregated summaries only.
- Customer and employee data, including excerpts, must never enter AI tools.
- Sales totals by store and week and store attributes are explicitly permitted by the brief for AI use. Aggregation of other data does not automatically authorize AI processing.
- Any other project data category requires written clarification before AI use. Research documents and reviewed project narrative must be checked for prohibited contents rather than treated as blanket authorization to include underlying records.
- A student’s review cannot override Meridian’s restrictions.
- The working wiki remains within the approved student project environment. Do not publish the repository or wiki as part of this work.
- Dana receives reviewed interview materials. Follow Meridian’s approval requirements for every release outside the project team, including class presentations and portfolio use.
- Apply the agreed retention and deletion rules to source copies, wiki pages, interview notes, and exports.

Named owners, approved systems and transfer methods, aggregation rules, and the return/deletion deadline remain operational agreements to settle under the checklist. Their absence does not authorize data transfer or access.

## Quality and acceptance criteria

The eventual wiki is ready for interview use when:

- The index links to all pages, and internal links resolve.
- Topic pages distinguish Meridian statements, external evidence, interpretations, and questions.
- Substantive factual claims are traceable to sources; dates and context are recorded where relevant.
- Approximately 6–8 relevant external sources have been reviewed individually and approved, or the user has approved a smaller evidence set.
- The pack supports a 45-minute interview with Dana and includes a briefing, prioritized questions with context, and an answer-capture template.
- Marcus’s technical questions are easy to find separately.
- Pasadena is framed as a hypothesis, and external research is not misrepresented as Meridian-specific evidence.
- Restricted data is excluded, and sharing follows the checklist.
- The log records approved updates, and a maintenance review has checked conflicting or stale claims, missing citations, unlinked pages, and broken links.

Follow-up is complete when approved interview notes have been incorporated, relevant answers and decisions are updated, and unanswered questions are visible with known follow-up responsibilities.

## Approval boundary

This document specifies the approved design for review. It does not authorize wiki construction, source ingestion, or an implementation plan. Wait for the user to approve this specification before writing an implementation plan.
