# Quests

This folder contains all quests for the prima terminal concept.

## Structure

```
quests/
  000-thee-the-door.md ← initiation quest — set identity and open the door
  QUEST_SCHEMA.md      ← the quest format spec (read this first)
  example/             ← starter arc — ships with the template
    001-awakening.md   ← the first quest every player receives
  <arc-name>/          ← add new arcs here as folders
```

## Contributing a Quest

1. Read `QUEST_SCHEMA.md` — the format is a contract.
2. Pick an existing arc folder or create a new one.
3. Number your quest sequentially within the arc.
4. The `requires` and `unlocks` fields connect quests into a graph — use them.
5. The completion check must be runnable and deterministic.

## Arc Index

| Arc | Description | Quest Count |
|---|---|---|
| root | Initiation entrypoint (`000-thee-the-door.md`) | 1 |
| example | Starter arc available after quest 000 | 1 |

Update this table as arcs are added.
