# Continua public repository guidance

This repository contains Continua's open-source developer surface: released contracts, SDKs, CLI,
MCP server, plugins, examples, and their build and conformance tooling.

## Read first

1. `README.md` for the public/private boundary.
2. The released manifest under `contracts/` when present.
3. The nearest package README and its conformance tests before changing a client.

## Hard rules

- This repository is wire-only. Never import `continua-cloud`, `continua-core`, `metamorph-saas`,
  deployment configuration, or private product contracts.
- Released snapshots arrive only through the digest-bound promotion process. Do not hand-edit
  generated contracts or generated transport bindings.
- Keep generated transport code separate from handwritten ergonomics such as discovery, preview,
  idempotency, retries, operation following, streaming, and receipt handling.
- The CLI, MCP server, SDKs, and plugins expose the same public operations. They do not implement a
  second orchestration or authorization authority.
- Keep passwords, keys, reusable credentials, one-use transfer capabilities, database rows, and
  SQL literals out of model context, logs, diagnostics, and receipts.
- Examples reference credentials through environment variables or configuration files and cover
  success, refusal, retry or recovery, and cleanup without committed secrets.
- Add only packages needed by a working slice. Empty future implementations and unsupported API
  claims do not belong on `main`.

## Working method

Use the same evidence progression as Cloud: implementation plan, development with quick focused
tests, manual journey, Smoke against a real published service, then Qualification for the supported
language/runtime and contract matrix. Plans specify outcomes and safety boundaries while leaving
ordinary implementation choices to the agent.
