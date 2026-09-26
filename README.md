# Wyatt Au — Rust kit ecosystem for production services

A kit ecosystem for building production Rust services: **~60 published kits across eight domains** (144 crates on crates.io, 50k+ lifetime downloads), all built to one [FAANG/defence-grade gate matrix](https://github.com/WyattAu/engineering-standards) — shared CI enforces **loom** model checking on concurrency primitives, **miri** on pointer logic, **cargo-fuzz** harnesses on untrusted parsers, **mutation testing** on test quality, **cargo-vet** (enforcing) on the supply chain, and **per-release provenance** (commit, toolchain, artifact SHA-256). The estate dogfoods itself: [estate-integration](https://github.com/WyattAu/estate-integration) composes the kits in one cross-crate suite — tokenkit auth → breaker → throttle-kit → healthkit → mailkit → blobkit/cas-kit — proving they ship as a system, not just as crates.

[![tokenkit](https://img.shields.io/crates/d/tokenkit.svg?label=tokenkit)](https://crates.io/crates/tokenkit)
[![cryptkit](https://img.shields.io/crates/d/cryptkit.svg?label=cryptkit)](https://crates.io/crates/cryptkit)
[![validkit](https://img.shields.io/crates/d/validkit.svg?label=validkit)](https://crates.io/crates/validkit)
[![mailkit](https://img.shields.io/crates/d/mailkit.svg?label=mailkit)](https://crates.io/crates/mailkit)
[![breaker](https://img.shields.io/crates/d/breaker.svg?label=breaker)](https://crates.io/crates/breaker)
[![throttle-kit](https://img.shields.io/crates/d/throttle-kit.svg?label=throttle-kit)](https://crates.io/crates/throttle-kit)

## Crate index

Every name and version below was verified against the crates.io API. Repo names that differ from the crate name are shown in parentheses. The full compatibility matrix (layers L0–L3, consumers, features) lives in [KITS.md](KITS.md).

### HTTP & services

| Crate | Version | Purpose |
|---|---|---|
| [`fetch-kit`](https://crates.io/crates/fetch-kit) | 0.1.4 | Resilient HTTP client — retry, circuit breaker, pooling, typed JSON (supersedes `resilient-fetch`) |
| [`webhookkit`](https://crates.io/crates/webhookkit) | 2.2.0 | Webhook signature verification — HMAC-SHA256, timestamps, Stripe/GoCardless parsers |
| [`axum-stack`](https://crates.io/crates/axum-stack) | 0.2.0 | Axum server utilities — shutdown, CORS, request ID, health routes |
| [`shutdown-kit`](https://crates.io/crates/shutdown-kit) (graceful) | 0.3.0 | Graceful shutdown — signal handling, connection draining, RAII guards |
| [`breaker`](https://crates.io/crates/breaker) | 2.0.1 | Async circuit breaker — sliding-window tripping, half-open probes, Tower layer |
| [`throttle-kit`](https://crates.io/crates/throttle-kit) (ratelimit) | 2.0.0 | GCRA rate limiting — in-memory + Redis backends, Tower layer |
| [`config-kit`](https://crates.io/crates/config-kit) | 0.1.1 | Layered typed config — file → env → overrides, secret redaction, hot reload |

### Data & persistence

| Crate | Version | Purpose |
|---|---|---|
| [`outbox-kit`](https://crates.io/crates/outbox-kit) | 0.1.1 | Transactional outbox — durable envelopes, at-least-once dispatch, replay |
| [`idempotency-kit`](https://crates.io/crates/idempotency-kit) | 0.1.0 | Idempotency keys — scoped derivation, TTL claims, response replay |
| [`cas-kit`](https://crates.io/crates/cas-kit) | 0.2.1 | Content-addressed blob store — BLAKE3, packfiles, Zstd, verify-on-read, GC |
| [`cache-pal`](https://crates.io/crates/cache-pal) (cachekit) | 0.4.0 | Unified caching — moka in-memory + Redis, TTL, stale-while-revalidate |
| [`blobkit`](https://crates.io/crates/blobkit) | 0.4.2 | Unified blob storage — Memory / Local / S3 behind one trait |
| [`poolkit`](https://crates.io/crates/poolkit) | 0.1.2 | SQLx connection pooling — health checks, lazy connections |

### Observability

| Crate | Version | Purpose |
|---|---|---|
| [`metrics-kit`](https://crates.io/crates/metrics-kit) | 0.1.0 | Lock-free Prometheus-exposition metrics — cardinality guards, cache-line padding |
| [`telemetry-init`](https://crates.io/crates/telemetry-init) | 0.1.0 | One-call observability bootstrap — tracing + metrics + OTLP, estate defaults |
| [`otelkit`](https://crates.io/crates/otelkit) | 2.0.3 | Tracing/telemetry init — OpenTelemetry, OTLP, Sentry, structured logging |
| [`otel-stack`](https://crates.io/crates/otel-stack) | 0.2.0 | Compatibility facade over otelkit — exporter selection (OTLP/stdout/Prometheus) |
| [`healthkit`](https://crates.io/crates/healthkit) | 1.3.1 | Liveness/readiness/startup probes — dependency checks for k8s/Docker |
| [`percentile-kit`](https://crates.io/crates/percentile-kit) | 0.1.0 | P50/P99/P99.9 latency tracking with committed budgets enforced in CI |

### Resilience & testing

| Crate | Version | Purpose |
|---|---|---|
| [`loop-retry`](https://crates.io/crates/loop-retry) (retry-backoff) | 0.1.1 | Generic async retry — exponential backoff with jitter |
| [`chaos-kit`](https://crates.io/crates/chaos-kit) | 0.1.1 | Deterministic fault injection — latency, errors, partitions, seeded scheduling |
| [`worker-kit`](https://crates.io/crates/worker-kit) | 0.1.0 | Periodic jobs — jittered intervals, graceful drain, leader election |
| [`testkit`](https://github.com/WyattAu/testkit) | repo only | Shared test utilities — test DBs, HTTP servers, auth helpers (not yet published) |

### Auth & data integrity

| Crate | Version | Purpose |
|---|---|---|
| [`tokenkit`](https://crates.io/crates/tokenkit) | 0.4.1 | Type-safe JWT — secret/key rotation, revocation |
| [`salting`](https://crates.io/crates/salting) | 2.0.0 | Argon2id password hashing — OWASP defaults, PHC format |
| [`cryptkit`](https://crates.io/crates/cryptkit) | 0.1.0 | HMAC-SHA256, AES-GCM, constant-time compare, zeroize |
| [`webauthn-kit`](https://crates.io/crates/webauthn-kit) | 0.3.1 | Passkey verification — CTAP2, COSE via ring, sign-count clone detection |
| [`multi-chain-wallet`](https://crates.io/crates/multi-chain-wallet) (hdwallet) | 0.2.1 | BIP32/39/44 HD wallet — BTC/ETH/SOL/TRON addresses |
| [`validkit`](https://crates.io/crates/validkit) | 1.3.1 | Typed newtypes for validated domain primitives — email, URL, cron, tenant |
| [`typed-id-new`](https://crates.io/crates/typed-id-new) (typed-id) | 0.1.0 | Type-safe ID newtypes via derive macro (+ `typed-id-derive`) |
| [`tamper-audit`](https://crates.io/crates/tamper-audit) (auditlog) | 0.2.0 | Tamper-evident audit log — SHA-256 chain, queryable trail |
| [`barbican`](https://crates.io/crates/barbican) | 0.2.1 | Auth middleware for Axum — extractors, role-based guards |
| [`accessctl`](https://crates.io/crates/accessctl) | 0.1.0 | RBAC — Cedar policy engine integration |
| [`oauth-toolkit`](https://crates.io/crates/oauth-toolkit) | 0.2.2 | OAuth/OIDC — PKCE, desktop loopback, mail-provider presets |
| [`scim-kit`](https://crates.io/crates/scim-kit) | 0.1.0 | SCIM 2.0 provisioning — types, filters, patching (RFC 7644) |

### Content & mail

| Crate | Version | Purpose |
|---|---|---|
| [`mailkit`](https://crates.io/crates/mailkit) | 0.3.1 | Email delivery — SMTP, Resend, SES, SendGrid, Postmark; MIME + queue |
| [`mail-sync-kit`](https://crates.io/crates/mail-sync-kit) | 0.1.1 | IMAP (QRESYNC/CONDSTORE/IDLE), JMAP, SMTP submission, outbox queue |
| [`sieve-kit`](https://crates.io/crates/sieve-kit) | 0.2.1 | Mail filter rules — RFC 5228 Sieve semantics |
| [`media-kit`](https://crates.io/crates/media-kit) | 0.2.1 | Image pipeline — sniff, resize, encode, variants, decompression-bomb guard |
| [`docs-pipeline`](https://crates.io/crates/docs-pipeline) | 0.1.4 | Markdown → HTML — tree-sitter highlighting, TOC, sanitize |
| [`simd-tokenizer`](https://crates.io/crates/simd-tokenizer) | 0.1.2 | SWAR-accelerated token estimator — optional exact tiktoken backend |
| [`i18n-kit`](https://crates.io/crates/i18n-kit) | 0.1.3 | Runtime i18n — BCP 47 locales, fallback chains, plural rules |

### Web frontend

| Crate | Version | Purpose |
|---|---|---|
| [`plychart`](https://crates.io/crates/plychart) | 0.2.0 | Canvas2D graphing for Rust/WASM — zero deps (+ `plycore`, `plycompute`, `ply-viz`, `plycharts`) |
| [`leptos-stale-indicator`](https://crates.io/crates/leptos-stale-indicator) | 0.1.0 | LIVE/DATA STALE freshness indicator |
| [`leptos-map-search`](https://crates.io/crates/leptos-map-search) | 0.1.0 | Map typeahead with keyboard navigation |
| [`leptos-sparkline`](https://crates.io/crates/leptos-sparkline) | 0.1.0 | Canvas sparkline mini-charts |
| [`leptos-capital-markers`](https://crates.io/crates/leptos-capital-markers) | 0.1.0 | Weather-aware Leaflet markers |
| [`leptos-crypto-ws`](https://crates.io/crates/leptos-crypto-ws) | 0.1.0 | Reactive Binance WebSocket client |
| [`leptos-leaflet-wyatt`](https://crates.io/crates/leptos-leaflet-wyatt) (leptos-leaflet) | 0.1.1 | Leaflet.js map components for Leptos |
| [`leptos-macros`](https://crates.io/crates/leptos-macros) (leptos-macro) | 0.1.0 | Proc-macros for Leptos components (+ `leptos-derive`) |

### Infra tooling

The **Evergreen** tooling (image registry, shims — [EvergreenImageRegistry](https://github.com/WyattAu/EvergreenImageRegistry), [EvergreenShims](https://github.com/WyattAu/EvergreenShims)) is repo-only infrastructure; no Evergreen crates are published to crates.io.

## Status

- **Production (1.x+):** breaker, throttle-kit, webhookkit, salting, validkit, healthkit, otelkit, error-codes, chronoshift, geo-kit, decimal-money — 11 stable kits; 45 stable crates estate-wide.
- **0.x:** the remaining ~50 kits are API-complete but pre-1.0 (semver: breaking = minor bump until 1.0). Expect iteration.
- **Not published:** testkit (repo-only), Evergreen tooling (repo-only).

## Governance

The [engineering-standards](https://github.com/WyattAu/engineering-standards) repo is the ecosystem's governance doc: the tiered gate matrix (build `--locked`, clippy `-D warnings`, cargo-deny, cargo-audit, llvm-cov thresholds, cargo-semver-checks, loom/miri/wasm gates), panic-free and fuzz policies, ECN/HFT latency discipline (committed criterion baselines, measured P50/P99 in READMEs), cargo-vet enforcement, and release provenance. Every kit repo adopts it via one reusable workflow call.

## Beyond the kits

- [ferro](https://github.com/WyattAu/ferro) — self-hosted file platform (WebDAV, OIDC, S3, full-text search)
- [suture](https://github.com/WyattAu/suture) — patch-based version control with semantic merge
- [vane](https://github.com/WyattAu/vane) — L4/L7 reverse proxy / edge gateway monorepo
- [crawlkit](https://github.com/WyattAu/crawlkit) — web crawler & SEO analysis toolkit
- [WyattsNotes](https://github.com/WyattAu/WyattsNotes) — multi-site educational documentation platform

## License

Individual projects are licensed under MIT, Apache-2.0, or AGPL-3.0 as specified in their repositories.
