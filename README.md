<img src="https://wcm.io/images/favicon-16@2x.png"/> github-action-maven-build
======

Composite GitHub Action that verifies a Maven Build.

Usage example:

```yaml
# Build validation

name: Build

on:
  push:
    branches:
      - develop
  pull_request:
  workflow_dispatch:

jobs:
  build:

    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        java: [17, 21, 25]
        os: [ubuntu-latest]
        distribution: [temurin]

    steps:
      - name: Maven Build
        uses: wcm-io-devops/github-action-maven-build@v1
        with:
          java-version: ${{ matrix.java }}
          maven-executable: ./mvnw
```

For all parameters, see [action.yml](action.yml).
