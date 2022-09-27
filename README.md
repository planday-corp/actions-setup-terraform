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

### Inputs

`terraform_wrapper`: Whether to install a wrapper to wrap subsequent calls of the terraform binary and expose its STDOUT, STDERR, and exit code as outputs named `stdout`, `stderr`, and `exitcode` respectively. See the [documentation](https://github.com/hashicorp/setup-terraform/tree/v2#inputs) for more information.
Defaults to `false`.


### Outputs

`terraform_version`: Terraform version from the `required_version` setting.

### Examples

Use this workflow in your pipeline:

```yaml
- name: Setup Terraform from the 'required_version'
  uses: planday-corp/actions-setup-terraform@v1
```

or to install the wrapper:

```yaml
- name: Setup Terraform from the 'required_version'
  uses: planday-corp/actions-setup-terraform@v1
  with:
    terraform_wrapper: true
```