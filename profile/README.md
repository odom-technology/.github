# ODOM Technology

ODOM Technology documents the design, construction, operation, and recovery of a
small, segmented Proxmox homelab with rack-independent household networking. Public
repositories contain sanitized learning material and reusable examples; exact
infrastructure and operational configuration remain private.

The current work is focused on final network segmentation, clean infrastructure
rebuilds, off-host recovery, and the service definitions that follow them. Public
documentation describes the target pattern and must not be interpreted as a live
service-status page.

## Public projects

- **homelab-docs** — step-by-step architecture and operations guides.
- **homelab-blueprints** — sanitized reference architectures, schemas, and examples;
  reusable automation remains under development.

Brand sources, exact infrastructure, planned deployment configuration, and private
product work are maintained in restricted repositories until explicitly approved for
release.

## Repository map

| Repository | Visibility | Responsibility |
| --- | --- | --- |
| `homelab-docs` | Public | Sanitized architecture, build, operations, and recovery guides |
| `homelab-blueprints` | Public | Sanitized examples, schemas, and future automation patterns |
| `brand-assets` | Private | Brand sources, release assets, and validation |
| `homelab-infrastructure` | Private | Exact inventory, Proxmox, network, automation, and recovery source |
| `homelab-services` | Private | Planned service catalog, placement, deployment design, and runbooks |
| `internal-dashboard` | Private | Tailnet-only dashboard requirements and future application source |

Substantial custom applications receive their own repositories. Their deployment
integration remains in `homelab-services`.

## Project principles

- Rebuildable infrastructure instead of undocumented manual configuration.
- Secure defaults and explicit trust boundaries.
- Recovery procedures tested from clean installations.
- Examples that never disclose production secrets, addresses, or identifiers.
