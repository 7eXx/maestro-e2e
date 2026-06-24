# Maestro E2E — AGENTS.md

## What this is

Maestro (v2.6.1) flow definitions for mobile UI E2E tests. Each `.yaml` in the repo root is a runnable flow.

## CLI

```sh
maestro test <flow.yaml>              # run a flow on connected device/simulator
maestro test --include-tags <tag> .   # run tagged flows
maestro test --format junit <flow>    # CI-friendly output
maestro cloud <apk> <flows_dir/>      # upload for cloud run (app.maestro.dev)
maestro check-syntax <flow.yaml>      # validate YAML
```

## Flows

| File | App under test | Purpose |
|------|---------------|---------|
| `contacts.yaml` | `com.google.android.contacts` | Creates a contact in Google Contacts |
| `tests.yaml` | `it.frigoveneta.webgest` | Login flow for WebGest |

## Structure

- Flows live at the repo root (no `flows/` subdir).
- `.maestro/screenshots/` — screenshot output (gitignored by convention).
- No CI config, README, or package files. No `.gitignore`.

## Notes

- YAML fields are Maestro-internal, not user-env-sensitive — but `tests.yaml` contains a real password; avoid leaking it.
- `contacts.yaml` assumes Italian-locale Android (UI labels like "Consenti", "Crea Contatto", "Salva").
- Running `maestro test` requires a connected device/emulator (iOS Simulator or Android Emulator) or `--device` flag.
- Use `maestro hierarchy` to inspect the current view tree when writing new flows.
