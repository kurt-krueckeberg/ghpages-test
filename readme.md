This repo is an example of using the [Sphinx to GitHub Pages V3](https://github.com/marketplace/actions/sphinx-to-github-pages) Action to automatically build
a Sphinx-doc website without having to:

1. manually build it locally: `make html`
2. Copy the files in `_build/html` and `_static` to the root of the repo.
3. push the changes

I did, however, make some minor changes to the [Sphinx to Github Pagpes](https://github.com/marketplace/actions/sphinx-to-github-pages):

1. I changed the branch from `master` to `main`, so instead of

```yml
on:
  push:
    branches: [master] # branch to trigger deployment
```

it is

```yml
on:
  push:
    branches: [main] # branch to trigger deployment
```

I also changed `runs-on: ubuntu-20.04` to `runs-on: ubuntu-latest`. My requirements.txt file has the Python3 packages needed to build the project.
This includes the `sphinx` package itself and two other packages:

- sphinx
- myst-parser
- sphinx-book-theme
```

> [!IMPORTANT]
> The `requirements.txt` files must go in your `docs` folder. Don't put it in the root. So in addition to your `.md`  files in `./docs` and the files automatically generated
> by `sphinxquick-start` (along with your modifications to `conf.py` and so forth), you need to put whatever extensions you need in `requirments.txt`
