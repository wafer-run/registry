# WAFER Block Registry

Static registry of block manifests for the [WAFER runtime](https://github.com/wafer-run/wafer-run).

## Resolution

The runtime resolves blocks by fetching:

```
https://raw.githubusercontent.com/wafer-run/registry/main/{org}/{block}/manifest.json
```

## Manifest format

```json
{
  "name": "wafer-run/sqlite",
  "summary": "SQLite database block",
  "latest": "0.0.1",
  "versions": {
    "0.0.1": {
      "abi": 1,
      "wasm_url": "https://github.com/wafer-run/wafer-run/releases/download/v0.0.1/sqlite.wasm",
      "crate": "wafer-block-sqlite"
    }
  }
}
```

- `abi` — integer ABI version for WASM compatibility
- `wasm_url` — URL to download the `.wasm` block (omit for native-only blocks)
- `flow_url` — URL to download the `.flow.json` (for flow blocks)
- `crate` — Rust crate name for native compilation

## Publishing

Add or update a `{org}/{block}/manifest.json` file and commit to `main`.
