This website was built automatically on github using the [Sphinx to GitHub Pages V3](https://github.com/marketplace/actions/sphinx-to-github-pages) the
[Sphinx-doc](https://sphinx-doc.org).


The first step is to enable Github Actions by going to Settings-\>Pages-\>Build and deployment "Source" and choosing "Github Actions", and choosing
"Static Website". Then adding the a workflow. You can choose "static.yml", commit it, and then edit it to be the 
[Sphinx to GitHub Pages V3](https://github.com/marketplace/actions/sphinx-to-github-pages) workflow.

## Changes to Workflow YAML File

I made some minor changes to the [Sphinx to GitHub Pages V3](https://github.com/marketplace/actions/sphinx-to-github-pages) workflow:

1. The branch was  changed from `master` to `main`, so instead of

```yml
on:
  push:
    branches: [master] # branch to trigger deployment
```

it is:

```yml
on:
  push:
    branches: [main] # branch to trigger deployment
```

2. The line 

```
runs-on: ubuntu-20.04
```

was changed to

```
runs-on: ubuntu-latest
```

## `requirements.txt`

In addition to the Sphinx package itself, the Python3 packages `myst-parser` and `sphinx-book-theme` are required. All the requirements must be placed in 
`docs/requirments.txt`, whose content is:

```
sphinx
myst-parser
sphinx-book-theme
```

> [!IMPORTANT]
> The `requirements.txt` files must go in the `docs` folder and not in the root folder.


## `docs/` Folder Contents

The `docs` folder holds all the files created when `sphinxquick-start` is run (and subsequent changes made to it) as well as any customr `.css` in `docs/_static`.
