# Meridian Research Wiki Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task after user approval. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a student Markdown research wiki and concise interview pack for a 45-minute conversation with Dana, then maintain it through approved interview follow-up.

**Architecture:** Preserve approved original source notes in `raw/`; maintain synthesized pages in `wiki/topics/`, `wiki/sources/`, and `wiki/interview/`. Keep navigation, an append-only change log, and maintenance instructions at the wiki root. Review each external source with the user before incorporating it.

**Tech Stack:** Markdown, relative links, Git history, manual review, and a read-only Python standard-library link check. No application, database, website, testing framework, or additional dependencies.

**Spec:** [Approved research wiki specification](../specs/2026-09-11-meridian-research-wiki-design.md). The user approved this specification in conversation; its on-disk draft status predates that approval.

**Plan status:** Tasks 1–5 complete for this assignment milestone. Task 6 not started because the stakeholder interview has not happened. Status reconciled on 2026-09-15.

| Task | Status | Evidence or remaining work |
|---|---|---|
| 1. Rules and navigation | Complete | Maintenance instructions, index, and initialization log created and checked. |
| 2. Brief-based foundation | Complete | Brief summary and four topic pages created and checked. |
| 3. External research | Complete for this milestone | User approved S001, S002, and S003 as sufficient; the milestone target is three public sources. S001 accuracy review recorded below. |
| 4. Interview pack | Complete | Five pack files created; user accepted the six essential and three optional Dana questions and their priority order. |
| 5. Interview readiness | Complete | Readiness review logged; 190 local links checked, original source URLs reviewed, and stale status text corrected. |
| 6. Interview follow-up | Not started | Stakeholder interview has not happened; follow-up requires screened, approved notes afterward. |

Additional completed work: the cited specialty-grocer openings answer was saved in `wiki/topics/specialty-grocer-openings.md`, indexed, and logged.

The user explicitly authorized committing and pushing the current project to GitHub on 2026-09-15; this supersedes the earlier no-publication scope for this push only.

## Global constraints

The following requirements are copied from the spec and apply to every task:

- “Treat Pasadena as a candidate to evaluate, not a conclusion to substantiate.”
- “Prepare technical questions for Marcus separately from the main interview with Dana.”
- “Students receive aggregated summaries only.”
- “Customer and employee data, including excerpts, must never enter AI tools.”
- “Sales totals by store and week and store attributes are explicitly permitted by the brief for AI use. Aggregation of other data does not automatically authorize AI processing.”
- “A student’s review cannot override Meridian’s restrictions.”
- “Do not publish the repository or wiki as part of this work.”
- “Wait for approval before incorporating it into the wiki.”
- “Explain proposed edits before making them and summarize completed changes in plain language afterward.”

Use the [data-handling checklist](../../data-handling-checklist.md) for the full handling, sharing, and retention requirements. Source selection and interview-note approval remain separate gates even after this plan is approved. Do not ingest restricted records or treat unresolved operational agreements as authorization to transfer data.

If execution exposes a choice not settled by the spec, this plan, or subsequent user decisions, ask the user before deciding it. Do not add tooling or expand the research scope without agreement.

## Confirmed file conventions

- Use small folders by purpose: topics, sources, and interview materials.
- Use `wiki/AGENTS.md` for wiki maintenance instructions.
- Use descriptive lowercase filenames.
- Use sequential external source IDs such as `S001`, shared by raw notes and wiki summaries. Use lowercase filenames such as `s001.md`.
- Preserve source notes by default; retain full documents only when needed and permitted.
- Put a simple metadata table at the top of each external source note.
- Keep briefing, Dana’s questions, and the answer template separate, connected by a pack overview. Marcus’s questions remain separate.
- Verify through manual review and link checks without adding a testing framework.

## File map

| File | Responsibility |
|---|---|
| `raw/client-brief.md` | Existing original brief; read without modification |
| `docs/data-handling-checklist.md` | Existing handling authority; link without modification |
| `raw/s001.md` onward | Approved external source notes, one ID per source |
| `wiki/AGENTS.md` | Page conventions and maintenance workflows |
| `wiki/index.md` | Catalog of every wiki page with descriptions |
| `wiki/log.md` | Append-only record of approved changes and reviews |
| `wiki/topics/business-priorities.md` | Decisions, stakeholder needs, and scope |
| `wiki/topics/store-performance.md` | Measures, comparison fairness, and quality questions |
| `wiki/topics/expansion-criteria.md` | Location-selection evidence and hypotheses |
| `wiki/topics/data-constraints.md` | Available data, limitations, handling rules, and clarification needs |
| `wiki/sources/client-brief.md` | Attributed summary of the existing brief |
| `wiki/sources/s001.md` onward | External source synthesis, linked to its raw note and affected topics |
| `wiki/interview/overview.md` | Entry point and use instructions for the 45-minute pack |
| `wiki/interview/briefing.md` | Concise preparation briefing |
| `wiki/interview/dana-questions.md` | Prioritized business interview questions with context |
| `wiki/interview/answer-template.md` | Capture structure for answers, decisions, and follow-ups |
| `wiki/interview/marcus-questions.md` | Separate technical questions |
| `wiki/interview/follow-up.md` | Reviewed answers, decisions, unresolved questions, and known responsibilities |

Interview notes are a future input. Before receiving them, ask for the student-approved source location and confirmation of review; do not scan for or open unreviewed notes. Do not create a supposed transcript or invent interview answers.

## Task 1: Establish the wiki rules and navigation

**Files:** Create `wiki/AGENTS.md`, `wiki/index.md`, and `wiki/log.md`.

**Consumes:** Approved spec, this plan, existing repository instructions, and the handling checklist.

**Produces:** The common conventions used by every later task and a working entry point.

- [x] Read the spec and checklist before execution. Confirm this plan has been approved.
- [x] Write `wiki/AGENTS.md` with rules for immutable sources, source-by-source approval, claim labeling, citations, query answering, saved-answer approval, note screening, sharing, and maintenance. Make clear that these rules also govern the maintainer’s handling of raw sources; directory placement alone does not make data safe to read.
- [x] Define four topic sections: `Meridian statements`, `External findings`, `Team interpretations and hypotheses`, and `Open questions`. Require each question to explain why it matters and name the intended respondent.
- [x] Define external source metadata fields: source ID, title, publisher or author, original URL, publication date, access date, review status, and approval reference. Use `Not provided by source` for an unavailable publication date; never guess it.
- [x] Require source notes to distinguish excerpts from summaries and record limitations. Keep synthesis and changing review history in the wiki rather than editing original approved notes.
- [x] Create an index linking only to pages that currently exist. Add new entries as later tasks create pages; avoid future links that are already broken.
- [x] Start the log with a dated entry explaining initialization and the approval supporting it. Use dated entries that identify activity, affected pages, reason, sources, and approvals for subsequent updates.

**Done looks like:** The wiki has a readable entry point, clear maintenance rules, and a first log entry. No external source has been incorporated or fetched as part of this task.

**How you check it:** Open `wiki/index.md` and follow its links. Read `wiki/AGENTS.md` and confirm it explicitly requires your approval for each external source, excludes restricted records, and explains all four claim categories. Check that the initialization log does not claim research has already occurred.

## Task 2: Build the brief-based topic foundation

**Files:** Create `wiki/sources/client-brief.md` and the four topic files from the file map. Update `wiki/index.md` and append to `wiki/log.md`.

**Consumes:** Existing brief and checklist, with conventions from Task 1.

**Produces:** An attributed Meridian baseline that external research and interview preparation can build on.

- [x] Summarize the brief with a relative link back to the original. Attribute its claims to Meridian rather than describing them as independently verified.
- [x] Populate business priorities with the dashboard request, expansion decision, broad success goals, and the stated three-week board milestone and approximate eight-week project. Do not convert relative timing into invented calendar deadlines.
- [x] Populate store performance with the requested store/category comparison and questions about success measures, store maturity, comparison fairness, and the POS migration. Label proposed analytical considerations as interpretations or questions.
- [x] Populate expansion criteria with the Pasadena preference as a Meridian statement and neutral questions about alternatives, evaluation criteria, and what evidence could change the choice.
- [x] Populate data constraints with the data categories named in the brief and a link to the handling checklist. Make clear that the brief's possession of data does not mean the students have received it. Flag that category-level sales AI use is not explicitly authorized by the store-by-week permission.
- [x] Under external findings, state that external research has not yet been incorporated. This is an accurate project state, not permission to invent findings.
- [x] Add open questions with rationale and intended respondent, keeping technical details directed to Marcus.
- [x] Link related topics, add all new pages to the index, and append the update to the log.

**Done looks like:** Four topic pages and a source summary accurately separate the brief’s statements from team interpretations and missing information. The original files are unchanged.

**How you check it:** Compare the summary against `raw/client-brief.md`. Pick a statement and follow its citation. Verify Pasadena is not presented as the winning site, success measures are not invented, and restricted data is not copied into the wiki. Run the link check under Task 5.

## Task 3: Incorporate approved external research one source at a time

**Status:** Complete for this assignment milestone. The user approved the three current public sources (S001, S002, and S003) as sufficient. Their ingestions are complete; user-selected URLs and direct ingestion requests supplied ingestion approval.

**Files:** Create `raw/s001.md` and `wiki/sources/s001.md` for the first approved external source; repeat with the next unused ID for later sources. Update affected topic pages and the index; append log entries.

**Consumes:** Topic gaps from Task 2 and user approval of each proposed source and its changes.

**Produces:** Three approved public research sources (S001, S002, and S003) linked to decision topics. This user-approved milestone target replaces the original approximately 6–8-source target for this assignment milestone.

- [x] Identify one candidate addressing grocery performance, expansion criteria, or the regional market. Prioritize primary evidence and assess its currency, geography, methods, relevance, and limitations. Do not use confidential Meridian details in public search queries.
- [x] Read the accessible source. Present its identity, takeaways, limitations, and exact proposed wiki updates in chat. If inaccessible, disclose this and suggest an accessible alternative; do not claim to have verified it.
- [x] Wait for the user's approval. Rejection or silence does not authorize incorporation.
- [x] After approval, assign the next source ID and create the raw source note with the required metadata, clearly identified excerpts or summary, and access limitations. Record actual approval evidence rather than fabricating a signed-off status.
- [x] Write the corresponding wiki source summary, linking to the raw note, original URL, and relevant topics. Explain applicability to Meridian and limits on that applicability.
- [x] Update affected topic pages with cited findings, labeled interpretations, and research-informed interview questions. Preserve conflicting claims with their respective citations and a question about resolving the disagreement.
- [x] Update the index and log; check new links and summarize the changes to the user.
- [x] Meet the user-approved milestone target of three public sources: S001, S002, and S003. No additional source ingestion is required for this milestone.

**Done looks like:** Each incorporated source has an immutable source note, linked synthesis, traceable approval, and a clear contribution to the interview preparation. Findings do not masquerade as Meridian-specific facts.

**How you check it:** Choose one source ID and follow the chain from topic claim to source summary to raw note and original publication. Compare the text with the source and its stated limitations. Check the approval entry in the log. Review the index to confirm coverage of the three research areas and the approved source count.

### User review note — S001 ingestion completed — 2026-09-15

The user checked the Gelson's micromarket claim against the original ICSC article and confirmed that it reports a 5,400-square-foot ReCharge by Gelson's micromarket in Costa Mesa and a 3,000-square-foot first micromarket in Santa Ana. The user accepts the AI summary because it accurately describes Gelson's Southern California micromarket experimentation and appropriately notes that these examples do not establish Meridian performance or Pasadena viability.

This accuracy review applies to the completed S001 ingestion. Task 3 was incomplete when the review was recorded; the user's subsequent approval of S001–S003 as sufficient completes Task 3 for this assignment milestone.

## Task 4: Assemble the interview pack

**Files:** Create `wiki/interview/overview.md`, `briefing.md`, `dana-questions.md`, `answer-template.md`, and `marcus-questions.md`. Update the index and append to the log.

**Consumes:** Cited topic pages and approved research from Tasks 2–3.

**Produces:** Separate, linked interview materials for a 45-minute conversation with Dana and a separate technical question list.

- [x] Write the overview linking to all pack components and explaining the 45-minute meeting context. Keep exact agenda allocations open for review rather than inventing a mandatory timing split.
- [x] Write the concise briefing covering Meridian's stated situation, the most relevant external evidence, and major uncertainties. Link to fuller topic pages instead of repeating their contents.
- [x] Write Dana's questions in priority order with stable question IDs such as `D01`. For each, include the question, why it matters, and a link to evidence or an unresolved assumption. Cover priorities, expansion criteria, success measures, scope, and constraints; keep phrasing neutral.
- [x] Mark essential questions and optional follow-ups to support prioritization within 45 minutes. Present the proposed prioritization for user review before treating the pack as ready.
- [x] Write Marcus's separate questions with IDs such as `M01`, covering extracts, definitions, migration, and relevant technical uncertainties. Do not imply he has already agreed to provide anything.
- [x] Create an answer template with fields for question ID, respondent, answer, explicit decision if any, student interpretation, unresolved follow-up, agreed owner, and agreed deadline. Leave answer fields empty because the meeting has not happened.
- [x] Put a visible instruction on the template requiring student screening before notes are supplied to AI. Link to the handling checklist rather than suggesting the template is safe for unrestricted raw notes.
- [x] Update navigation and the log. Explain that materials require the appropriate review before sharing and do not send or publish them.

**Done looks like:** The overview opens a usable set of interview materials; Dana's business questions and Marcus's technical questions are separate. The answer template contains no fabricated responses.

**How you check it:** Open the overview and walk through the pack in meeting order. Confirm the priority list is realistic for 45 minutes, each major question has a rationale and link, and the briefing does not assume Pasadena is correct. Review the proposed priorities and request changes if needed. Check that the answer template separates decisions from interpretations.

### User review decision — Task 4 accepted — 2026-09-15

The user reviewed and accepted the six essential and three optional questions for Dana and their proposed priority order. The user accepts them because they cover the main decisions to clarify: project success, Pasadena and expansion criteria, the board deliverable, and data permissions. The optional questions are useful if time allows.

Task 4 is complete. This acceptance does not constitute Task 5's readiness review or approval to share materials externally. At that review checkpoint, the user instructed that Task 5 must not start. The user subsequently authorized Task 5, which is now complete.

## Task 5: Review interview readiness

**Status:** Complete. See the [Task 5 review record](../../../wiki/log.md) for acceptance checks, corrections, evidence limitations, and release conditions. Readiness for student preparation does not authorize additional data access or replace applicable Meridian release approval.

**Files:** Correct defects only in created wiki files; append the review and outcomes to `wiki/log.md`. Do not revise approved original sources to make claims fit.

**Consumes:** All pre-interview deliverables from Tasks 1–4.

**Produces:** Reviewed interview materials and an explicit account of any remaining gaps.

- [x] Run this read-only local Markdown link check from the repository root:

```bash
python3 - <<'PY'
from pathlib import Path
import re
from urllib.parse import unquote, urlsplit

pages = sorted(Path('wiki').rglob('*.md'))
assert pages, 'No wiki pages found'
errors = []
for page in pages:
    for target in re.findall(r'\[[^\]]*\]\(([^)]+)\)', page.read_text()):
        target = target.strip().strip('<>')
        parsed = urlsplit(target)
        if parsed.scheme or parsed.netloc or not parsed.path:
            continue
        destination = page.parent / unquote(parsed.path)
        if not destination.exists():
            errors.append(f'{page}: missing {target}')
if errors:
    raise SystemExit('\n'.join(errors))
print(f'Checked local file links in {len(pages)} wiki pages.')
PY
```

- [x] Manually check heading anchors and external URLs used in the pack. The script checks file existence only; it does not verify anchors, source accuracy, permissions, or full Markdown syntax.
- [x] Compare `wiki/index.md` with the Markdown file list from `rg --files wiki`. Confirm every other wiki page has an index link and description; the index itself is the entry point.
- [x] Review every substantive claim in the briefing and question rationales for citation support and correct labeling. Check topic pages for stale or conflicting claims and identify any unresolved disagreement explicitly.
- [x] Confirm every approved source has an approval record and that no pending source was incorporated. Verify source notes and the original brief were not silently rewritten.
- [x] Review the spec's acceptance criteria one by one. Record passed checks and actual remaining gaps in the log; do not label the pack ready if essential questions, citations, or handling requirements remain unresolved.
- [x] Summarize readiness to the user and identify the materials requiring review before release. Do not share them externally.

**Done looks like:** Local links resolve, the index is complete, evidence is traceable, and the pack satisfies the spec's pre-interview criteria. Remaining uncertainties are visible as questions rather than unsupported conclusions.

**How you check it:** Run the supplied command and expect a checked-page count with no missing-link errors. Read the final review log, spot-check cited claims against their sources, and compare the pack with the spec's acceptance list. Approval to build does not replace Meridian's required release approval.

### User review note — Task 5 accepted — 2026-09-17

The user reviewed Task 5's briefing and checked the SafeGraph source against the original article. The user specifically verified that the article recommends evaluating trade areas, competition, physical access and parking, financial/legal costs, and existing-store performance. This supports how the briefing summarizes SafeGraph as a site-selection framework.

The user accepts Task 5's output because the summary accurately reflects the original source and appropriately treats the SafeGraph material as a framework for questions rather than proof that Pasadena is the right location.

## Task 6: Incorporate reviewed interview follow-up

**Status:** Not started. The stakeholder interview has not happened yet.

**When:** After the interview and only after student screening and source-update approval. This task cannot be completed during pre-interview construction.

**Files:** Read the student-approved interview source at its confirmed location. Create `wiki/interview/follow-up.md`; update affected topic pages, the index, and append to the log. Preserve the reviewed source unchanged.

**Consumes:** Actual interview notes checked by a student for accuracy and prohibited information, plus user approval of proposed incorporation.

**Produces:** Updated knowledge, explicit decisions, and a visible list of unresolved questions.

- [ ] Ask for confirmation that notes have been screened before opening them, and confirm their approved location. If that confirmation is missing, wait; do not search for unreviewed notes.
- [ ] Read the approved notes and propose takeaways and updates to the user. Wait for approval before incorporating them. If unexpected restricted information is discovered, stop and follow the checklist's incident procedure.
- [ ] Create the follow-up page linked to the actual source. Organize answers by interview question ID, preserving the distinction between stakeholder statements, explicit decisions, and student interpretations.
- [ ] Update affected topics with citations. Preserve prior claims where needed to explain a change or conflict; do not rewrite the original brief.
- [ ] List unresolved questions and only the owners and deadlines actually agreed. If no owner or deadline was agreed, state that explicitly and ask for clarification rather than inventing one.
- [ ] Update the index and log, rerun the link check, and review follow-up claims against the approved notes.
- [ ] Report completion of this scope and remind the team to apply the checklist's agreed retention and access rules. Do not delete material or extend research automatically.

**Done looks like:** Actual approved interview information is reflected in the wiki, decisions are distinct from interpretations, and unanswered questions remain easy to find with known responsibilities or explicit assignment gaps.

**How you check it:** Compare the follow-up page with the approved notes. Select a question ID and trace its answer to the source and affected topic. Check that no owner, deadline, or decision was invented and that the index and link check include the follow-up page.

## Approval and delivery checkpoints

1. User approves this plan before any wiki construction.
2. User reviews each external source and proposed changes before incorporation.
3. User reviews the draft interview pack's priorities and usability.
4. Meridian's applicable release approval is obtained before external sharing; this plan does not authorize sending materials.
5. A student screens interview notes before AI access, and the user approves proposed updates before incorporation.

Tasks 1–5 deliver interview readiness. Task 6 delivers follow-up after the interview; report these milestones separately rather than claiming the entire lifecycle is complete early. No publication, dependency installation, or unrelated repository changes are included.

## Spec coverage review

| Spec requirement | Plan coverage |
|---|---|
| Source/wiki/instruction separation | Tasks 1–3 |
| Topic organization and claim distinctions | Tasks 1–2 |
| Source metadata, immutability, citations, limitations | Tasks 1–3 |
| Individual approval and 6–8-source research target | Task 3 |
| Index, append-only log, query and saved-answer workflow | Task 1 and updates in Tasks 2–6 |
| 45-minute Dana pack and separate Marcus questions | Task 4 |
| Data handling, screening, sharing, retention | Global constraints and Tasks 1, 4–6 |
| Link checks, contradictions, stale claims, missing citations | Task 5 and follow-up checks in Task 6 |
| Reviewed notes, decisions, unresolved follow-up | Task 6 |
| No execution before plan approval | Plan status and approval checkpoints |
