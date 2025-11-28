<!-- BEGIN_TF_DOCS -->
# Renovate + HCP Terraform Private Registry Integration Demo

This demonstration showcases how **Renovate** automatically detects and updates dependencies
from **HCP Terraform Private Registry**, ensuring your Terraform infrastructure code stays
current with the latest module and provider versions.

## What This Demo Demonstrates

**Key Integration Points:**
- Automated dependency detection for private Terraform modules hosted in HCP Terraform
- Automatic version updates for both private modules and public providers
- Pull request automation for infrastructure-as-code dependency management

## Demo Components

**1. Private Module Dependency:**

- **Module:** `benoitblais-hashicorp/uuid/random` (version 1.0.0)
- **Source:** HCP Terraform Private Registry (`app.terraform.io`)
- **Purpose:** Generates a random UUID for demonstration purposes

**2. Public Provider Dependency:**

- **Provider:** `hashicorp/random` (version 3.7.2)
- **Source:** Public Terraform Registry
- **Purpose:** Enables random resource generation

**3. Terraform Version Constraint:**

- **Required Version:** >= 1.7.5

## How Renovate Works in This Demo

1. **Discovery:** Renovate scans the repository and identifies:
   - Private module reference in `main.tf`
   - Provider version constraints in `versions.tf`
   - Terraform core version requirements

2. **Version Monitoring:** Renovate periodically checks:
   - HCP Terraform Private Registry for new versions of `uuid/random` module
   - Public registry for updates to the `random` provider
   - Terraform releases for core version updates

3. **Automated PRs:** When updates are available, Renovate:
   - Creates pull requests with version bumps
   - Includes release notes and changelogs
   - Allows testing before merging

## Demo Value Proposition

This setup demonstrates enterprise-grade dependency management for Terraform, showing how organizations can:

- **Maintain security** by staying current with patches
- **Reduce manual overhead** of tracking module/provider updates
- **Enable governance** through controlled, reviewable updates
- **Support hybrid registries** (private + public) seamlessly

## Expected Renovate Behavior

When configured, Renovate will monitor and propose updates for:

- ✅ Private module version (`module.uuid`)
- ✅ Random provider version
- ✅ Terraform core version constraint

## Documentation

## Requirements

The following requirements are needed by this module:

- <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) (>= 1.7.5)

- <a name="requirement_random"></a> [random](#requirement\_random) (3.7.2)

## Modules

The following Modules are called:

### <a name="module_uuid"></a> [uuid](#module\_uuid)

Source: app.terraform.io/benoitblais-hashicorp/uuid/random

Version: 1.0.0

## Required Inputs

No required inputs.

## Optional Inputs

No optional inputs.

## Resources

No resources.

## Outputs

The following outputs are exported:

### <a name="output_uuid"></a> [uuid](#output\_uuid)

Description: The generated uuid presented in string format.

<!-- markdownlint-enable -->
<!-- END_TF_DOCS -->