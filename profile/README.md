# ODOM Technology

ODOM Technology documents the design, construction, operation, and recovery of a
small three-node homelab. Public repositories contain sanitized learning material
and reusable examples; exact infrastructure and operational configuration remain
private.

## Public projects

- **homelab-docs** — step-by-step architecture and operations guides.
- **homelab-blueprints** — reusable automation, templates, and example deployments.

Brand sources, exact infrastructure, deployment configuration, and private application
code are maintained in restricted repositories until explicitly approved for release.

## Repository map

| Repository | Visibility | Responsibility |
| --- | --- | --- |
| `homelab-docs` | Public | Sanitized architecture, build, operations, and recovery guides |
| `homelab-blueprints` | Public | Reusable examples, schemas, and automation patterns |
| `brand-assets` | Private | Brand sources, release assets, and validation |
| `homelab-infrastructure` | Private | Exact inventory, Proxmox, network, automation, and recovery source |
| `homelab-services` | Private | Active service placement, deployment, configuration, and runbooks |
| `internal-dashboard` | Private | Tailnet-only dashboard product and application source |

Substantial custom applications receive their own repositories. Their deployment
integration remains in `homelab-services`.

## Project principles

- Rebuildable infrastructure instead of undocumented manual configuration.
- Secure defaults and explicit trust boundaries.
- Recovery procedures tested from clean installations.
- Examples that never disclose production secrets, addresses, or identifiers.
