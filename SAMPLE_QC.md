# Sample runs and QC evidence

Here are the two sample lessons and the notes from reviewing them. Choose **Try the HTTP example** or **Try the SQL joins example** in the app to load a brief and its starter sources. The app has two separate reviews; the notes below also include a manual check against the linked primary and official references. A link is a place to check a claim, not proof by itself.

## Originality and acknowledgements

The lesson wording, worked examples, practice activities, and knowledge checks are original instructional synthesis written for these sample objectives; they are not copied from the cited material. The external resources below are acknowledged for the facts, explanations, or supplementary learning they provide. Short source titles and descriptions are paraphrased. Video authors and book authors are credited with their own resource links.

## Sample 1 — HTTP Requests and Responses

**Objective:** Explain GET and POST methods and distinguish between 2xx, 4xx, and 5xx response status categories.

### Manual factual check (QC layer 1)

- **GET:** RFC 9110 §9.3.1 defines GET as requesting transfer of a current selected representation. The lesson correctly describes it as retrieval, safe, and idempotent. RFC 9110 §9.3.1 states request content in GET has no generally defined semantics; the lesson says a GET should not carry content with defined semantics.
- **POST:** RFC 9110 §9.3.3 describes POST as asking the target resource to process the representation enclosed according to resource-specific semantics. Creation is one possible use, not the only use. The lesson explicitly avoids saying POST always creates.
- **Status classes:** RFC 9110 §15 defines 2xx as successful, 4xx as client error, and 5xx as server error, with the first digit indicating the class. The lesson's examples (200, 201, 400, 404, 500, 503) match these categories. A 404 can also mean the server is unwilling to disclose that a representation exists; the lesson uses it as the common missing-resource example rather than claiming that every 404 proves nonexistence.
- **Coverage/reliability:** RFC 9110 is the normative source; MDN is a readable secondary explanation; Gourley et al. is an older supplementary book, explicitly subordinated to the current standard. Traversy Media’s HTTP Crash Course & Exploration is linked directly. It covers the request/response cycle and status codes and runs about 38 minutes, so assign selected sections outside the 45-minute class plan.

**QC 1 report:** The source list includes a standard, a book, and a video, with notes about what each supports. The RFC covers the main claims. Before assigning the video, preview it and choose relevant sections; its full runtime is about 38 minutes, so it sits outside the 45-minute plan. Without a connected writing service, the app checks source coverage but does not compare lesson claims with the linked pages.

### Instructional review (QC layer 2)

- Objective alignment: learners explain GET/POST and classify 2xx/4xx/5xx; the practice and four-item check ask learners to do both.
- Structure: brief concepts → worked exchange → pair diagnosis → knowledge check → wrap-up.
- Pacing: 3 + 8 + 8 + 7 + 8 + 6 + 5 = **45 minutes**.
- Practical application: API request/response and outage/error scenarios.

**QC 2 report:** Passes objective keyword, example, practice, knowledge-check, and 45-minute pacing checks. Instructor review should ensure learners have enough prior HTTP vocabulary for the request example.

## Sample 2 — SQL Joins: Combining Related Tables

**Objective:** Given two related tables, write an INNER JOIN and a LEFT JOIN, then explain which unmatched rows each result keeps.

### Manual factual check (QC layer 1)

- PostgreSQL's official tutorial demonstrates joins through table references and join conditions. The lesson correctly says INNER JOIN returns matching row pairs, and that one-to-many matches can repeat a left-side row.
- PostgreSQL documents LEFT OUTER JOIN as preserving rows from its left input and filling right-side columns with NULL where no match exists. The lesson also correctly warns that a WHERE condition on right-side columns can eliminate NULL-extended rows.
- Microsoft Learn provides an additional guided reference. Beaulieu's *Learning SQL*, third edition, is the book reference; PostgreSQL docs are used for the syntax and exact behavior.
- The named Simon Sez IT video is a supplementary source that covers extra join varieties. Preview it before assigning to confirm the runtime and select only the relevant section.

**QC 1 report:** The source list includes official documentation, a book, and a video, with notes about what each supports. Preview the video to check its runtime and add context for any join types outside the lesson. Without a connected writing service, the app checks source coverage but does not compare lesson claims with the linked pages.

### Instructional review (QC layer 2)

- Objective alignment: learners write both join forms and explain the treatment of unmatched rows.
- Structure: relationship model → INNER JOIN → LEFT JOIN → predicted result → guided query → knowledge check.
- Pacing: 7 + 8 + 8 + 7 + 8 + 4 + 3 = **45 minutes**.
- Practical application: a query to find students with no enrollment, plus a warning about NULL behavior.

**QC 2 report:** Passes objective keyword, example, practice, knowledge-check, and 45-minute pacing checks. Instructor review should check learners' familiarity with SELECT, table aliases, and NULL before class.

## References checked

- IETF, [RFC 9110 — HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110.html), sections 9 and 15.
- MDN, [HTTP request methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods) and [HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status).
- PostgreSQL, [Joins Between Tables](https://www.postgresql.org/docs/current/tutorial-join.html).
- Microsoft Learn, [Combining data from multiple tables: SQL joins](https://learn.microsoft.com/en-us/training/azure-databases/postgresql/basic-sql-join-tables/).
- David Gourley et al., *HTTP: The Definitive Guide* (O'Reilly, 2002); supplementary historical book reference.
- Alan Beaulieu, *Learning SQL*, 3rd edition (O'Reilly, 2020).
- Traversy Media, [HTTP Crash Course & Exploration](https://www.youtube.com/watch?v=iYM2zFP3Zn0) (about 38 minutes; assign selectively outside the 45-minute lesson).
- Simon Sez IT, [Special SQL Joins Tutorial](https://www.youtube.com/watch?v=iq3eUqVmneg); supplementary video, instructor preview recommended.
