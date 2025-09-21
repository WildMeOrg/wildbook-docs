# Wildbook Docs
This repo contains all the documentation for Wildbook. Documentation is published with every accepted PR.

## Planned changes
The documentation will eventually support:
- #12 release versions to match product functionality
- #14 language support
- #15 generated API documentation

## Quick Start

### Docker
With docker and docker compose installed; run the development server with 
```bash
docker compose up
```
This will serve the documentation and automatically reload on changes at [http://localhost:8000](http://loaclhost:8000)
## Local Setup

1.  **Clone the repository:**
    ```bash
    git clone --depth=5 https://github.com/WildMeOrg/wildbook-docs.git
    cd wildbook-docs
    ```
2.  **Set up a virtual environment and install dependencies:**
    ```bash
    python -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    ```

### Running Locally

1.  **Start the development server (with live reload):**
    ```bash
    make dev
    ```
    This will serve the documentation and automatically reload on changes. Open your browser to the address provided by `sphinx-autobuild` (usually `http://127.0.0.1:8000/`).

2.  **Build the documentation (for deployment):**
    ```bash
    make html
    ```
    The static HTML files will be generated in `docs/_build/html/`.

## Contribute to docs
Changes to the content of the docs are done in the `/docs` folder in the markdown files (file extension `.md`).
* Software usage instructions should be clear and concise; aim for an 8th grade reading level.
* Do not use in-line styling unless following an existing pattern.
* If you add a page to the docs, be sure to reference it in the appropriate `index.md` table of contents.
* We are using sphinx with a markdown extension, so the formatting may not follow standard markdown. If unsure, follow the formatting standards of [`myst-parser`](https://myst-parser.readthedocs.io/en/latest/syntax/typography.html).
