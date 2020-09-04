# GitHub Action - ktlint check
GitHub action that runs a ktlint against changed files.

## Example

```yml
on:
  pull_request:
    branches:
      - dev

jobs:
  style-check:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v2
      - name: Fetch dev branch
        run: git fetch origin dev
      - name: Run ktlint against dev
        uses: Doist/GithubActionKtlint@master
        with:
          args: "--android --relative"
          target: "origin/dev"

```
