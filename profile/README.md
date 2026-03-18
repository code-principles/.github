# .principles

**Select the engineering principles you want your AI agent to apply — for code, docs, infrastructure, configuration, schemas, and pipelines.**

A curated catalog of engineering principles, organized into a `.principles` hierarchy that projects declare to guide AI-assisted work across all "X as Code" artifact types.

---

## 💡 Why `.principles`?

> *"The AI already knows everything. The question is: does it know what **you** care about?"*

AI agents already know SOLID, GoF, OWASP, DDD, Clean Architecture, 12-Factor, and the rest. That's not the bottleneck. The bottleneck is that *knowing* all of this is not the same as *applying* the right subset of it to your specific project, your specific stack, and your specific risk profile.

**`.principles` is the bridge between what the AI knows and what it should focus on.** It doesn't teach the AI — it gives it your *intent*. And this applies not just to source code, but to any artifact type treated as code: docs, infrastructure, configuration, schemas, pipelines.

> 🎯 The AI writes the code. You bring the craft.

---

## 🗂️ Not just code — any artifact

`.principles` is built for the **"X as Code"** world: *docs as code*, *infrastructure as code*, *configuration as code*, *pipeline as code*, *schema as code*. All of these live as [plain text in version control](https://github.com/Plain-Text-as-Code) — and all of them benefit from principled review.

The system detects the artifact type of the file being reviewed and loads the right principle stack automatically:

| Artifact type | Examples | Principles |
|---|---|---|
| **Code** | `.java`, `.ts`, `.py`, `.go`, … | SOLID, GoF, fail-fast, input validation, DDD, concurrency, … |
| **Docs** | `README.md`, `DESIGN.md`, `ADR-*.md`, … | DOC-PURPOSE, DOC-MINIMAL, DOC-AUDIENCE, DOC-ACCURACY, … |
| **Config** | `.env`, `application.yaml`, `appsettings.json`, … | 12FACTOR-03, no hardcoded secrets, schema validation, … |
| **Infra** | `.tf`, `Dockerfile`, `Chart.yaml`, … | IaC, immutable infra, idempotency, composable modules, … |
| **Schema** | `.proto`, `.graphql`, `openapi.yaml`, `schema.sql`, … | Backward compatibility, self-describing, consistent naming, … |
| **Pipeline** | `.github/workflows/`, `Jenkinsfile`, … | Idempotency, minimal permissions, no secrets in logs, … |

Run `/audit README.md` and you get doc-specific findings. Run `/audit main.tf` and you get IaC-specific findings. The right principles fire for the right artifact — without any manual configuration.

---

## 🌳 A project is a tree of different worlds

Place `.principles` files in your project — just like `.gitignore`, they cascade down the file tree and subdirectories can add, narrow, or suppress:

```
my-project/
├── .principles                ◄ 🌐 @microservices + @security-focused
├── backend/
│   ├── .principles            ◄ ☕ @spring-boot  (Java · REST · DDD)
│   └── src/payments/
│       └── .principles        ◄ 💳 CODE-RL-IDEMPOTENCY
├── frontend/
│   └── .principles            ◄ ⚛️  @react + @typescript
├── infra/
│   └── .principles            ◄ 🏗️  CODE-AR-INFRASTRUCTURE-AS-CODE + CODE-AR-IMMUTABLE-INFRASTRUCTURE
└── docs/
    └── .principles            ◄ 📝 (doc-specific principles — no security scanning in prose)
```

Before coding or reviewing, the AI walks up from the file to the git root, merges the hierarchy (innermost wins), and loads the full principle content into its context — front-of-mind, the way a senior developer carries their internalized knowledge into every session.

---

## 🔄 Shift left — catch it while you're working, not after

`.principles` supports a **shift-left quality loop** where principles are active *before and during* work, not just when auditing:

```
🔭 /scout  →  ⚡ /prime  →  ✍️ work  →  🔎 /audit  →  🔧 fix  →  🔎 /audit  →  ✅ done
```

These are **AI commands, not CLI tools** — you use natural language:

| Command | What it does |
|---|---|
| `/scout` | Analyzes your project, detects stack and domain, writes `.principles` files |
| `/prime` | Loads the full principle hierarchy into the AI's context before you write a line — code, doc, infra, or otherwise |
| `/audit current changes` | Reviews only what changed since last commit, grouped by severity |
| `/audit the payment module` | Reviews a specific area — you describe it, the AI finds it |

`/prime` is the key step: principles active *while* you work, not just *after*. `/audit` is the quality gut-check — not just bugs, but *"is this artifact well-principled?"*

---

## 📚 What's included

228+ principles across 16 namespaces, actively growing:

**SOLID · Gang of Four · GRASP · DRY · KISS · YAGNI · Clean Architecture · DDD · CQRS · Event Sourcing · 12-Factor · OWASP Top 10 · Functional Programming · Database Design · Security Architecture · Package Design · Concurrency · Performance · Observability · API Design · Testing Strategy · and more**

Every principle cites a verifiable source — book with ISBN, RFC, or paper with DOI. 45 shipped groups (`@spring-boot`, `@react`, `@microservices`, `@security-focused`, `@fp`, `@db`, `@java`, `@kotlin`, `@rust`, …) bundle related principles for common stacks and languages. Many principles include **code examples and diagrams** — not just a definition, but a demonstration of the principle in practice.

New namespaces in progress: continuous delivery, hexagonal architecture, and more. See [TODO.md](https://github.com/dot-principles/principles/blob/main/TODO.md).

---

## 📦 Repositories

- [**.principles**](https://github.com/dot-principles/principles) — the principle catalog, groups, layer model, and slash commands
- [**Plain-Text-as-Code**](https://github.com/Plain-Text-as-Code) — the manifest behind the approach: version-controlled plain text as a first-class engineering practice

---

## Status

v0.2.0 — proof of concept. Errors exist, gaps exist, groupings are opinionated. See the [Disclaimer](https://github.com/dot-principles/principles/blob/main/DISCLAIMER.md). Contributions are welcome.
