# Wild Me Docs
This repo contains all the documentation for all Wild Me products, including Wildbook, Scout, and Codex. Documentation is published with every accepted PR.

## Planned changes
The documentation will eventually support:
- TODO #12 release versions to match product functionality
- TODO #14 language support
- TODO #15 generated API documentation

## Local Setup
1. Install the prereqs:
- install sphinx
- install [sphinx-book-there](https://sphinx-book-theme.readthedocs.io/en/stable/tutorials/get-started.html): `pip install sphinx-book-theme`
- install [myst-parser](https://www.sphinx-doc.org/en/master/usage/markdown.html) (used by sphinx markdown extension): `pip install myst-parser`
2. Clone the `wildme-docs` repo: `git clone https://github.com/WildMeOrg/wildme-docs.git`

## Build locally
To build:
1. `cd` to the `docs` directory:
2. Run the following commands:
    ```
    python -m venv .venv
    source .venv/bin/activate
    make html
    ```
3. Files will be in `docs/_build/product-docs/en/html/`

## Contribute to docs
TODO #11