This repo is an example of using [Sphinx to GitHub Pages V3](https://github.com/marketplace/actions/sphinx-to-github-pages) Action to automatically build
a Sphinx-doc website.

However, I did make these changes to the [Sphinx to Github Pagpes](https://github.com/marketplace/actions/sphinx-to-github-pages):

1. I changed the brnache `master` as shown below:

```yml
on:
  push:
    branches: [master] # branch to trigger deployment
```

to `main` like this:


```yml
on:
  push:
    branches: [main] # branch to trigger deployment
```

I also changed

```
runs-on: ubuntu-20.04
```

to 

```
runs-on: ubuntu-latest
```

> [!NOTE]
> The `requirements.txt` files must go in your `docs` folder. Don't put it in the root. So in addition to your `.md`  files in `./docs` and the files automatically generated
> by `sphinxquick-start` (along with your modifications to `conf.py` and so forth), you need to put whatever extensions you need in `requirments.txt`

My `requirements.txt` has:

```
sphinx
myst-parser
sphinx-book-theme
```
