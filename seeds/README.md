# Seeds

Seeds are the bootstrap layer — everything needed to get the concept's environment
up and running from a fresh terminal session.

## Files

| File | Purpose |
|---|---|
| `bootstrap.sh` | Run this first — installs packages and sets up dotfiles |
| `packages.yaml` | Declarative list of required and optional packages |
| `dotfiles/` | Config files deployed to `~` by the bootstrap script |

## Usage

```bash
# From inside a fresh Termux or terminal session:
bash seeds/bootstrap.sh
```

The bootstrap script is idempotent — safe to run more than once.

## Supported Setup Paths

| Environment | Manager auto-detected | Behavior |
|---|---|---|
| Termux | `pkg` | Installs required packages, then deploys dotfiles and `.prima-env` |
| Debian/Ubuntu-like Linux | `apt-get` | Installs required packages, then deploys dotfiles and `.prima-env` |
| Other environments | none | Skips package installation with warning; still deploys dotfiles and `.prima-env` |

## Packages

Source of truth: `seeds/packages.yaml`

- Required: core dependencies needed for quest flow (`git`, `curl`)
- Optional: quality-of-life packages (`vim`, `python`, `openssh`)

## Expected Bootstrap Outcomes

- Required packages are installed when a supported package manager is available.
- Existing dotfiles in `$HOME` are preserved (bootstrap skips files that already exist).
- `~/.prima-env` is created with concept metadata and root path.

## Troubleshooting Matrix

| Symptom | Resolution |
|---|---|
| Package manager command not found | Install required packages manually (`git`, `curl`) and rerun bootstrap |
| Permission or package install failure | Retry with a refreshed package index (`pkg update` or `apt-get update`) |
| Dotfile not copied | Check whether the target already exists in `$HOME` (existing files are intentionally not overwritten) |
| `.prima-env` missing | Re-run `bash seeds/bootstrap.sh` from repo root and check write permissions in `$HOME` |

## Dotfiles

Files in `seeds/dotfiles/` are copied to `~/` during bootstrap.
Name them with a leading dot as they should appear at the destination:

```
seeds/dotfiles/.bashrc         → ~/.bashrc
seeds/dotfiles/.profile        → ~/.profile
seeds/dotfiles/.prima-env      → ~/.prima-env
```

## Design Notes

Seeds should be **minimal and additive** — they should not overwrite existing
config without checking. A player's home directory may already have things in it.
When in doubt, append rather than replace.

☯
