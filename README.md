# CS5744_TransitFlow

This repository contains a zola project which generates HTML for Project 1.

## Setup

This set of instructions assumes that you have `git` and `zola` ([link](https://www.getzola.org)) installed.

```bash
git clone git@github.com:panevain/CS5744_TransitFlow.git
cd CS5744_TransitFlow
git submodule update --init
zola serve
```

## Adding Content

The [book theme](https://www.getzola.org/themes/book/) goes on to explain four key things:
1. Each subfolder of `content` represents a chapter and must contain an `_index.md` file
2. Each page in the chapter is `<slug>.md`
3. The front matter of `_index.md` must contain `sort_by = "weight"` and `weight=n`, where `n` is the chapter number.
4. The front matter of each page must contain `weight=n`, where `n` is the page number.

Note that the folder and file names appear in the url.

## Building for the Web

When you push to main, a GitHub Actions build kicks off. Go to [here](https://panevain.github.io/CS5744_TransitFlow/) to view the site
