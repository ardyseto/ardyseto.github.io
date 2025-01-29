---
layout: post
title: Brew and Conda package list with size information
date: 2025-01-28 01:59:00
description: this is tutorial how to get size information of brew and conda list packages
tags: brew conda
categories: programming
---

When managing packages on macOS, it's often useful to know how much disk space each package consumes. This can help with system maintenance, cleanup, and optimization of storage space. This tutorial demonstrates how to retrieve size information for packages installed via two popular package managers: `brew` and `conda` or `pip`.

We'll cover:
- How to list package sizes for Homebrew installations
- How to get size information for Conda/pip packages
- Sorting and formatting the output for better readability

Let's dive into the commands and their usage...

## Brew
this is the script to get the size information of brew packages:

```bash
du -sch $(brew --cellar)/*/* | sed "s|$(brew --cellar)/\([^/]*\)/.*|\1|" | sort -k1h
```
source: [https://gist.github.com/eguven/23d8c9fc78856bd20f65f8bcf03e691b](https://gist.github.com/eguven/23d8c9fc78856bd20f65f8bcf03e691b)

and the result will look like this:

```bash
...
 46M	rav1e
 53M	ffmpeg
 73M	python@3.13
 77M	node
 82M	icu4c@76
123M	ghostscript
263M	pandoc
1.2G	total
```

## Conda / Pip
this is the script to get the size information of conda packages:

```bash
conda activate web
pip list | tail -n +3 | awk '{print $1}' | xargs pip show | grep -E 'Location:|Name:' | cut -d ' ' -f 2 | paste -d ' ' - - | awk '{print $2 "/" tolower($1)}' | xargs du -sh 2> /dev/null | sort -h | awk '{print $1, $2}' | awk -F/ '{print $1, $NF}'
```
source: [https://stackoverflow.com/questions/34266159/how-to-see-sizes-of-installed-pip-packages](https://stackoverflow.com/questions/34266159/how-to-see-sizes-of-installed-pip-packages) with some modification to sort by size.

and the result will look like this:

```bash
...
2.4M  pypdf2
3.0M  ipython
5.2M  pygments
5.6M  reportlab
6.8M  mkdocs
9.0M  jedi
10M  setuptools
12M  pip
18M  sqlalchemy
31M  babel
 ```
