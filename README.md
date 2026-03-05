# 🐙 krakenn

**krakenn** is a cross-platform CLI tool that intelligently merges **production database data** with the **test/staging schema**, allowing developers to test new schema changes on real data—safely, efficiently, and repeatably.

---

## 🚧 Status

🔨 This project is currently under active development.  
Expect rapid iteration, breaking changes, and incomplete features.

---

## 🌟 Problem Statement

In typical software development lifecycles, test/staging environments often evolve ahead of production in terms of schema. However, production holds the most realistic and critical data. Reconciling these two environments is difficult and error-prone.

> krakenn aims to create the "ideal test DB": **latest schema + real data** — intelligently, with full control and safety.

---

## ✅ Key Features (Planned)

- 🔍 Schema diffing between two PostgreSQL databases (`prod` and `test`)
- 💡 Smart SQL migration plan generation
- 🔄 Data copy from prod → test with schema alignment
- 🧠 Default value filling and type-safe transformations
- 🔐 Optional data masking for sensitive fields
- 🚫 Foreign key & constraint-aware data sync
- 📦 Cross-platform CLI (Mac, Linux, Windows)

---

## 🚧 Phases of Development

### Phase 1 — MVP (CLI Tool)

- [ ] Connect to two PostgreSQL databases
- [ ] Detect and output schema differences
- [ ] Generate migration SQL for test schema
- [ ] Insert prod data into test schema (with column alignment)
- [ ] CLI with subcommands:
  - `krakenn diff`
  - `krakenn migrate`
  - `krakenn sync-data`

### Phase 2 — Schema & Data Enhancements

- [ ] Handle new columns with defaults/nulls
- [ ] Rename/match fields using rules
- [ ] Dry-run support and verbose logs

### Phase 3 — Data Masking & Profiles

- [ ] Built-in anonymization (`faker`, `hash`)
- [ ] Config-driven sync profiles (JSON/YAML)
- [ ] Test output validation (row count, hash match, etc.)

### Phase 4 — GUI/Visualization (Optional)

- [ ] Electron or Web-based UI
- [ ] Schema diff viewer
- [ ] Data mapping visualization

---

## 🔧 Tech Stack

### Core Language

- **TypeScript + Node.js** for portability and developer speed

### DB & CLI

- `pg`: PostgreSQL client
- `commander`: CLI framework
- `chalk`: Terminal output styling
- `inquirer`: Interactive prompts (for flags/config)
- `zod`: Schema validation

### Packaging

- `pkg` or `esbuild` to produce standalone binaries
- OS support: macOS, Linux, Windows

---

## 📦 Installation (Planned)

```bash
# via npm
npm install -g krakenn

# or download binary from Releases
./krakenn --help
```
