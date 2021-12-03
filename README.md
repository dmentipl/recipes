# Recipes

Food recipes.

## Requirements

The website is built with [Sphinx](https://www.sphinx-doc.org/) and [MyST](https://myst-parser.readthedocs.io/). See `requirements.txt` and `requirements-dev.txt` for all dependencies.

Install dependencies in a virtual environment.

```bash
python -m venv .env
source .env/bin/activate
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r requirements.txt -r requirements-dev.txt
```

## Usage

Instructions for building and viewing the website locally.

### Build

Make changes then build the HTML with Sphinx.

```bash
sphinx-build . _build -b dirhtml
```

### View

Inspect the output in a web browser.

```bash
python -m http.server 8000 --directory _build
```

### Autobuild

An alternative, handy for development, is to automatically build the website and re-render upon any change using sphinx-autobuild.

```bash
sphinx-autobuild . _build -b dirhtml --host 0.0.0.0 --open-browser &
```

## Deploy

A GitHub Actions workflow is used to deploy website. Any changes pushed to the main branch will automatically rebuild the website.

See [deploy.yml](.github/workflows/deploy.yml) for details.
