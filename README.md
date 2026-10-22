# Continua

This is Continua's open-source developer repository. It contains released public contracts, the
customer CLI, MCP server, application SDKs, agent plugins, examples, and the tooling needed to
build and verify them.

Continua's hosted backend, console, workers, deployment assets, platform adapters, and private
qualification evidence live in the private `continua-cloud` repository. The regional database
substrate lives in the private `continua-core` repository. Neither implementation is mirrored or
imported here.

## Repository map

| Path | Responsibility |
| --- | --- |
| `contracts` | Digest-bound released public API, event, operation, and manifest bundles |
| `clients/cli` | Predictable human and automation CLI with structured output and stable exits |
| `clients/mcp` | MCP tools exposing the same bounded public operations to coding agents |
| `sdks` | Application and control clients for TypeScript, Python, Go, and Rust |
| `plugins` | Installable Codex and Claude Code integrations built on the public MCP server |
| `examples` | Complete setup, success, refusal, recovery, and cleanup journeys |
| `tools/contracts` | Bundle verification and generated-transport tooling |

## Agent-first contract

An agent should be able to discover Continua, authenticate with project-scoped authority, preview a
change, execute it idempotently, follow its operation, and return a durable receipt without reading
private implementation docs or exposing secrets and bulk data to model context.

The CLI, MCP server, SDKs, plugins, and console are different presentations of the same public
operations. They share stable errors, idempotency, pagination, bounded retries, operation handles,
and guarantee manifests. None is a second workflow or authorization authority.

## Release boundary

Contracts arrive as deterministic, digest-bound bundles promoted from their owning private
repository. Generated transports are derived from those bundles and stay separate from handwritten
ergonomics. A client does not claim support for a contract version until common conformance vectors
and its real integration journey pass.

The repository is licensed under [Apache-2.0](LICENSE).
