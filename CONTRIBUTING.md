# Contributing

Thank you for your interest in contributing.

## Setup Baseline (run before changes)

From the repository root:

```bash
bash seeds/bootstrap.sh
source ~/.prima-env
bash tools/prime_check.sh
bash tools/scan_lexeme.sh .
```

If you only want to scan a sub-area, use:

```bash
bash tools/scan_lexeme.sh <path>
```

## How to Contribute

1. Fork the repository.
2. Create a feature branch from the default branch.
3. Make focused, small changes with clear commit messages.
4. Open a pull request with a clear summary of:
   - what changed
   - why it changed
   - any follow-up work

## Pull Request Guidelines

- Keep pull requests scoped to one logical change.
- Update relevant documentation when behavior changes.
- Ensure checks/tests pass before requesting review.
- Include setup/validation impact in the PR description when changing `seeds/`, `guides/`, `quests/`, or `tools/`.

## Setup and Pre-PR Done Checklist

- [ ] Bootstrap completed (`bash seeds/bootstrap.sh`)
- [ ] Environment marker loaded (`source ~/.prima-env`)
- [ ] Prime check reviewed (`bash tools/prime_check.sh`)
- [ ] Lexeme scan reviewed (`bash tools/scan_lexeme.sh .` or `bash tools/scan_lexeme.sh <path>`)
- [ ] Relevant docs updated for any onboarding/setup/quest flow change

## Reporting Issues

When opening an issue, include:

- expected behavior
- actual behavior
- steps to reproduce
- environment details (OS, versions, etc.)

## Questions

If anything is unclear, open a discussion or issue before starting large changes.
