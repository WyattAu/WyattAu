# WyattAu Kit Compatibility Matrix

All crates are published on crates.io under the `WyattAu` ecosystem. Layer model:
**L0** leaf utilities (no internal deps) → **L1** core primitives → **L2** service infrastructure → **L3** application-level frameworks.

Versions below are read from each repo's `Cargo.toml` and verified against vendored copies in
[`ecom-engine/crates/vendor/`](https://forgejo.wyattau.com/Kiln/ecom-engine).

## L0 — Leaf utilities

| Crate | Version | Purpose | Layer | Consumers | Optional features of note |
|---|---|---|---|---|---|
| `salting` | 0.2.0 | Deterministic salt derivation for keyed hashing | L0 | suture, Tachyon, crawlkit, CivitForge, clawdius | — |
| `error-codes` | 0.1.0 | Stable numeric/error-code registry (repo: `errcode`) | L0 | error-classify | — |
| `cryptkit` | 0.1.0 | AEAD encryption, key handling, hashing helpers | L0 | ferro, aether-core, Tachyon, CivitForge, clawdius, crawlkit | — |
| `chronoshift` | 0.2.0 | Time abstractions and clock injection (repo: `clock`) | L0 | — | — |
| `typed-id-new` | 0.1.0 | Strongly-typed identifiers (repo: `typed-id`) | L0 | — | `derive` (typed-id-derive) |
| `validkit` | 0.1.0 | Composable input validation primitives | L0 | ferro, Tachyon, CivitForge, EvergreenShims | — |
| `geo-kit` | 0.1.1 | Geocoding / geo utilities (UK postcode incl. GIR 0AA, etc.) | L0 | ecom-engine (vendored) | — |
| `simd-tokenizer` | 0.1.0 | Token estimation — safe SWAR whitespace scan (5× scalar), optional tiktoken | L0 | — | `tiktoken` |
| `delta-kit` | 0.1.0 | Rabin-rolling binary-safe delta codec (rsync-style, wire-compatible with suture) | L0 | — | — |
| `crdts-kit` | 0.1.0 | RGA replicated string — tombstones, causal convergence (proptest-verified), serde (repo: `crdts-kit`) | L0 | — | `serde`, `uuid` off for wasm |
| `model-router` | 0.1.0 | Cost-aware LLM routing — pricing tables, USD budget tracking, fallback chains (genai companion) | L0 | — | `genai` adapter |

## L1 — Core primitives

| Crate | Version | Purpose | Layer | Consumers | Optional features of note |
|---|---|---|---|---|---|
| `error-classify` | 0.2.0 | Error trait classification (repo: `app-error`); builds on `error-codes` | L1 | — | — |
| `tokenkit` | 0.1.1 | Token minting/verification | L1 | ferro, aether-core, accessctl, barbican, ws-barbican, Tachyon, CivitForge, clawdius, crawlkit, suture | — |
| `oauth-toolkit` | 0.2.0 | OAuth flow helpers — PKCE, web social login, desktop loopback capture, mail-provider presets (Gmail/Outlook/Yahoo/AOL/Fastmail) | L1 | — | — |
| `loop-retry` | 0.1.0 | Retry loops with backoff (repo: `retry-backoff`) | L1 | crawlkit, EvergreenShims, ecom-engine (vendored) | — |
| `shutdown-kit` | 0.2.0 | Graceful shutdown coordination (repo: `graceful`) | L1 | axum-stack | — |
| `breaker` | 0.3.0 | Circuit breaker | L1 | ferro, aether-core, fetchkit | — |
| `throttle-kit` | 0.3.0 | Rate limiting / throttling (repo: `ratelimit`) | L1 | ferro | — |
| `shared-state` | 0.1.0 | Shared/app-state plumbing | L1 | — | — |
| `eventbus-kit` | 0.2.0 | In-process event bus (repo: `eventbus`) | L1 | — | — |
| `cas-kit` | 0.1.0 | BLAKE3 content-addressed blob store — packfiles, zstd, verify-on-read (zero-unwrap) | L1 | — | `zstd` (default) |
| `webauthn-kit` | 0.1.0 | Custom CTAP2/COSE WebAuthn over `ring` — registration/authentication verification, sign-count state machine, challenge/replay store (repo: `webauthn-kit`) | L1 | — | `serde` |

## L2 — Service infrastructure

| Crate | Version | Purpose | Layer | Consumers | Optional features of note |
|---|---|---|---|---|---|
| `cache-pal` | 0.3.0 | Caching abstractions (repo: `cachekit`) | L2 | — | — |
| `poolkit` | 0.1.0 | Connection/resource pooling | L2 | — | — |
| `envstack` | 0.2.0 | Layered env/config loading | L2 | crawlkit | — |
| `otelkit` | 0.1.0 | OpenTelemetry setup helpers | L2 | EvergreenShims | — |
| `healthkit` | 0.1.0 | Health/readiness endpoints | L2 | axum-stack, ecom-engine (vendored) | — |
| `webhookkit` | 0.2.0 | Signed outbound webhooks + HMAC verification | L2 | ecom-engine (vendored) | — |
| `mailkit` | 0.2.0 | Transactional email sending + JWZ-lite message threading | L2 | ferro | — |
| `tantivy-helper` | 0.2.0 | Tantivy search index helpers (repo: `tantivy-ext`) | L2 | — | — |
| `api-paginate` | 0.1.0 | Cursor/offset pagination (repo: `paginate`) | L2 | — | — |
| `decimal-money` | 0.2.0 | Decimal money type (repo: `money`) | L2 | billing-kit, ecom-engine (vendored) | — |
| `tamper-audit` | 0.1.0 | Tamper-evident audit logging (repo: `auditlog`) | L2 | — | — |
| `json-envelope` | 0.1.0 | Signed/encapsulated JSON payloads | L2 | — | — |
| `http-errors` | 0.1.0 | HTTP error mapping (repo: `http-error`) | L2 | — | — |
| `pid-manager` | 0.1.0 | PID file management for services | L2 | — | — |
| `testkit` | 0.1.0 | Shared test utilities/fixtures | L2 | — | dev-dep only by design |
| `media-kit` | 0.1.0 | Media upload/processing helpers | L2 | ferro, Tachyon, ecom-engine (vendored) | — |
| `flag-kit` | 0.1.0 | Feature flags | L2 | ferro | — |
| `blobkit` | 0.2.0 | Object storage abstraction | L2 | EvergreenShims, ecom-engine (vendored) | — |
| `ws-kit` | 0.2.0 | WebSocket server/session management | L2 | aether-core, ferro, ws-barbican | — |
| `billing-kit` | 0.1.0 | Billing/pricing primitives | L2 | — | — |
| `api-types` | 0.1.0 | Shared API request/response types | L2 | — | — |
| `axum-stack` | 0.1.0 | Opinionated axum router/middleware stack (healthkit + shutdown-kit) | L2 | — | — |
| `multi-chain-wallet` | 0.1.0 | Multi-chain wallet/HDWallet (repo: `hdwallet`) | L2 | — | — |
| `actor-kit` | 0.1.0 | Work-stealing actor runtime — OTP supervision trees, crossbeam steal, bounded backpressure; `ResourcePolicy` hook | L2 | — | `serde`, `unsafe-pool` (opt-in arena), `zero-copy` |
| `docs-pipeline` | 0.1.0 | Markdown → HTML pipeline — pulldown 0.13, tree-sitter 0.25 highlighting (TOML+Markdown restored), TOC, sanitize, MDX | L2 | Tachyon (tachyon-renderer re-export) | per-language `lang-*` features |

## L3 — Application frameworks

| Crate | Version | Purpose | Layer | Consumers | Optional features of note |
|---|---|---|---|---|---|
| `barbican` | 0.1.0 | Secrets/credential custody service toolkit | L3 | ws-barbican | — |
| `accessctl` | 0.1.0 | Access control / authorization | L3 | — | — |
| `fetchkit` | 0.1.0 | Hardened outbound HTTP fetcher (breaker-integrated) | L3 | — | — |
| `ws-barbican` | 0.1.0 | WebSocket transport to barbican (ws-kit + tokenkit) | L3 | aether-core | — |

## Vendored-copy policy & drift detection

`ecom-engine` vendors a pinned set of kits under `crates/vendor/` (currently:
`blobkit`, `geo-kit`, `media-kit`, `money`→`decimal-money`, `webhookkit`, `healthkit`,
`loop-retry`) so the engine builds against reviewed copies rather than floating crates.io
versions. Homebite consumes these kits transitively via the engine.

Policy:

1. Vendor copies track published crates.io versions — they must not silently diverge.
2. [`scripts/check_vendor_drift.sh`](https://forgejo.wyattau.com/Kiln/ecom-engine) (in
   ecom-engine) compares each vendored `Cargo.toml` version against crates.io; exit 1 on drift.
   Directory names may differ from crate names (`money` → `decimal-money`,
   `retry-backoff` → `loop-retry`); the script maps these.
3. The Forgejo workflow `.forgejo/workflows/vendor-drift.yml` runs the check weekly
   (Mondays 06:00 UTC) plus on-demand via `workflow_dispatch`, so a stale kit (cf. the
   webhookkit staleness incident) is caught before it bites.

When bumping a vendored kit: publish to crates.io, update the engine's vendor copy, then
update the version column here.
