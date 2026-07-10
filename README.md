# AerEO Notebooks — Executable Book

[![Jupyter Book Badge](https://jupyterbook.org/badge.svg)](https://frandorr.github.io/aereo-notebooks)
[![Launch on Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/frandorr/aereo-notebooks/main?urlpath=lab/tree/notebooks/01-sentinel2.ipynb)

This repository hosts an [Executable Book](https://executablebooks.org/) of tutorials for [AerEO](https://github.com/frandorr/aereo), a modular satellite data discovery, extraction, and processing framework.

## Live site

The rendered book is published to GitHub Pages:

**https://frandorr.github.io/aereo-notebooks**

## Run interactively

Click the Binder badge above to launch the notebooks on [mybinder.org](https://mybinder.org). You can also run cells live in the browser using the 🚀 rocket menu and **Live Code** button on the published site.

## Build locally

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter-book build .
```

Open `_build/html/index.html` in your browser.

To rebuild and execute notebooks during the build (slower), edit `_config.yml`:

```yaml
execute:
  execute_notebooks: "auto"
```

## Add a new notebook

1. Drop the `.ipynb` file into `notebooks/`.
2. Add an entry to `_toc.yml`.
3. Rebuild with `jupyter-book build .`.

## Authentication

Notebooks that use NASA data (VIIRS, Sentinel-3 OLCI, etc.) require [earthaccess](https://earthaccess.readthedocs.io) credentials. Configure a `~/.netrc` file before running those examples — see the [earthaccess authentication guide](https://earthaccess.readthedocs.io/en/latest/user/howto/authenticate/).

## Repository layout

```text
.
├── _config.yml              # Jupyter Book configuration
├── _toc.yml                 # Table of contents
├── intro.md                 # Landing page
├── notebooks/               # Tutorial notebooks
├── config/                  # Job configs and AOIs used by the notebooks
├── .binder/                 # Binder environment
├── .github/workflows/       # GitHub Pages deployment
└── requirements.txt         # Local and CI dependencies
```

## License

Same as [AerEO](https://github.com/frandorr/aereo): Apache 2.0.
