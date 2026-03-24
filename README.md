# Reusable Workflows

Centralized reusable GitHub Actions workflows for the mbasri-actions organization. These workflows provide standardized CI/CD pipelines that can be called from any repository with minimal configuration.

## Features

- Centralized versioning using [mbasri-actions/semver](https://github.com/mbasri-actions/semver)
- Standardized CI/CD pipelines per technology
- Easy to integrate with minimal configuration
- Extensible to support multiple technologies and use cases

## Requirements

`No Requirements`

## Available Workflows

| Workflow | Description |
| --- | --- |
| `terraform-module-release.yml` | Versioning workflow for Terraform modules |
| `terraform-deploy.yml` | Deploy workflow for Terraform projects (plan, approve, apply) |

## Usage

Here's an example of how to use the Terraform module workflow in your repository:

```yaml
name: Release

on:
  workflow_dispatch:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main ]

permissions:
  contents: write
  models: read
  security-events: write

jobs:
  release:
    uses: mbasri-actions/reusable-workflows/.github/workflows/terraform-module-release.yml@main
```

## Author

* [**Mohamed BASRI**](https://github.com/mbasri)

## License

This is free and unencumbered software released into the public domain. See the [LICENSE](./LICENSE) file for details.
