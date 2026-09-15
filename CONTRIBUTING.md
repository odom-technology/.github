# Contributing

## Workflow

1. Read the target repository's README, contribution guide, and local instructions.
2. Open an issue before substantial product, interface, or architectural changes.
3. Unless the repository documents another workflow, create work from the `dev` branch.
4. Keep commits focused and explain user-facing and operational consequences.
5. Update tests, examples, and documentation with behavior changes.
6. Confirm that all submitted material is sanitized.

## Sanitization

Never commit credentials, recovery codes, private keys, internal endpoints, private
network details, device identifiers, production inventory, customer information, or
other personal data to a public repository. Sanitize logs and screenshots. Use reserved
example domains, RFC 5737 documentation addresses, and clearly marked placeholder
values in documentation and tests.

## Licensing

The target repository's license and contribution terms control. ODOM Tech does not
apply an organization-wide default license. If a repository has no license, do not
assume permission to copy, modify, or redistribute its contents.
