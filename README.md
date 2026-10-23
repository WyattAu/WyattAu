# Wyatt Au

Rust kit ecosystem for production services: built to one [gate matrix](https://github.com/WyattAu/engineering-standards): build `--locked`, clippy `-D warnings`, cargo-deny, cargo-audit, llvm-cov thresholds, cargo-semver-checks, loom and miri where applicable, cargo-vet, release provenance. The estate composes as a system: [estate-integration](https://github.com/WyattAu/estate-integration) is the cross-crate proof.

The products and most crates run in production for my own businesses; [estate-integration](https://github.com/WyattAu/estate-integration) is the CI proof that the crates they are built from compose and pass the same gates daily.

The index below is complete. Every public repository appears exactly once under exactly one heading; every entry links to its repository, and each description is that repository's own metadata. Private repositories are listed by name only. Counts per heading are stated so completeness is checkable at a glance.

## Products (6 repositories)

- [ferro](https://github.com/WyattAu/ferro): Self-hosted file storage platform: WebDAV (Class 1/2/3), CalDAV/CardDAV, OIDC auth, S3-compatible backends, full-text search, WASM processing workers. Single binary, docker compose up.
- [clawdius](https://github.com/WyattAu/clawdius): Remote agentic coding with a WASM sandbox and OS-level bubblewrap isolation: agents can read what they need and cannot write to the system.
- [aileron](https://github.com/WyattAu/aileron): Keyboard-driven web environment for developers: native tiling, Lua configuration, zero-extension ad blocking, and a built-in MCP server so LLMs can see the web. Powered by Servo.
- [chisel-doc](https://github.com/WyattAu/chisel-doc): Industrial-hardening fork of PdfCraft: a PDF reader and editor written from scratch in pure Rust, built to a defined gate matrix.
- [aperture-vault](https://github.com/WyattAu/aperture-vault): Photo and video vault: single binary, content-addressed storage, Immich-compatible API, faster ingest with less overhead.
- [CivitForge](https://github.com/WyattAu/CivitForge): Federated software forge built for petabyte scale: Actions running on Kubernetes pods.

## HTTP, API and services (24 repositories)

- [axum-stack](https://github.com/WyattAu/axum-stack) ([crate](https://crates.io/crates/axum-stack)): Axum server utilities: shutdown, CORS, request ID, health routes, middleware stack.
- [axum-server](https://github.com/WyattAu/axum-server): Axum server utilities: shutdown, CORS, request ID, health routes, middleware stack.
- [json-envelope](https://github.com/WyattAu/json-envelope) ([crate](https://crates.io/crates/json-envelope)): Standard API response envelope for Rust services.
- [http-error](https://github.com/WyattAu/http-error): Derive macro for mapping error enums to HTTP status codes.
- [app-error](https://github.com/WyattAu/app-error): Common application error variants with recovery classification.
- [errcode](https://github.com/WyattAu/errcode): Structured error handling for Rust: derive macros for error codes, HTTP status mapping, and RFC 7807 Problem Details.
- [api-types](https://github.com/WyattAu/api-types) ([crate](https://crates.io/crates/api-types)): Standard API response types for Rust: Success, Error, and List wrappers with OpenAPI derives and RFC 7807 Problem Details.
- [validkit](https://github.com/WyattAu/validkit) ([crate](https://crates.io/crates/validkit)): Unified input validation: typed newtypes for email, URL, phone, cron, tenant, locale with proptest.
- [paginate](https://github.com/WyattAu/paginate): Pagination types for Rust APIs: offset-based and cursor-based pagination with OpenAPI support.
- [envstack](https://github.com/WyattAu/envstack) ([crate](https://crates.io/crates/envstack)): Layered configuration for Rust: environment variables, TOML files, and CLI args with type-safe extraction and validation.
- [config-kit](https://github.com/WyattAu/config-kit) ([crate](https://crates.io/crates/config-kit)): Layered typed configuration for Rust: file → env → overrides with unknown-field denial, secret redaction, and hot reload.
- [fetch-kit](https://github.com/WyattAu/fetch-kit) ([crate](https://crates.io/crates/fetch-kit)): Resilient HTTP client for Rust: retry, circuit breaker, connection pooling, and typed JSON helpers built on reqwest, with a native middleware stack that mirrors the reqwest-middleware shape.
- [ratelimit](https://github.com/WyattAu/ratelimit): Rate limiting for Rust: GCRA (Generic Cell Rate Algorithm) with pluggable.
- [idempotency-kit](https://github.com/WyattAu/idempotency-kit) ([crate](https://crates.io/crates/idempotency-kit)): Idempotency keys for Rust: scoped BLAKE3 key derivation, TTL claims with response replay, pluggable memory/redis stores.
- [outbox-kit](https://github.com/WyattAu/outbox-kit) ([crate](https://crates.io/crates/outbox-kit)): Transactional outbox for Rust: durable event envelopes, at-least-once dispatch with breaker-aware backoff, replay after restart.
- [webhookkit](https://github.com/WyattAu/webhookkit) ([crate](https://crates.io/crates/webhookkit)): Verify webhook signatures in Rust: with a nostd-compatible core.
- [ws-kit](https://github.com/WyattAu/ws-kit) ([crate](https://crates.io/crates/ws-kit)): Generic authenticated typed WebSocket: BroadcastHub, RoomManager, heartbeat.
- [uds-kit](https://github.com/WyattAu/uds-kit) ([crate](https://crates.io/crates/uds-kit)): Timeout-aware Unix domain socket connect/read/write helpers for Tokio: transport-only, protocol-agnostic.
- [eventbus](https://github.com/WyattAu/eventbus): Async event bus for Rust: typed pub/sub with optional persistence, replay, and wildcard subscriptions.
- [worker-kit](https://github.com/WyattAu/worker-kit) ([crate](https://crates.io/crates/worker-kit)): Periodic job scheduling for Rust services: jittered intervals, graceful drain, breaker-aware failure budgets, optional leader election.
- [healthkit](https://github.com/WyattAu/healthkit) ([crate](https://crates.io/crates/healthkit)): Health check endpoints for Rust: liveness, readiness, and startup probes with dependency checking for Kubernetes and Docker.
- [geo-kit](https://github.com/WyattAu/geo-kit) ([crate](https://crates.io/crates/geo-kit)): Typed newtypes for validated geo primitives: postcodes, country codes, coordinates, addresses.
- Private: `deploy-webhook-rs`, `eventbusd`.

## Auth, identity and policy (11 repositories)

- [tokenkit](https://github.com/WyattAu/tokenkit) ([crate](https://crates.io/crates/tokenkit)): Type-safe JWT encode/decode for Rust with configurable validation, secret rotation, key rotation, and revocation support.
- [oauth-toolkit](https://github.com/WyattAu/oauth-toolkit) ([crate](https://crates.io/crates/oauth-toolkit)): Shared OAuth2/OIDC primitives: crypto, PKCE, scopes, CSRF, social login, OIDC, JWKS validation.
- [webauthn-kit](https://github.com/WyattAu/webauthn-kit) ([crate](https://crates.io/crates/webauthn-kit)): Standalone WebAuthn/FIDO2 passkey verification kit for Rust: CTAP2 parsing, COSE ES256/RS256 via ring, replay/freshness protection, sign-count clone detection. No storage, no framework.
- [scim-kit](https://github.com/WyattAu/scim-kit) ([crate](https://crates.io/crates/scim-kit)): Self-contained SCIM 2.0 (RFC 7644) provisioning types, stores, and optional axum router.
- [accessctl](https://github.com/WyattAu/accessctl) ([crate](https://crates.io/crates/accessctl)): Role-based access control for Rust: Cedar policy engine integration with typed roles and Axum middleware.
- [auditlog](https://github.com/WyattAu/auditlog): Tamper-evident audit logging for Rust: SHA-256 chain, immutable entries, and queryable audit trail.
- [policy-kit](https://github.com/WyattAu/policy-kit) ([crate](https://crates.io/crates/policy-kit)): Fail-closed Rego policy evaluation for Rust: bundle loading, dialect auto-detect, typed verdicts.
- [salting](https://github.com/WyattAu/salting) ([crate](https://crates.io/crates/salting)): Opinionated Argon2id password hashing for Rust with OWASP-recommended defaults.
- [cryptkit](https://github.com/WyattAu/cryptkit) ([crate](https://crates.io/crates/cryptkit)): Cryptographic primitives for Rust: HMAC-SHA256, AES-GCM, constant-time comparison, and secure random with zeroize.
- [typed-id](https://github.com/WyattAu/typed-id): Type-safe ID newtypes via derive macro.
- Private: `authbox`.

## Data, storage and retrieval (14 repositories)

- [blobkit](https://github.com/WyattAu/blobkit) ([crate](https://crates.io/crates/blobkit)): Typed object storage: BlobStore trait with S3/Local/Memory backends, audit, presigned URLs.
- [cas-kit](https://github.com/WyattAu/cas-kit) ([crate](https://crates.io/crates/cas-kit)): Content-addressed blob store: BLAKE3 addressing, 2-hex bucketing, optional Zstd, packfiles, verify-on-read. Extracted from Suture.
- [delta-kit](https://github.com/WyattAu/delta-kit) ([crate](https://crates.io/crates/delta-kit)): Binary delta codec: Rabin rolling-hash copy/insert opcodes, prefix/suffix fast-path, binary-safe. Extracted from Suture.
- [crawlkit](https://github.com/WyattAu/crawlkit): Site crawl kit.
- [crawlkit-testbed](https://github.com/WyattAu/crawlkit-testbed): Ground-truth conformance testbed for crawlkit: a site with planted, documented defects, and a scorer that measures precision and recall against them.
- [tantivy-ext](https://github.com/WyattAu/tantivy-ext): Full-text search for Rust: Tantivy wrapper with autocomplete, highlighting, and typed queries.
- [crdts-kit](https://github.com/WyattAu/crdts-kit) ([crate](https://crates.io/crates/crdts-kit)): CRDT toolkit: RGA replicated string with tombstones, participant presence, serde + wasm support.
- [shared-state](https://github.com/WyattAu/shared-state) ([crate](https://crates.io/crates/shared-state)): Concurrent state utilities: readiness gates, TTL caches, shared counters, type aliases.
- [poolkit](https://github.com/WyattAu/poolkit) ([crate](https://crates.io/crates/poolkit)): Database connection pooling for Rust: SQLx wrapper with health checks, lazy connections, test containers, and metrics.
- [slab-pool](https://github.com/WyattAu/slab-pool) ([crate](https://crates.io/crates/slab-pool)): Lock-free slab object pool: tagged-pointer ABA protection, RAII guards, loom+miri verified.
- [shm-rings](https://github.com/WyattAu/shm-rings) ([crate](https://crates.io/crates/shm-rings)): Lock-free shared-memory SPMC ring: power-of-two masked, cache-line aligned, zero SeqCst, loom+miri verified.
- [cachekit](https://github.com/WyattAu/cachekit): Unified caching for Rust: in-memory (moka) and Redis backends with TTL, stale-while-revalidate, and eviction listeners.
- [crdt-demo](https://github.com/WyattAu/crdt-demo): Live multi-user CRDT demo: crdts-kit + ws-kit, single binary, open two tabs and watch edits converge.
- [signalkit](https://github.com/WyattAu/signalkit) ([crate](https://crates.io/crates/signalkit)): Snapshot, store, and score any counter: subjects/observations engine + engagement-integrity signals.

## Observability, time and hardware (10 repositories)

- [metrics-kit](https://github.com/WyattAu/metrics-kit) ([crate](https://crates.io/crates/metrics-kit)): Lock-free Prometheus-exposition metrics kit: counters, gauges, histograms with cache-line padding, cardinality guards, VictoriaMetrics/Grafana-compatible output.
- [telemetry-init](https://github.com/WyattAu/telemetry-init) ([crate](https://crates.io/crates/telemetry-init)): One-call observability bootstrap for Rust services: tracing + metrics + OTLP wired with estate defaults.
- [otelkit](https://github.com/WyattAu/otelkit) ([crate](https://crates.io/crates/otelkit)): Tracing and telemetry initialization for Rust: OpenTelemetry, OTLP export, Sentry integration, and structured logging.
- [otel-stack](https://github.com/WyattAu/otel-stack) ([crate](https://crates.io/crates/otel-stack)): OpenTelemetry integration for Rust: unified tracing, metrics, and OTLP export with version-pinned dependencies.
- [observability-assets](https://github.com/WyattAu/observability-assets): Central VictoriaMetrics + Grafana assets for every shipping WyattAu build: scrape configs, vmalert rules, dashboards.
- [clock-kit](https://github.com/WyattAu/clock-kit) ([crate](https://crates.io/crates/clock-kit)): Time-source abstraction for Rust: monotonic/wall separation, TSC calibration, PTP quality detection, deterministic test clock.
- [clock](https://github.com/WyattAu/clock): Trait-based time abstraction with mock clock for testing.
- [percentile-kit](https://github.com/WyattAu/percentile-kit) ([crate](https://crates.io/crates/percentile-kit)): Latency percentile tracking and budget gates for Rust: P50/P99 from criterion output, committed budgets, CI regression enforcement.
- [hw-kit](https://github.com/WyattAu/hw-kit) ([crate](https://crates.io/crates/hw-kit)): Hardware topology and control for Rust: CPU/NUMA discovery, core pinning, NUMA binding, hugepage reservation (Linux).
- [uring-kit](https://github.com/WyattAu/uring-kit) ([crate](https://crates.io/crates/uring-kit)): Reusable io_uring socket substrate: ring lifecycle, registered buffers, zero-copy socket ops (Linux).

## Resilience, concurrency and testing (14 repositories)

- [retry-backoff](https://github.com/WyattAu/retry-backoff): Generic async retry with exponential backoff and jitter.
- [chaos-kit](https://github.com/WyattAu/chaos-kit) ([crate](https://crates.io/crates/chaos-kit)): Deterministic fault injection for Rust tests: latency, errors, partitions, and resource starvation with seeded scheduling.
- [testkit](https://github.com/WyattAu/testkit): Shared test utilities for Rust: test databases, HTTP servers, auth helpers, and assertions.
- [kit-conformance](https://github.com/WyattAu/kit-conformance): Shared conformance harness for the WyattAu Rust kit ecosystem.
- [graceful](https://github.com/WyattAu/graceful): Graceful shutdown for Rust services: signal handling, connection draining, and RAII cleanup guards.
- [breaker](https://github.com/WyattAu/breaker) ([crate](https://crates.io/crates/breaker)): Async circuit breaker for Rust: sliding-window failure-rate tripping,.
- [pid-manager](https://github.com/WyattAu/pid-manager) ([crate](https://crates.io/crates/pid-manager)): PID file management with RAII cleanup and process liveness checks.
- [mcp-doctor](https://github.com/WyattAu/mcp-doctor): Audit an OpenCode MCP fleet: config, backends, credential entitlement, and real MCP handshakes.
- [flag-kit](https://github.com/WyattAu/flag-kit) ([crate](https://crates.io/crates/flag-kit)): Feature flags: FlagSet rollout, targeting, audit, OTel.
- [flaglab](https://github.com/WyattAu/flaglab): Audit feature flags across repos and emit reviewable removal candidates (Piranha's missing orchestrator).
- [sieve-kit](https://github.com/WyattAu/sieve-kit) ([crate](https://crates.io/crates/sieve-kit)): Rule-based mail filtering engine: conditions, actions, bounded regex evaluation.
- [actor-kit](https://github.com/WyattAu/actor-kit) ([crate](https://crates.io/crates/actor-kit)): Work-stealing actor runtime: OTP supervision trees, crossbeam work-stealing, bounded backpressure.
- [tui-actions](https://github.com/WyattAu/tui-actions) ([crate](https://crates.io/crates/tui-actions)): Terminal action/keymap layer for Rust: chord parsing (ctrl+s, leader sequences), modal context stacks, conflict and unbound-key detection, help rows derived from the live keymap. No terminal dependency.
- Private: `flagsd`.

## Money, ledger and billing (13 repositories)

- [money](https://github.com/WyattAu/money): Money types for Rust: CurrencyAmount with Decimal precision, multi-currency support, FX conversion, and formatting.
- [ledger-kit](https://github.com/WyattAu/ledger-kit) ([crate](https://crates.io/crates/ledger-kit)): Double-entry ledger for Rust: decimal-money postings, outbox-backed journal, idempotent posting, tamper-evident history.
- [double-entry](https://github.com/WyattAu/double-entry) ([crate](https://crates.io/crates/double-entry)): Immutable double-entry accounting core: append-only journals, balanced posting, period close, reversal by counter-entry.
- [invoice-kit](https://github.com/WyattAu/invoice-kit) ([crate](https://crates.io/crates/invoice-kit)): Accounts-receivable invoicing for an SME ledger: three orthogonal document states, Peppol/EN 16931 arithmetic, per-jurisdiction rounding policy.
- [ap-kit](https://github.com/WyattAu/ap-kit) ([crate](https://crates.io/crates/ap-kit)): Accounts payable: supplier bills, input VAT recoverability, and the three-way split between payable, deductible tax and expense.
- [vat-rules](https://github.com/WyattAu/vat-rules) ([crate](https://crates.io/crates/vat-rules)): Tax categories, exemption codes, document types and rounding regimes shared by the AR and AP sides of an accounting ledger.
- [billing-kit](https://github.com/WyattAu/billing-kit) ([crate](https://crates.io/crates/billing-kit)): Billing primitives: Price with tax/discount, re-exporting decimal-money CurrencyAmount.
- [book-kit](https://github.com/WyattAu/book-kit) ([crate](https://crates.io/crates/book-kit)): Lock-free limit order book: price-time priority, single-writer/multi-reader snapshots, zero-allocation hot path, loom-verified.
- [hdwallet](https://github.com/WyattAu/hdwallet): HD wallet for Rust: BIP32/39/44 derivation with multi-chain address generation (BTC, ETH, SOL, TRON).
- [recon-kit](https://github.com/WyattAu/recon-kit) ([crate](https://crates.io/crates/recon-kit)): Bank statement types and a matching engine for reconciling statements against a ledger: no format parsing, no floats, no silent auto-matching.
- [report-kit](https://github.com/WyattAu/report-kit) ([crate](https://crates.io/crates/report-kit)): Trial balance and aging reports over a double-entry ledger: per-currency by construction, with the accounting equation as a runtime check.
- [statement-ofx](https://github.com/WyattAu/statement-ofx): OFX bank statement adapter producing recon-kit Statements: sign-normalising, float-free amounts, zero dependencies beyond the model.
- [vat-return](https://github.com/WyattAu/vat-return): VAT return boxes from AR invoices and AP bills: deductible-only input tax, per-currency, tax-point filtered.

## Formats, parsers and conformance (22 repositories)

- [a2l-parse](https://github.com/WyattAu/a2l-parse) ([crate](https://crates.io/crates/a2l-parse)): ASAP2/A2L ECU description parser: PROJECT/MODULE/CHARACTERISTIC/MEASUREMENT/RECORD_LAYOUT/COMPU_METHOD, calibration data model.
- [cal-model](https://github.com/WyattAu/cal-model) ([crate](https://crates.io/crates/cal-model)): A2L calibration data model and session layer: characteristic binding, COMPU_METHOD conversions, limit validation, curve calibration.
- [dbc-parse](https://github.com/WyattAu/dbc-parse) ([crate](https://crates.io/crates/dbc-parse)): DBC file parser: CAN message definitions, signal layout (bit-offset/length/endianness/scaling), value tables, extended multiplexing.
- [can-core](https://github.com/WyattAu/can-core) ([crate](https://crates.io/crates/can-core)): CAN 2.0 and CAN FD frame codec: identifier parsing, DLC handling, bit-timing calculation.
- [xcp-core](https://github.com/WyattAu/xcp-core) ([crate](https://crates.io/crates/xcp-core)): XCP on CAN: Universal Measurement and Calibration Protocol: commands, responses, DAQ lists.
- [id3-core](https://github.com/WyattAu/id3-core) ([crate](https://crates.io/crates/id3-core)): ID3v1/ID3v2 audio tag reader and writer for Rust: CHAP/CTOC chapters, APIC art, no_std.
- [mp4-core](https://github.com/WyattAu/mp4-core) ([crate](https://crates.io/crates/mp4-core)): ISO-BMFF (MP4/M4A/M4B) box reader and writer for Rust: ilst metadata, chpl chapters, no_std.
- [cuesheet-core](https://github.com/WyattAu/cuesheet-core): CDRWIN cue sheet reader and writer: tracks, indices, MM:SS:FF at 75 fps, CD-TEXT, no_std.
- [font-parse](https://github.com/WyattAu/font-parse) ([crate](https://crates.io/crates/font-parse)): SFNT/OTF/TrueType/WOFF/WOFF2 binary font parser: offset tables, character maps, glyph outlines, variable fonts.
- [font-model](https://github.com/WyattAu/font-model) ([crate](https://crates.io/crates/font-model)): Typed owned editable font model: glyph outlines, cmap formats 4 and 12, metrics, validation, subsetting.
- [font-shape](https://github.com/WyattAu/font-shape) ([crate](https://crates.io/crates/font-shape)): Glyph rasterization and text measurement: scanline fill, stroke expansion,.
- [font-conformance](https://github.com/WyattAu/font-conformance): Independent differential oracle for the estate text stack: font-parse vs fontations, font-shape vs the rival rasterizers, Err-not-panic over a hostile corpus.
- [sheet-core](https://github.com/WyattAu/sheet-core) ([crate](https://crates.io/crates/sheet-core)): Spreadsheet data model: sparse cells, dependency DAG, topological order, formula reference extraction.
- [sheet-engine](https://github.com/WyattAu/sheet-engine) ([crate](https://crates.io/crates/sheet-engine)): Spreadsheet calculation engine: dependency-driven incremental recalculation, Excel-compatible semantics, volatile function tracking.
- [sheet-xlsx](https://github.com/WyattAu/sheet-xlsx) ([crate](https://crates.io/crates/sheet-xlsx)): XLSX codec: workbook, worksheets, shared strings, styles, calc chain.
- [formula-lang](https://github.com/WyattAu/formula-lang) ([crate](https://crates.io/crates/formula-lang)): Spreadsheet formula language: tokenizer, Pratt parser, AST, evaluator core. Excel-compatible function semantics.
- [audiobook-core](https://github.com/WyattAu/audiobook-core) ([crate](https://crates.io/crates/audiobook-core)): Audiobook domain model for Rust: format-independent titles, parts and chapters from MP3 and M4B.
- [audiobook-conformance](https://github.com/WyattAu/audiobook-conformance): Conformance harness for the WyattAu audiobook stack: cross-checks mp4-core/id3-core/audiobook-core against ffmpeg and ffprobe.
- [audiobook-shelf](https://github.com/WyattAu/audiobook-shelf): Audiobook-first library manager: decides which files form one book, orders them by disc then track, parses the folder-name conventions a library is actually named with, and reports what is inconsistent.
- [ldir](https://github.com/WyattAu/ldir): LDIR (Low-level document intermediate representation), a universal document that compiles from an IR lang.
- [wire-kit](https://github.com/WyattAu/wire-kit) ([crate](https://crates.io/crates/wire-kit)): Zero-copy binary wire codecs: SBE block encoding and FIX 4.4 tag=value, bounds-checked, allocation-free decode, SIMD-assisted scanning.
- [sensors_rpi_pico](https://github.com/WyattAu/sensors_rpi_pico).

## Audio, DSP and media (3 repositories)

- [dsp-core](https://github.com/WyattAu/dsp-core) ([crate](https://crates.io/crates/dsp-core)): Foundational audio DSP primitives: biquad filters, FFT, convolution, windowing, dynamics, oscillators: allocation-free process paths.
- [dsp-spectral](https://github.com/WyattAu/dsp-spectral) ([crate](https://crates.io/crates/dsp-spectral)): Spectral audio analysis and restoration: STFT/ISTFT, mel/MFCC features, spectral gating, HPSS source separation.
- [media-kit](https://github.com/WyattAu/media-kit) ([crate](https://crates.io/crates/media-kit)): Full image pipeline: sniff, meta, resize, encode, composite, variants with bomb-guard and async support.

## Web frontends, UI and Leptos (21 repositories)

- [plychart](https://github.com/WyattAu/plychart) ([crate](https://crates.io/crates/plychart)): High-performance WASM charting library for Rust.
- [leptos-stale-indicator](https://github.com/WyattAu/leptos-stale-indicator) ([crate](https://crates.io/crates/leptos-stale-indicator)): Data freshness indicator for Leptos: shows LIVE/DATA STALE status based on fetch timestamps.
- [leptos-map-search](https://github.com/WyattAu/leptos-map-search) ([crate](https://crates.io/crates/leptos-map-search)): Map search/typeahead component for Leptos: filter and select countries with keyboard navigation.
- [leptos-sparkline](https://github.com/WyattAu/leptos-sparkline) ([crate](https://crates.io/crates/leptos-sparkline)): Leptos component (see repo).
- [leptos-capital-markers](https://github.com/WyattAu/leptos-capital-markers) ([crate](https://crates.io/crates/leptos-capital-markers)): Capital city markers for leptos-leaflet: renders weather-aware markers on a Leaflet map.
- [leptos-crypto-ws](https://github.com/WyattAu/leptos-crypto-ws) ([crate](https://crates.io/crates/leptos-crypto-ws)): Leptos component (see repo).
- [leptos-leaflet](https://github.com/WyattAu/leptos-leaflet): Leptos components for [Leaflet.js](https://leafletjs.com/) maps. Provides a declarative, reactive API for building interactive maps in Rust/WASM with Leptos.
- [leptos-macro](https://github.com/WyattAu/leptos-macro): Procedural macros for Leptos components: boilerplate reduction for lib.rs, feature flags, and prop defaults.
- [theme-kit](https://github.com/WyattAu/theme-kit) ([crate](https://crates.io/crates/theme-kit)): Typed design-token contract for the estate: DTCG 2025.10 in/out, semantic role vocabulary, build-failing WCAG contrast gate, derived CVD/high-contrast/monochrome variants, data-only emitters (CSS, VS Code, ANSI-16).
- [theme-egui](https://github.com/WyattAu/theme-egui) ([crate](https://crates.io/crates/theme-egui)): egui/epaint lowering for theme-kit: the adapter that makes the estate token contract real in chisel-doc, chisel-platform's future front-end, and any egui app. One file of placement, zero colour maths.
- [shroom-theme](https://github.com/WyattAu/shroom-theme): VS Code colour theme with 7 variants: dark, light, high-contrast, monochrome, and 3 dichromacy adaptations (deuteranopia, protanopia, tritanopia). 1049 tokens, alpha-composited WCAG 2.1 AA, APCA lightness separation, CVD simulation in linear RGB.
- [a11y-kit](https://github.com/WyattAu/a11y-kit) ([crate](https://crates.io/crates/a11y-kit)): Accessibility semantics layer for the estate: platform-free semantic node model (role, name, states, relations), tree audit as a CI gate, AccessKit conversion behind a feature. The layer nobody funds, owned.
- [color-kit](https://github.com/WyattAu/color-kit) ([crate](https://crates.io/crates/color-kit)): Colour science leaf for Rust: linear-sRGB core, Oklab/OkLCH, WCAG 2.1 AA contrast, perceptual lightness contrast, dichromat simulation, deterministic quantisation. no_std.
- [tauri-preset](https://github.com/WyattAu/tauri-preset): Shared Tauri v2 configuration presets for window, bundle, and security settings.
- [i18n-kit](https://github.com/WyattAu/i18n-kit): Runtime i18n for Rust: BCP 47 locales, flat catalogs with dot-notation keys, fallback chains, interpolation, simple pluralization.
- [polyfont](https://github.com/WyattAu/polyfont): A multi font plugin for vscode and other editors.
- [tao](https://github.com/WyattAu/tao).
- [tauri](https://github.com/WyattAu/tauri).
- [wry](https://github.com/WyattAu/wry).
- [input-kit](https://github.com/WyattAu/input-kit) ([crate](https://crates.io/crates/input-kit)): Toolkit-neutral text-composition semantics for Rust: IME preedit state machine, grapheme-cluster caret mapping, and dead-key composition. Pure logic, no windowing or widget dependency.
- [ui-text-edit](https://github.com/WyattAu/ui-text-edit) ([crate](https://crates.io/crates/ui-text-edit)): Text-field semantics for Rust GUIs: a buffer-agnostic TextBuffer, a grapheme-correct caret/selection/edit model, and an a11y-state bridge. Composes input-kit for IME. Not a code editor.

## Sites and documentation (19 repositories)

- [pediment](https://github.com/WyattAu/pediment): Shared design tokens, components, hooks, and utilities for Astro+SolidJS+Starlight+Cloudflare projects.
- [starlight-sites](https://github.com/WyattAu/starlight-sites): Wyatt's Notes new site with starlight.
- [starlight-kit](https://github.com/WyattAu/starlight-kit): Starlight plugin development kit: shared configuration, plugin factory, and boilerplate for Astro/Starlight plugins.
- [starlight-progress](https://github.com/WyattAu/starlight-progress): Starlight plugin providing a reading progress bar and collapsible TOC sidebar.
- [starlight-katex](https://github.com/WyattAu/starlight-katex): Write $E = mc^2$ in any page. Get server-rendered KaTeX, automatic dark mode, and zero client-side JavaScript.
- [starlight-content-guard](https://github.com/WyattAu/starlight-content-guard): Starlight plugin and CLI for comprehensive content validation at scale.
- [starlight-multi-site](https://github.com/WyattAu/starlight-multi-site): CLI tool and shared config factory for managing multiple Starlight documentation sites from a single monorepo.
- [starlight-interactive-islands](https://github.com/WyattAu/starlight-interactive-islands): Dont know why theres no standardized plugin.
- [starlight-cross-domain-sync](https://github.com/WyattAu/starlight-cross-domain-sync): Starlight plugin to synchronize the dark/light theme preference across subdomains via cookies and BroadcastChannel.
- [starlight-dse-test](https://github.com/WyattAu/starlight-dse-test): DSE study and test platform built with Astro Starlight.
- [docs-core](https://github.com/WyattAu/docs-core) ([crate](https://crates.io/crates/docs-core)): Rust docs pipeline core: CommonMark+GFM to static HTML with astro-island-compatible island emission, so a Rust shell hydrates the estate's existing SolidJS bundles. Consolidates Tachyon + docs-pipeline + the starlight-* stack (ADR-0004 §2.5).
- [docs-pipeline](https://github.com/WyattAu/docs-pipeline) ([crate](https://crates.io/crates/docs-pipeline)): Markdown rendering and tree-sitter syntax highlighting pipeline for documentation sites.
- [Tachyon](https://github.com/WyattAu/Tachyon): JIT documentation server with internal developer portal, the build step latency inherently in traditional SSG can be eliminated by reactive file watching on the host file system, while still able to compile as SSG if needed.
- [hydrated-personal-site](https://github.com/WyattAu/hydrated-personal-site): High-performance personal site and intelligence dashboard. Astro 5 + SolidJS 1.9 + Tailwind CSS 4 + Rust/WASM widgets, deployed to Cloudflare Pages and Workers.
- [WyattsNotes](https://github.com/WyattAu/WyattsNotes): Deprecated, new repo at https://github.com/WyattAu/starlight-sites. A list of personal notes modified for public use, require a high degree of contributions to polish.
- [forgeyard](https://github.com/WyattAu/forgeyard): Standardized repository templates with CI/CD for Rust, Astro+SolidJS, Starlight, and TypeScript projects.
- [cf-worker-utils](https://github.com/WyattAu/cf-worker-utils): Cloudflare Workers utilities: SWR cache, circuit breaker, rate limiter, security headers, and structured logging.
- [estate-site](https://github.com/WyattAu/estate-site): The WyattAu estate index: built by the estate's own docs engine.
- [pele-rehype](https://github.com/WyattAu/pele-rehype): Rehype plugin: render mermaid fences with Pele in Astro/Starlight (fast, CSS-variable themable SVG).

## AI, agents and search (10 repositories)

- [model-router](https://github.com/WyattAu/model-router) ([crate](https://crates.io/crates/model-router)): Cost-aware LLM routing core: per-model pricing, USD budget tracking, task-class routing with fallback chains.
- [simd-tokenizer](https://github.com/WyattAu/simd-tokenizer) ([crate](https://crates.io/crates/simd-tokenizer)): Safe SWAR-accelerated whitespace token estimator with optional exact tiktoken backend.
- [latent-oracle](https://github.com/WyattAu/latent-oracle): Searchless neural chess research engine: strictly 0-ply policy with symbolic invariants.
- [latent-oracle-data](https://github.com/WyattAu/latent-oracle-data): Data pipeline for latent-oracle: Lichess PGN to shards to Stockfish labels.
- [ironclaw](https://github.com/WyattAu/ironclaw): Fork of nearai/ironclaw: WyattAu staging with validkit adoption and clippy fixes.
- [morph](https://github.com/WyattAu/morph): The specification for a agentic programming language.
- [contact-miner](https://github.com/WyattAu/contact-miner) ([crate](https://crates.io/crates/contact-miner)): Multi-engine web contact discovery: emails, phones, WhatsApp/Telegram/Signal handles from public pages.
- [trendkit](https://github.com/WyattAu/trendkit) ([crate](https://crates.io/crates/trendkit)): Dev-trend crawler in Rust: GitHub/HN/crates.io snapshots, velocity scoring, personal relevance, Telegram digest.
- [comfyui-kit](https://github.com/WyattAu/comfyui-kit) ([crate](https://crates.io/crates/comfyui-kit)): Typed Rust client for the ComfyUI HTTP API: queue workflows, track history, fetch generations.
- [skillkit](https://github.com/WyattAu/skillkit) ([crate](https://crates.io/crates/skillkit)): Tooling for the agent-skill economy: lint, package, verify, and audit SKILL.md skills.

## Mail and messaging (5 repositories)

- [mailkit](https://github.com/WyattAu/mailkit) ([crate](https://crates.io/crates/mailkit)): Email delivery for Rust: SMTP, Resend, AWS SES, SendGrid, and Postmark.
- [mail-sync-kit](https://github.com/WyattAu/mail-sync-kit) ([crate](https://crates.io/crates/mail-sync-kit)): Protocol-agnostic mail sync engines: IMAP (QRESYNC/CONDSTORE/IDLE), JMAP, SMTP submission (XOAUTH2), outbox queue.
- [barbican](https://github.com/WyattAu/barbican) ([crate](https://crates.io/crates/barbican)): Authentication and authorization middleware for Axum: extractors, role-based guards, and public path bypass.
- [ws-barbican](https://github.com/WyattAu/ws-barbican) ([crate](https://crates.io/crates/ws-barbican)): Barbican wrapper for ws-kit: JWT auth via header/query/cookie.
- [kestrel](https://github.com/WyattAu/kestrel): tui+gui email client in Rust.

## Applications and products (9 repositories)

- [suture](https://github.com/WyattAu/suture): Core logic of suture.
- [chisel-platform](https://github.com/WyattAu/chisel-platform): Platform side of Chisel Docs: identity, assets, and the tamper-evident document audit trail: composed from the WyattAu kit estate.
- [vane](https://github.com/WyattAu/vane): L4/L7 reverse proxy,edge gateway, micro sidecar monorepo.
- [estate-integration](https://github.com/WyattAu/estate-integration): Cross-crate dogfooding suite proving the WyattAu crate estate composes.
- [homebrew-clawdius](https://github.com/WyattAu/homebrew-clawdius): Homebrew tap for Clawdius.
- [homebrew-suture-merge-driver](https://github.com/WyattAu/homebrew-suture-merge-driver): Homebrew tap for [Suture](https://github.com/WyattAu/suture): a universal semantic merge driver that resolves Git merge conflicts automatically for 17+ file formats.
- [continuwuity](https://github.com/WyattAu/continuwuity).
- [aether-core](https://github.com/WyattAu/aether-core): Aether-core is the open core logic for aether and the exact logic for Aether community edition.
- [warploom](https://github.com/WyattAu/warploom): A data-oriented C++ engine with deterministic simulation, Vulkan rendering, an ECS, and a time-warp editor.

## Infrastructure and hosting (12 repositories)

- [traefik-setup](https://github.com/WyattAu/traefik-setup): Docker-compose repository for setting up traefik.
- [traefik-stack](https://github.com/WyattAu/traefik-stack): Traefik setup with a few stacks. Open Portainer.io and copy the docker-compose.yml script with the .env.
- [EvergreenImageRegistry](https://github.com/WyattAu/EvergreenImageRegistry): LTS images by community efforts.
- [EvergreenShims](https://github.com/WyattAu/EvergreenShims): Shims for building images with, especially those ones without a healthcheck.
- [RunnerImages](https://github.com/WyattAu/RunnerImages): A list of base images usable for CI.
- [forgejo-k8s-runner](https://github.com/WyattAu/forgejo-k8s-runner): Forgejo Actions runner setup for Kubernetes.
- [gitea-setup](https://github.com/WyattAu/gitea-setup): Docker compose setup for self-hosted Gitea.
- [hosting-api](https://github.com/WyattAu/hosting-api): Control-plane API for the WyattAu hosting platform: tenant state, backup triggers, metrics. Dogfoods telemetry-init, metrics-kit, testkit.
- [hosting-dashboard](https://github.com/WyattAu/hosting-dashboard): Customer dashboard for the WyattAu hosting platform: tenants, backup jobs, health. Astro + SolidJS, dogfoods pediment.
- [SimpleInfrastructureStack](https://github.com/WyattAu/SimpleInfrastructureStack): Simple truenas infrasturcture stack with terraform.
- [cachyos_sys_dotfiles](https://github.com/WyattAu/cachyos_sys_dotfiles): Personal infrastructure-as-code for a multi-device Arch/CachyOS/WSL environment. Managed by [chezmoi](https://www.chezmoi.io/) (user-space configs) and [Ansible](https://www.ansible.com/) (system provisioning).
- Private: `windows-dotfiles`.

## Templates and estate governance (26 repositories)

- [OmniRust-template](https://github.com/WyattAu/OmniRust-template): Maximalist Rust monorepo template: cargo workspace, estate tier-a gates (clippy pedantic/loom/miri/llvm-cov/deny/vet), nix + dual devcontainers.
- [OmniTS-template](https://github.com/WyattAu/OmniTS-template): Maximalist TypeScript monorepo template: bun workspaces, Astro shell + SolidJS islands, biome, vitest + playwright, changesets.
- [OmniGo-template](https://github.com/WyattAu/OmniGo-template): Maximalist Go monorepo template: go.work anchor, golangci-lint v2, govulncheck, native fuzzing, goreleaser with homebrew tap.
- [OmniPython-template](https://github.com/WyattAu/OmniPython-template): A starting point for python projects.
- [OmniHaskell-template](https://github.com/WyattAu/OmniHaskell-template): Maximalist Haskell monorepo template: cabal multi-package, nix-owned GHC 9.8 (9.6/9.10 legs), HLS, fourmolu + hlint + weeder, tasty + hedgehog.
- [OmniCPP-template](https://github.com/WyattAu/OmniCPP-template): A starter template for CMake projects.
- [OmniCPP-docker](https://github.com/WyattAu/OmniCPP-docker): Docker containing CPP and CMake tooling.
- [OmniEmbedded-template](https://github.com/WyattAu/OmniEmbedded-template): Maximalist embedded C/C++ template: RP2040/RP2350, pinned pico-sdk, CMake presets, PIO scaffold, flash/RAM budget gates, HIL smoke.
- [OmniInfra-template](https://github.com/WyattAu/OmniInfra-template): Maximalist OpenTofu infrastructure template: tflint, fail-closed conftest/OPA policy gates, terraform-docs, sops, human-gated apply.
- [OmniDotfiles-template](https://github.com/WyattAu/OmniDotfiles-template): Maximalist dotfiles template: chezmoi-first, shellcheck + shfmt + bats, ubuntu+arch container CI for OS parity.
- [OmniDocs-template](https://github.com/WyattAu/OmniDocs-template): Maximalist Starlight documentation site template: Astro + Starlight, bun, biome, Pages deploy on every merge.
- [OmniLean-template](https://github.com/WyattAu/OmniLean-template): Maximalist Lean 4 template: Lake, pinned toolchain, kernel-checked theorems as gates, lean-action CI, mathlib toggle.
- [OmniLaTeX-template](https://github.com/WyattAu/OmniLaTeX-template): A LaTeX template design to provide a universal template matching formatting needs for different institutes.
- [OmniLaTeX-CV](https://github.com/WyattAu/OmniLaTeX-CV): CV template derive from my OmniLaTeX-template repository, probably over engineered due to the original template mainly for academic and book writing.
- [OmniLaTeX-coverletter](https://github.com/WyattAu/OmniLaTeX-coverletter): Cover letter usage displaying OmniLaTeX-template multi document capabilities.
- [OmniLaTeX-docker](https://github.com/WyattAu/OmniLaTeX-docker): The docker image for https://github.com/WyattAu/OmniLaTeX-template.
- [OmniR-template](https://github.com/WyattAu/OmniR-template): A starter monorepo template for R projects.
- [engineering-standards](https://github.com/WyattAu/engineering-standards): Engineering standards: shared CI, policies, templates for the WyattAu kit ecosystem.
- [PatentSafePermissiveLicense](https://github.com/WyattAu/PatentSafePermissiveLicense): Patent-Safe Permissive License is inspired by Apache-2 for better readibility and more explicit clause declarations.
- [omni-copier-e2e](https://github.com/WyattAu/omni-copier-e2e): Maximalist Rust monorepo template: cargo workspace + estate tier-a gates.
- [omni-python-e2e](https://github.com/WyattAu/omni-python-e2e): E2E derived repo for OmniPython-template update channel (ADR-0001).
- [conan-center-index](https://github.com/WyattAu/conan-center-index).
- [latex2e](https://github.com/WyattAu/latex2e).
- [luaotfload](https://github.com/WyattAu/luaotfload).
- [OmniSkill-template](https://github.com/WyattAu/OmniSkill-template): Canonical agent-skill skeleton, validated by skillkit in CI.
- Private: `OmniFlutter-template`.

## Personal and private (9 repositories)

- [uofg_r_mono](https://github.com/WyattAu/uofg_r_mono): An R monorepo template: multiple R packages live in one repository, sharing a single.
- Private: `wyatt-cv`, `coa`, `uofg_sml_soc_docs`, `phys-maths-gypt-notes`, `FlutterSSG`, `homebite_docs`, `pediment-pro`, `peptide-web`.

## License

Individual projects are licensed under MIT, Apache-2.0, or AGPL-3.0 as specified in their repositories.

## Provenance of this document

Generated on 2026-10-23 from the GitHub repository listing (214 public non-fork repositories via the API plus 14 private repositories named from account metadata), with per-repository descriptions taken verbatim from each repository's own metadata, em dash characters removed, and headings annotated with per-heading counts so completeness is checkable by inspection.
