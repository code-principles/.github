# code-principles

A curated catalog of software engineering principles, designed to focus AI coding agents on the principles that matter for your codebase.

Modern AI coding agents already know SOLID, OWASP, DDD, and the rest. `.principles` does not teach them — it **focuses and triggers** that knowledge by declaring which engineering lens applies to your project.

## How it works

Place a `.principles` file in your project root:

```
@spring-boot        # activate a group of related principles
CODE-OB-004         # add a specific principle
!CODE-API-012       # suppress one that doesn't fit
```

The AI resolves the full hierarchy before coding or reviewing — innermost files override outermost, so subdirectories can narrow or extend the active set.

## Three commands

| Command | What it does |
|---|---|
| `/scout` | Detects your stack and creates `.principles` files |
| `/prime` | Resolves the hierarchy and prepares your coding frame |
| `/audit` | Reviews code and groups findings by severity |

## What's included

214 principles across 13 categories — SOLID, GoF, DDD, GRASP, Clean Architecture, OWASP Top 10, 12-Factor, concurrency, performance, observability, API design, and more. Every principle cites a verifiable source (book with ISBN, RFC, or paper with DOI).

## Repositories

- [**.principles**](https://github.com/code-principles/.principles) — the principle catalog and tooling

## Status

This is a proof of concept. Errors exist, gaps exist, and groupings are opinionated. See the [Disclaimer](https://github.com/code-principles/.principles/blob/main/DISCLAIMER.md).

Contributions are welcome.
