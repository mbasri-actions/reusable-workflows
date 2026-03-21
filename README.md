# Reusable Workflows

Centralized reusable GitHub Actions workflows for the mbasri-actions organization. These workflows provide standardized CI/CD pipelines that can be called from any repository with minimal configuration.

## Features

- Centralized versioning using [mbasri-actions/gitversion](https://github.com/mbasri-actions/gitversion)
- Standardized CI/CD pipelines per technology
- Easy to integrate with minimal configuration
- Extensible to support multiple technologies and use cases

## Requirements

`No Requirements`

## Available Workflows

| Workflow | Description |
| --- | --- |
| `terraform-module.yml` | Versioning workflow for Terraform modules |

## Usage

Here's an example of how to use the Terraform module workflow in your repository:

```yaml
name: Tag Version

on:
  workflow_dispatch:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main ]

permissions:
  contents: write
  models: read

jobs:
  gitversion-and-push:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v6
      with:
        fetch-depth: 0
        fetch-tags: true

    - name: Generate semantic version and tag repository
      uses: mbasri-actions/gitversion@main
      id: gitversion
      with:
        isTerraformModule: 'true'
```

## Author

* [**Mohamed BASRI**](https://github.com/mbasri)

## License

This is free and unencumbered software released into the public domain. See the [LICENSE](./LICENSE) file for details.
