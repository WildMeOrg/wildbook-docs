- clone wildme-docs
- install sphinx
- install [myst-parser](https://www.sphinx-doc.org/en/master/usage/markdown.html) (used by sphinx markdown extension)

to build, from this `docs/` directory:
```
python -m venv .venv
source .venv/bin/activate
make html
```

files will be in `_build/html/`.

