# Sphincter — Prima Terminal Concept

Sphincter is a quest-driven terminal concept repository. It turns command-line work into a structured path: bootstrap, enter the world, complete quests, and validate progress.

## Start Here

1. Clone the repository:
   ```bash
   git clone <your-fork-url>
   cd <your-repo-name>
   ```
2. Bootstrap the environment:
   ```bash
   bash seeds/bootstrap.sh
   source ~/.prima-env
   ```
3. Start the first quest:
   ```bash
   cat quests/000-thee-the-door.md
   ```
4. Run baseline validation:
   ```bash
   bash tools/prime_check.sh
   bash tools/scan_lexeme.sh .
   ```

## Documentation Index

| Area | Purpose | Entry |
|---|---|---|
| Getting started | Full onboarding walkthrough | [guides/getting-started.md](guides/getting-started.md) |
| Seeds / setup | Bootstrap behavior, packages, dotfiles | [seeds/README.md](seeds/README.md) |
| First quest | Concept naming and first actions | [quests/000-thee-the-door.md](quests/000-thee-the-door.md) |
| Quests | Quest structure and arc management | [quests/README.md](quests/README.md) |
| World | Lore and conceptual setting | [world/README.md](world/README.md) |
| Intake | THEE/YOD/EMBER intake flow | [intake/README.md](intake/README.md) |
| Validation checks | Prime state and lexeme scan checks | [tools/prime_check.sh](tools/prime_check.sh), [tools/scan_lexeme.sh](tools/scan_lexeme.sh) |

## Setup Validation

Run these checks after setup and before opening a PR:

```bash
bash tools/prime_check.sh
bash tools/scan_lexeme.sh <path>
```

Example for this repository root:

```bash
bash tools/scan_lexeme.sh .
```

Done checklist:

- [ ] `bash seeds/bootstrap.sh` completed successfully
- [ ] `source ~/.prima-env` loaded without error
- [ ] `quests/000-thee-the-door.md` reviewed and started
- [ ] `bash tools/prime_check.sh` passes
# Sphincter 🍥 — Prima Terminal Concept

Sphincter is a quest-driven terminal concept repository. It turns command-line work into a structured path: bootstrap, enter the world, complete quests, and validate progress.

## Project Space Ownership

- `quests/`: add or evolve quest arcs and completion checks
- `guides/`: improve onboarding and practical how-to documentation
- `seeds/`: maintain bootstrap logic, package definitions, and dotfiles
- `world/`: maintain lore and conceptual framing
- `intake/`: maintain capture and triage flow for incoming fragments

## Repository Maturity Roadmap

- [ ] **Phase 1 — Onboarding + setup cleanup**  
      Keep startup flow current and remove stale setup friction.
- [ ] **Phase 2 — Content consistency (quests/world/guides)**  
      Align quest progression, lore, and practical docs into one coherent path.
- [ ] **Phase 3 — Automation polish**  
      Strengthen repeatable checks and contribution hygiene across PRs.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution workflow and PR expectations.
