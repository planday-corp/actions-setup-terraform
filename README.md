# Actions Terraform setup

This repository contains a Github action to setup Terraform with the version string set in `required_version` from a `terraform` block.

```
terraform {
  required_providers {
    ...
  }

  required_version = ">= 1.1.0"  # <--- capture this version string
}
```

## Usage

Use this workflow in your pipeline:

```yaml
- name: Setup Terraform from the 'required_version'
  uses: planday-corp/actions-setup-terraform/.github/workflows/setup-terraform.yml@v1
```