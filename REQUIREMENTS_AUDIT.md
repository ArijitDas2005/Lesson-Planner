# Requirements audit

Checked against the AI Research Intern task on 7 November 2026.

| Requirement | Status | Implementation / evidence |
|---|---|---|
| Lesson title and objective inputs | Done | Required fields, empty-input validation, sample briefs. |
| Research books, websites, YouTube | Implemented; live providers restricted here | Local backend searches web/video via DuckDuckGo and books via Google Books with Open Library fallback. Search failures produce explicit search-link fallbacks, not fake results. This environment returned no DuckDuckGo records and catalog access failed/rate-limited. |
| Structured lesson, explanations, examples, applications | Done | Two complete built-in sample lessons and generic scaffold; optional model generator synthesizes from attached evidence. |
| Supplementary videos and references | Done | Sample lessons include direct YouTube links and bibliographic references; dynamic output is prompted to cite attached sources. Video review is left to the instructor. |
| 45-minute ceiling | Done for included lessons; model output gets QC | HTTP pacing totals 45 minutes; SQL pacing totals 45 minutes. Optional supplementary videos are assigned outside the lesson plan. QC checks generated pacing. |
| QC 1: factual/research audit | Implemented; live model requires credentials | Separate AI endpoint retrieves up to eight public HTML/text source pages, supplies excerpts and fetch failures to a skeptical audit prompt, and returns verified claims, issues, recommendations, and limits. Without a model, the app labels its local checks as source-coverage heuristics only. |
| QC 2: instructional audit | Implemented; live model requires credentials | Separate AI call evaluates objective alignment, clarity, structure, examples, practice, checks, prior knowledge, and time. Without a model, local structural checks are labeled as heuristic. |
| Separate audit reports | Done | Independent report state, UI cards, retry controls, saved/exported with the lesson. |
| Review, edit, save, preview | Done | Editable lesson preview, browser-local drafts, saved lesson library, final-save action. |
| Apply QC recommendations | Done | Adds the recommended follow-up items to the editable lesson for instructor resolution. |
| Export lesson, references, reports | Done | Markdown and JSON export include lesson, source list, and both QC reports. |
| Empty input and provider/model failures | Done | Empty research returns 400; UI validates brief; search/model failures display errors and retry controls without replacing the existing lesson. |
| Preserve instructor edits | Done | Draft and editor changes are stored in localStorage; failed generation does not replace current lesson state. |
| Required sample plus second sample | Done | HTTP and SQL join sample lessons and manual fact-check/QC documentation in `SAMPLE_QC.md`. |
| Originality and acknowledgements | Done | Attribution/originality note in README and sample QC record; lesson references credit standards, sites, books, and videos. |

## Verification limits

Python backend compiles, the app page serves HTTP 200, malformed/empty requests return errors, fallback search cards render, HTML element references resolve, and both sample schedules total 45 minutes. This workspace has no AI credentials, so model generation and model-backed QC could not be exercised end to end. Its outbound research providers also failed/rate-limited; dynamic results must be verified in an environment with network access. The two sample lessons were manually checked against their cited standards and official documentation; see `SAMPLE_QC.md`.
