# Getting Started

Welcome. This guide gets you from zero to your first quest in one session.

## Supported Environments

| Environment | Package manager path used by `seeds/bootstrap.sh` | Notes |
|---|---|---|
| Termux (Android) | `pkg install -y ...` | Recommended baseline |
| Debian/Ubuntu-like Linux | `apt-get install -y ...` | Supported when `apt-get` is available |
| macOS / other shells | none (manual package install) | Bootstrap still configures dotfiles and `.prima-env`, but package install is skipped unless you install dependencies manually |

## Prerequisites

- `git`
- Internet access for initial package bootstrap
- A shell session (Termux, bash, zsh, etc.)

Required packages (from `seeds/packages.yaml`):
- `git`
- `curl`

Optional packages:
- `vim`
- `python`
- `openssh`

## Step 1 — Clone Sphincter

```bash
git clone https://github.com/Eaprime1/sphincter.git
cd sphincter
```

## Step 2 — Bootstrap the Environment

```bash
bash seeds/bootstrap.sh
```

This installs required packages and sets up your environment marker. It is
idempotent — run it again any time something seems off.

Load your environment marker after bootstrap:

```bash
source ~/.prima-env
```

Expected bootstrap outcomes:
- Required packages are installed via detected package manager (or skipped with a warning when unavailable).
- Dotfiles in `seeds/dotfiles/` are copied into `~/` only when missing.
- `~/.prima-env` exists with `PRIMA_CONCEPT`, `PRIMA_VERSION`, and `PRIMA_ROOT`.

## Step 3 — Read the World

Before starting quests, spend five minutes in `world/lore.md`. Context
makes the quests make sense.

```bash
cat world/lore.md
```

## Step 4 — Your First Quest

Open your first quest:

```bash
cat quests/000-thee-the-door.md
```

Read the lore section. Then follow the tasks. Then run the completion check.

## Step 5 — Validate Setup

```bash
bash tools/prime_check.sh
bash tools/scan_lexeme.sh .
```

## Step 6 — Record Your Progress

Sphincter does not auto-track your path yet. Keep a local log:

```bash
echo "Completed quests/000-thee-the-door.md — $(date)" >> ~/prima-log.txt
```

## Troubleshooting

| Symptom | Likely cause | Resolution |
|---|---|---|
| `pkg: command not found` in Termux | Outdated or mismatched shell environment | Run `pkg update && pkg upgrade` and retry `bash seeds/bootstrap.sh` |
| `apt-get: command not found` | Non-Debian Linux or limited environment | Install required packages (`git`, `curl`) manually, then rerun bootstrap |
| `No supported package manager found` warning | Platform without `pkg`/`apt-get` | Install required packages manually; bootstrap can still set dotfiles and `.prima-env` |
| A package fails to install | Package unavailable on platform | Continue with core required packages; treat unavailable optional packages as non-blocking |
| Quest completion check fails unexpectedly | Incomplete objective or mismatch in expected files | Re-open the quest and follow its completion-check command exactly; if still blocked, open an issue |
