name: Release

on:
  pull_request:
    types: [ closed ]
  workflow_dispatch:
    inputs:
      version:
        description: Semantic version (e.g. v1.0.0)
        required: true

jobs:
  release:
    if: >-
      github.event_name == 'workflow_dispatch' ||
      github.event.pull_request.merged == true && startsWith(github.event.pull_request.head.ref, 'release/')
    runs-on: ubuntu-latest
    timeout-minutes: 5
    env:
      GH_TOKEN: ${{ github.token }}
      GH_REPO: ${{ github.repository }}
      RELEASE_BRANCH: ${{ github.event.pull_request.head.ref || github.event.inputs.version }}

    steps:
      - name: Create release draft
        id: release
        run: |
          version=${RELEASE_BRANCH#release/}
          gh release create ${version} --title ${version} --generate-notes
