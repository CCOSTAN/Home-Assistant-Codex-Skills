# Contributing

Contributions that make these skills safer, clearer, or more reusable are welcome.

## Before opening a pull request

1. Keep each skill self-contained: `SKILL.md` is the entry point and relative links must remain inside that skill or this repository.
2. Use generic example entity IDs, hostnames, users, domains, and paths.
3. Never include credentials, access tokens, webhook IDs, private IP addresses, personal data, local workstation paths, or machine-specific agent instructions.
4. Keep Home Assistant examples syntactically valid and avoid claiming an entity or service exists unless it is clearly presented as an example.
5. Add or update tests when validator behavior changes.

## Validation

Run all tests from the repository root:

```sh
python -m unittest discover -s homeassistant-dashboard-designer/tests -p "test_*.py"
python -m unittest discover -s homeassistant-yaml-dry-verifier/tests -p "test_*.py"
python -m unittest discover -s network-architecture-diagrammer/tests -p "test_*.py"
```

Install PyYAML if the YAML verifier tests report that it is unavailable:

```sh
python -m pip install PyYAML
```

Also run a public-content scan appropriate for your environment and review the complete Git diff before committing.

## Pull requests

- Explain the user-facing problem and the behavior change.
- Keep unrelated formatting or content changes out of the pull request.
- Include validation results.
- Update the relevant README when installation, invocation, or output changes.
