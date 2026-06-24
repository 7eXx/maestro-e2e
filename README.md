# Maestro E2E

[Maestro](https://maestro.mobile.dev) v2.6.1 flow definitions for mobile UI end-to-end tests.

## Prerequisites

- [Maestro CLI](https://maestro.mobile.dev/getting-started/installing-maestro) installed
- A connected Android emulator/device or iOS simulator

## Usage

```sh
# Run a single flow
maestro test contacts.yaml

# Run all flows in the directory
maestro test .

# Validate flow syntax
maestro check-syntax contacts.yaml
```

## Flows

| Flow | App | Description |
|------|-----|-------------|
| `contacts.yaml` | Google Contacts | Creates a contact (Italian locale) |
| `tests.yaml` | WebGest (`it.frigoveneta.webgest`) | Login flow |

## Structure

```
├── contacts.yaml
├── tests.yaml
└── .maestro/
    └── screenshots/
```

## Resources

- [Maestro Docs](https://maestro.mobile.dev)
- [Flow Reference](https://maestro.mobile.dev/api-reference/commands)
