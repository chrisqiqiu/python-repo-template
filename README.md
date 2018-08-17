# python-repo-template

[![Build Status](https://travis-ci.org/kyhau/python-repo-template.svg?branch=master)](https://travis-ci.org/kyhau/python-repo-template)
[![codecov](https://codecov.io/gh/kyhau/python-repo-template/branch/master/graph/badge.svg)](https://codecov.io/gh/kyhau/python-repo-template)

This is a template repository that you can use to quickly create a python application that can be built, tested, and
released as an internal python module.

**Use**

- [Travis CI](https://travis-ci.org/)
- [tox](https://tox.readthedocs.io/en/latest/)
- [codecov](https://codecov.io/) 
- [bumpversion](https://github.com/peritus/bumpversion)

## Setting up a new repository from this template

Create a directory and pull all the files in this template.

```bash
mkdir new_repo_name
cd new_repo_name
git init
git pull https://github.com/kyhau/python-repo-template
```

## Create virtual env and install dependencies 

**Linux**

```bash
virtualenv env
. env/bin/activate
pip install -e .
```

**Windows**
```bash
virtualenv env
env\Scripts\activate
pip install -e .
```

## Run pytest with Tox

```bash
pip install -r requirements-build.txt
tox -r
```

## Build wheels

If the library is py2/py3 compatible then remove the `bdist_wheel` lines in tox.ini and run this line.

```bash
python setup.py bdist_wheel --universal
```


## Version-bump your application or module with [bumpversion](https://github.com/peritus/bumpversion)

Install bumpversion:

    pip install bumpversion

To move from a dev version to a full release, run this command:

    bumpversion release
    e.g. 1.2.3.dev0 -> 1.2.3

To move from a full release to a dev version, run this command:

    bumpversion patch
    e.g. 1.2.3 -> 1.2.4.dev0

To bump a major|minor|patch 'part', run one of these commands:

    bumpversion major
    bumpversion minor
    bumpversion patch
    e.g. 1.2.3.dev0 -> 2.0.0.dev0
    e.g. 1.2.3.dev0 -> 1.3.0.dev0
    e.g. 1.2.3.dev0 -> 1.2.4.dev0

To bump a dev version, run this command:

    bumpversion dev
    e.g. 1.2.3.dev0 -> 1.2.3.dev1

To see what would happen without changing any files, run this command:

    bumpversion --dry-run --list release
    e.g. 1.2.3.dev0 -> 1.2.3
