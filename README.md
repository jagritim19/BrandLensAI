# BrandLens AI — Round 2 MVP

## Run
Open `index.html` in a modern browser. No build step is required.

## Deploy with GitHub Pages
1. Create a public repository named `BrandLens-AI`.
2. Upload `index.html` and `README.md` to the repository root.
3. Open Settings → Pages.
4. Choose Deploy from a branch, select `main` and `/ (root)`, then Save.
5. Wait for GitHub Pages to publish the site.

## Implemented
- Editable brand name, tone, terminology, prohibited phrases, approved facts and extra guidance.
- Content submission and rule-based analysis.
- Findings with severity, matched wording, explanations and suggested actions.
- Approve / request changes workflow.
- Browser-local review history and JSON export.
- Responsive mobile interface.

## Honest technical limitations
This MVP uses deterministic JavaScript rules, not a connected LLM. Claim detection is heuristic and may produce false positives or miss claims. A flag means human review is needed, not that a claim is false. Data is stored in localStorage in the current browser/device, not a shared team database. Do not enter confidential brand material.

## Planned Round 3
1. Evidence-grounded claim checking with source retrieval and optional LLM assistance.
2. Visual brand and accessibility checks for uploaded creative assets.
3. Multi-user roles, comments, version history and approval routing.
