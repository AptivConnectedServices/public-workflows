# Public Workflows
This repository contains Aptiv Connected Services (ACS) reusable workflows that are intended to be shared/reused in other ACS private repositories. 

These [reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows) are maintained to help standardize actions and reduce code duplication across the organization.

## Basic Usage
To use one of these reusable workflow in your repository, you can use the `uses` directive in the `jobs` section of your workflow. It should reference one of the workflows in the [.github/workflows](.github/workflows) directory.

The example below uses the [.github/workflows/docker.yml](.github/workflows/docker.yml) workflow to build a docker image and pushes it to ghcr.io if it was a push action to the `main` branch or a tag of the form `v*.*.*`.
```yaml
name: Docker

on:
  push:
    branches:
      - main
    tags:
      - "v*.*.*"
  pull_request:
    paths:
      - 'Dockerfile'
      - 'requirements.txt'
      - 'src/**'

jobs:
  example:
    uses: AptivConnectedServices/public-workflows/.github/workflows/docker.yml@docker-v1
    with:
      name: ${{ github.repository }}
      push: ${{ github.event_name == 'push' }}
```
