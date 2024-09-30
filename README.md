# Wildbook Docs
This repo contains all the documentation for Wildbook. Documentation is published with every accepted PR.

## Planned changes
The documentation will eventually support:
- #12 release versions to match product functionality
- #14 language support
- #15 generated API documentation

## Local Setup
1. Install the prereqs:
- install sphinx
- install [sphinx-book-theme](https://sphinx-book-theme.readthedocs.io/en/stable/tutorials/get-started.html): `pip install sphinx-book-theme`
- install [myst-parser](https://www.sphinx-doc.org/en/master/usage/markdown.html) (used by sphinx markdown extension): `pip install myst-parser`
2. Clone the `wildme-docs` repo: `git clone https://github.com/WildMeOrg/wildbook-docs.git`

## Build locally
To build:
1. `cd` to the `docs` directory:
2. Run the following commands:
    ```
    python -m venv .venv
    source .venv/bin/activate
    make html
    ```
3. Files will be in `docs/_build/html/`

If you aren't seeing your changes, try `make clean html` to force a complete rebuild.

To see files as they will appear online, including url paths:
1. In a new terminal, `cd` to `docs/_build/html/`
2. `python -m SimpleHTTPServer` or `python3 -m http.server`
3. Open `http://localhost:8000` in your browser

## Contribute to docs
Changes to the content of the docs are done in the `/docs` folder in the markdown files (file extension `.md`).
* Software usage instructions should be clear and concise; aim for an 8th grade reading level.
* Do not use in-line styling unless following an existing pattern.
* If you add a page to the docs, be sure to reference it in the appropriate `index.md` table of contents.
* We are using sphinx with a markdown extension, so the formatting may not follow standard markdown. If unsure, follow the formatting standards of [`myst-parser`](https://myst-parser.readthedocs.io/en/latest/syntax/typography.html).
