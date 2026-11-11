BrandLens AI — Round 3 MVP
Run locally
Download or clone this repository.
Open index.html in a modern browser. No build tools or package installation are required.
Use Load sample to try the content-review journey.
Deploy on GitHub Pages
Keep index.html in the repository root. In GitHub, open Settings → Pages, choose Deploy from a branch, select main and /(root), then save. GitHub Pages publishes static files from the selected source. See https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
Features in this MVP
Editable brand name, tone, preferred terms, prohibited terms, approved facts and extra guidance.
Rule-based content checks with explanations and suggested wording.
Claim review against the local approved-facts list using text matching.
Image preview, alt-text presence prompt and WCAG contrast ratio calculation.
Demo role selector (Editor, Reviewer, Admin), comments, version snapshots and approval decisions.
Review history, summary counters and JSON export.
Responsive mobile interface and local browser persistence.
Important implementation limits
No connected LLM or external fact-checking service. Claim matching is local text matching only; it does not establish truth or independently verify sources.
Visual checks do not perform image recognition, logo detection or a complete accessibility audit.
Roles are a demonstration only. There is no authentication, server, shared database or real multi-user collaboration. Anyone using the same browser profile can change the demo role.
Data is stored in the current browser's localStorage. It is not synchronized across devices and may be cleared by browser settings.
Do not enter confidential or personal information.
Architecture
A single static HTML page contains semantic sections, CSS responsive layout, and vanilla JavaScript. JavaScript loads/saves guideline and review data in localStorage, runs deterministic text rules, calculates contrast from relative luminance, previews uploaded images with an object URL, and renders the review workflow. GitHub Pages can host these static assets.
Manual test checklist
Open the app with no saved data: all sections should load and empty states should be visible.
Run analysis with empty text: validation alert appears and no review is created.
Load sample and analyse: prohibited phrases and risky claims should be flagged.
Save a custom term rule and analyse matching text: replacement suggestion appears.
Add an approved fact and check a sentence containing it: possible text match is displayed; do not treat it as proof.
Check a risky claim with no matching fact: “Needs evidence” is displayed.
Upload an image under 5 MB, enter alt text, run visual checks.
Change foreground/background colours: contrast ratio updates; low contrast is flagged.
Create a review, add a comment as Editor, save a version, then switch to Reviewer and approve/request changes.
Refresh the page: guidelines and review history should remain in the same browser.
Export JSON: a downloadable JSON file should be created.
Clear history: confirm that review records are removed.
Roadmap
Add a secure backend, authentication and shared database before claiming real team collaboration.
Add source-linked claim verification with trusted evidence and human review.
Add image-based logo/colour analysis and automated accessibility scanning.
Add automated browser tests, audit logs, backups and privacy controls.
