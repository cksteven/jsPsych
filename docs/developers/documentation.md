# Building the jsPsych documentation

The documentation hosted at [https://www.jspsych.org](https://www.jspsych.org) is generated using [mkdocs](https://www.mkdocs.org/) and the [mkdocs-material theme](https://squidfunk.github.io/mkdocs-material/). The documentation files are located in the [`/docs` directory of the GitHub repository](https://github.com/jspsych/jsPsych/tree/main/docs). The documentation is written using markdown.

To build a local copy of the docs, you will need to install `mkdocs`, `mkdocs-material`, and `mike` using `poetry`. 

## Install poetry

[Poetry](https://python-poetry.org/) is a package manager for python. Follow the install instructions on the `poetry` website to get it running.

## Install dev dependencies

Run the command `poetry install` in the root directory of jsPsych to install `mkdocs`, `mkdocs-material`, and their dependencies.

## Building a local copy of the docs

Run `poetry run mike deploy [version] -u` to build a new version of the documentation or to override an existing version. For example, if you are testing an edit to version `7.2` of the documentation, run `poetry mike deploy 7.2 -u`.

This will build the documentation and commit it directly to the `gh-pages` branch.

We use [`mike`](https://github.com/jimporter/mike) instead of `mkdocs` for the build step to support versioning of the documentation. `mike` runs the `mkdocs` command under the hood.

## Viewing the local docs

Run `poetry run mike serve` to launch a local webserver. The docs will be viewable at `http://localhost:8000`.
