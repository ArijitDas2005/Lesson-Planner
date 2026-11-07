# Lesson Planner

A small local tool for turning a learning goal into a lesson plan, with sources and two separate reviews to help you refine it.

## Getting started

1. Open PowerShell in this folder.
2. Run `python server.py`.
3. Visit `http://127.0.0.1:8765` in your browser.

There’s nothing extra to install; the server uses Python’s standard library. Your drafts and saved lessons stay in this browser on this device.

## A typical session

Enter a lesson title and a learning goal, then search for books, websites, and videos. Search results are suggestions to investigate, so open the links and decide which sources are useful. You can also add a source you already know.

Build a lesson from the included outline, or connect a compatible writing service for a custom draft. The service can also help with two separate reviews: one looks at sources and factual claims, and the other looks at clarity, activities, and alignment with your learning goal. Without a connected service, the app runs simpler checks for source coverage and lesson structure. Those checks can flag things to look at, but they cannot verify facts.

Read through the lesson, make your own edits, and add any review notes you want to address. Save it to your lesson list, or download a Markdown copy or JSON backup with the sources and review reports.

## Connecting a writing service

Open **Connect a writing service** and enter an OpenAI-compatible chat completions URL, model name, and access key. When you draft or run a review, the app sends the lesson title, learning goal, source details, and key to that service through the local server. The key is not saved by the app. Check the provider’s own data-handling terms before using it.

## Sources and originality

The sample lessons use original explanations, examples, and activities, informed by the sources listed in each lesson. HTTP references include IETF RFC 9110, MDN, *HTTP: The Definitive Guide*, and a Traversy Media video. SQL references include PostgreSQL documentation, Microsoft Learn, *Learning SQL*, and a Simon Sez IT video. Discovery uses DuckDuckGo, Google Books, and Open Library; these help find sources but aren’t credited as lesson authors. Sample fact-checking notes and source acknowledgements are in [SAMPLE_QC.md](SAMPLE_QC.md).

The page loads DM Mono, DM Sans, and Playfair Display from Google Fonts. If you prefer not to use that external request, the page has local font fallbacks.

## A few things to keep in mind

- The included HTTP and SQL lessons have worked examples. Other titles start with a general outline that you should adapt before teaching.
- Search providers can be unavailable or change their pages. If a search fails, use the direct search links or add sources yourself.
- Book searches show catalog details, not book contents. Source reviews can retrieve up to eight public web pages; they can’t read paywalled pages, PDFs, or books, and some sites block access.
- A connected service can compare claims with the retrieved text, but its review can still miss things. Read the sources and use your judgment.
- Each lesson plan is paced for 45 minutes. Suggested videos are extra and should be assigned outside that time unless you adjust the plan.

## Project files

- `index.html`, `styles.css`, and `app.js` make up the browser app.
- `server.py` serves the app and handles research and writing-service requests.
- [SAMPLE_QC.md](SAMPLE_QC.md) records the two sample lessons, source checks, and review notes.
- [REQUIREMENTS_AUDIT.md](REQUIREMENTS_AUDIT.md) maps the requested features to the implementation and notes what could not be tested here.

## Checks run

The Python server syntax, local page response, input validation, saved-draft handling, and 45-minute sample schedules were checked. Live search was limited in this environment, and no writing-service credentials were available, so connected drafting and reviews could not be exercised here. See [REQUIREMENTS_AUDIT.md](REQUIREMENTS_AUDIT.md) for details.
