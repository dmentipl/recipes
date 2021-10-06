# Recipes

Food recipes.

## Requirements

The website is built with [Sphinx](https://www.sphinx-doc.org/) and [MyST](https://myst-nb.readthedocs.io/). See `requirements.txt` for all dependencies.

Install dependencies. For example in a conda environment.

```bash
conda create --name recipes python pip
conda activate recipes
pip install -r requirements.txt
```

## Usage

Instructions for installing and building the website locally.

### Build

Make changes then build the HTML with Sphinx.

```bash
make dirhtml
```

### View

Inspect the output in a web browser.

```bash
python -m http.server 8000 --directory _build/dirhtml
```

### Autobuild

An alternative, handy for development, is to automatically build the website and re-render upon any change using sphinx-autobuild.

```bash
sphinx-autobuild . _build -b dirhtml --host 0.0.0.0 --open-browser &
```

## Deploy

A GitHub Actions workflow is used to deploy website. Any changes pushed to the main branch will automatically rebuild the website.

See [deploy.yml](.github/workflows/deploy.yml) for details.
