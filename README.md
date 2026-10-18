# Wyatt Au

Rust kit ecosystem for production services: 218 repositories (204 public, 14 private), of which the kit estate publishes to crates.io. Every repository is built to one [gate matrix](https://github.com/WyattAu/engineering-standards): build `--locked`, clippy `-D warnings`, cargo-deny, cargo-audit, llvm-cov thresholds, cargo-semver-checks, loom and miri where applicable, cargo-vet, release provenance. The estate composes as a system: [estate-integration](https://github.com/WyattAu/estate-integration) is the cross-crate proof.

The index below is complete. Every public repository appears exactly once under exactly one heading; every entry links to its repository, and each description is that repository's own metadata. Private repositories are listed by name only. Counts per heading are stated so completeness is checkable at a glance.


## HTTP, API and services (24 repositories)

- [axum-stack](https://github.com/WyattAu/axum-stack) ([crate](https://crates.io/crates/axum-stack)): Axum server utilities : shutdown, CORS, request ID, health routes, middleware stack.
- [axum-server](https://github.com/WyattAu/axum-server) ([crate](https://crates.io/crates/axum-server)): Axum server utilities : shutdown, CORS, request ID, health routes, middleware stack.
- [json-envelope](https://github.com/WyattAu/json-envelope) ([crate](https://crates.io/crates/json-envelope)): Standard API response envelope for Rust services.
- [http-error](https://github.com/WyattAu/http-error) ([crate](https://crates.io/crates/http-error)): Derive macro for mapping error enums to HTTP status codes.
- [app-error](https://github.com/WyattAu/app-error) ([crate](https://crates.io/crates/app-error)): Common application error variants with recovery classification.
- [errcode](https://github.com/WyattAu/errcode) ([crate](https://crates.io/crates/errcode)): ## Purpose.
- [api-types](https://github.com/WyattAu/api-types).
- [validkit](https://github.com/WyattAu/validkit) ([crate](https://crates.io/crates/validkit)): Unified input validation : typed newtypes for email, URL, phone, cron, tenant, locale with proptest.
- [paginate](https://github.com/WyattAu/paginate) ([crate](https://crates.io/crates/paginate)): ## Overview.
- [envstack](https://github.com/WyattAu/envstack) ([crate](https://crates.io/crates/envstack)): ## Features.
- [config-kit](https://github.com/WyattAu/config-kit) ([crate](https://crates.io/crates/config-kit)): Layered typed configuration for Rust : file → env → overrides with unknown-field denial, secret redaction, and hot reload.
- [fetch-kit](https://github.com/WyattAu/fetch-kit) ([crate](https://crates.io/crates/fetch-kit)): ## Features.
- [ratelimit](https://github.com/WyattAu/ratelimit).
- [idempotency-kit](https://github.com/WyattAu/idempotency-kit) ([crate](https://crates.io/crates/idempotency-kit)): Idempotency keys for Rust : scoped BLAKE3 key derivation, TTL claims with response replay, pluggable memory/redis stores.
- [outbox-kit](https://github.com/WyattAu/outbox-kit) ([crate](https://crates.io/crates/outbox-kit)): Transactional outbox for Rust : durable event envelopes, at-least-once dispatch with breaker-aware backoff, replay after restart.
- [webhookkit](https://github.com/WyattAu/webhookkit).
- [ws-kit](https://github.com/WyattAu/ws-kit) ([crate](https://crates.io/crates/ws-kit)): Generic authenticated typed WebSocket : BroadcastHub, RoomManager, heartbeat.
- [uds-kit](https://github.com/WyattAu/uds-kit) ([crate](https://crates.io/crates/uds-kit)): Timeout-aware Unix domain socket connect/read/write helpers for Tokio : transport-only, protocol-agnostic.
- [eventbus](https://github.com/WyattAu/eventbus).
- [worker-kit](https://github.com/WyattAu/worker-kit) ([crate](https://crates.io/crates/worker-kit)): Periodic job scheduling for Rust services : jittered intervals, graceful drain, breaker-aware failure budgets, optional leader election.
- [healthkit](https://github.com/WyattAu/healthkit).
- [geo-kit](https://github.com/WyattAu/geo-kit).
- Private: `deploy-webhook-rs`, `eventbusd`.

## Auth, identity and policy (11 repositories)

- [tokenkit](https://github.com/WyattAu/tokenkit).
- [oauth-toolkit](https://github.com/WyattAu/oauth-toolkit) ([crate](https://crates.io/crates/oauth-toolkit)): Shared OAuth2/OIDC primitives : crypto, PKCE, scopes, CSRF, social login, OIDC, JWKS validation.
- [webauthn-kit](https://github.com/WyattAu/webauthn-kit) ([crate](https://crates.io/crates/webauthn-kit)): Standalone WebAuthn/FIDO2 passkey verification kit for Rust: CTAP2 parsing, COSE ES256/RS256 via ring, replay/freshness protection, sign-count clone detection. No storage, no framework.
- [scim-kit](https://github.com/WyattAu/scim-kit) ([crate](https://crates.io/crates/scim-kit)): Self-contained SCIM 2.0 (RFC 7644) provisioning types, stores, and optional axum router.
- [accessctl](https://github.com/WyattAu/accessctl).
- [auditlog](https://github.com/WyattAu/auditlog).
- [policy-kit](https://github.com/WyattAu/policy-kit) ([crate](https://crates.io/crates/policy-kit)): Fail-closed Rego policy evaluation for Rust : bundle loading, dialect auto-detect, typed verdicts.
- [salting](https://github.com/WyattAu/salting).
- [cryptkit](https://github.com/WyattAu/cryptkit) ([crate](https://crates.io/crates/cryptkit)): ## Purpose.
- [typed-id](https://github.com/WyattAu/typed-id) ([crate](https://crates.io/crates/typed-id)): Type-safe ID newtypes via derive macro.
- Private: `authbox`.

## Data, storage and retrieval (13 repositories)

- [blobkit](https://github.com/WyattAu/blobkit) ([crate](https://crates.io/crates/blobkit)): Typed object storage : BlobStore trait with S3/Local/Memory backends, audit, presigned URLs.
- [cas-kit](https://github.com/WyattAu/cas-kit) ([crate](https://crates.io/crates/cas-kit)): Content-addressed blob store: BLAKE3 addressing, 2-hex bucketing, optional Zstd, packfiles, verify-on-read. Extracted from Suture.
- [delta-kit](https://github.com/WyattAu/delta-kit) ([crate](https://crates.io/crates/delta-kit)): Binary delta codec: Rabin rolling-hash copy/insert opcodes, prefix/suffix fast-path, binary-safe. Extracted from Suture.
- [crawlkit](https://github.com/WyattAu/crawlkit) ([crate](https://crates.io/crates/crawlkit)): Site crawl kit.
- [crawlkit-testbed](https://github.com/WyattAu/crawlkit-testbed): Ground-truth conformance testbed for crawlkit: a site with planted, documented defects, and a scorer that measures precision and recall against them.
- [tantivy-ext](https://github.com/WyattAu/tantivy-ext).
- [crdts-kit](https://github.com/WyattAu/crdts-kit) ([crate](https://crates.io/crates/crdts-kit)): CRDT toolkit : RGA replicated string with tombstones, participant presence, serde + wasm support.
- [shared-state](https://github.com/WyattAu/shared-state) ([crate](https://crates.io/crates/shared-state)): Concurrent state utilities : readiness gates, TTL caches, shared counters, type aliases.
- [poolkit](https://github.com/WyattAu/poolkit) ([crate](https://crates.io/crates/poolkit)): ## Purpose.
- [slab-pool](https://github.com/WyattAu/slab-pool) ([crate](https://crates.io/crates/slab-pool)): Lock-free slab object pool : tagged-pointer ABA protection, RAII guards, loom+miri verified.
- [shm-rings](https://github.com/WyattAu/shm-rings) ([crate](https://crates.io/crates/shm-rings)): Lock-free shared-memory SPMC ring : power-of-two masked, cache-line aligned, zero SeqCst, loom+miri verified.
- [cachekit](https://github.com/WyattAu/cachekit).
- [crdt-demo](https://github.com/WyattAu/crdt-demo) ([crate](https://crates.io/crates/crdt-demo)): Live multi-user CRDT demo : crdts-kit + ws-kit, single binary, open two tabs and watch edits converge.

## Observability, time and hardware (10 repositories)

- [metrics-kit](https://github.com/WyattAu/metrics-kit) ([crate](https://crates.io/crates/metrics-kit)): Lock-free Prometheus-exposition metrics kit : counters, gauges, histograms with cache-line padding, cardinality guards, VictoriaMetrics/Grafana-compatible output.
- [telemetry-init](https://github.com/WyattAu/telemetry-init) ([crate](https://crates.io/crates/telemetry-init)): One-call observability bootstrap for Rust services : tracing + metrics + OTLP wired with estate defaults.
- [otelkit](https://github.com/WyattAu/otelkit) ([crate](https://crates.io/crates/otelkit)): ## Purpose.
- [otel-stack](https://github.com/WyattAu/otel-stack).
- [observability-assets](https://github.com/WyattAu/observability-assets): Central VictoriaMetrics + Grafana assets for every shipping WyattAu build : scrape configs, vmalert rules, dashboards.
- [clock-kit](https://github.com/WyattAu/clock-kit) ([crate](https://crates.io/crates/clock-kit)): Time-source abstraction for Rust : monotonic/wall separation, TSC calibration, PTP quality detection, deterministic test clock.
- [clock](https://github.com/WyattAu/clock) ([crate](https://crates.io/crates/clock)): Trait-based time abstraction with mock clock for testing.
- [percentile-kit](https://github.com/WyattAu/percentile-kit) ([crate](https://crates.io/crates/percentile-kit)): Latency percentile tracking and budget gates for Rust : P50/P99 from criterion output, committed budgets, CI regression enforcement.
- [hw-kit](https://github.com/WyattAu/hw-kit) ([crate](https://crates.io/crates/hw-kit)): Hardware topology and control for Rust : CPU/NUMA discovery, core pinning, NUMA binding, hugepage reservation (Linux).
- [uring-kit](https://github.com/WyattAu/uring-kit) ([crate](https://crates.io/crates/uring-kit)): Reusable io_uring socket substrate : ring lifecycle, registered buffers, zero-copy socket ops (Linux).

## Resilience, concurrency and testing (14 repositories)

- [retry-backoff](https://github.com/WyattAu/retry-backoff) ([crate](https://crates.io/crates/retry-backoff)): Generic async retry with exponential backoff and jitter.
- [chaos-kit](https://github.com/WyattAu/chaos-kit) ([crate](https://crates.io/crates/chaos-kit)): Deterministic fault injection for Rust tests : latency, errors, partitions, and resource starvation with seeded scheduling.
- [testkit](https://github.com/WyattAu/testkit) ([crate](https://crates.io/crates/testkit)): Shared test utilities for Rust : test databases, HTTP servers, auth helpers, and assertions.
- [kit-conformance](https://github.com/WyattAu/kit-conformance): Shared conformance harness for the WyattAu Rust kit ecosystem.
- [graceful](https://github.com/WyattAu/graceful).
- [breaker](https://github.com/WyattAu/breaker).
- [pid-manager](https://github.com/WyattAu/pid-manager).
- [mcp-doctor](https://github.com/WyattAu/mcp-doctor) ([crate](https://crates.io/crates/mcp-doctor)): Audit an OpenCode MCP fleet: config, backends, credential entitlement, and real MCP handshakes.
- [flag-kit](https://github.com/WyattAu/flag-kit) ([crate](https://crates.io/crates/flag-kit)): Feature flags : FlagSet rollout, targeting, audit, OTel.
- [flaglab](https://github.com/WyattAu/flaglab) ([crate](https://crates.io/crates/flaglab)): Audit feature flags across repos and emit reviewable removal candidates (Piranha's missing orchestrator).
- [sieve-kit](https://github.com/WyattAu/sieve-kit) ([crate](https://crates.io/crates/sieve-kit)): Rule-based mail filtering engine: conditions, actions, bounded regex evaluation.
- [actor-kit](https://github.com/WyattAu/actor-kit) ([crate](https://crates.io/crates/actor-kit)): Work-stealing actor runtime : OTP supervision trees, crossbeam work-stealing, bounded backpressure.
- [tui-actions](https://github.com/WyattAu/tui-actions) ([crate](https://crates.io/crates/tui-actions)): Terminal action/keymap layer for Rust : chord parsing (ctrl+s, leader sequences), modal context stacks, conflict and unbound-key detection, help rows derived from the live keymap. No terminal dependency.
- Private: `flagsd`.

## Money, ledger and billing (9 repositories)

- [money](https://github.com/WyattAu/money).
- [ledger-kit](https://github.com/WyattAu/ledger-kit) ([crate](https://crates.io/crates/ledger-kit)): Double-entry ledger for Rust : decimal-money postings, outbox-backed journal, idempotent posting, tamper-evident history.
- [double-entry](https://github.com/WyattAu/double-entry) ([crate](https://crates.io/crates/double-entry)): Immutable double-entry accounting core : append-only journals, balanced posting, period close, reversal by counter-entry.
- [invoice-kit](https://github.com/WyattAu/invoice-kit) ([crate](https://crates.io/crates/invoice-kit)): Accounts-receivable invoicing for an SME ledger : three orthogonal document states, Peppol/EN 16931 arithmetic, per-jurisdiction rounding policy.
- [ap-kit](https://github.com/WyattAu/ap-kit) ([crate](https://crates.io/crates/ap-kit)): Accounts payable: supplier bills, input VAT recoverability, and the three-way split between payable, deductible tax and expense.
- [vat-rules](https://github.com/WyattAu/vat-rules) ([crate](https://crates.io/crates/vat-rules)): Tax categories, exemption codes, document types and rounding regimes shared by the AR and AP sides of an accounting ledger.
- [billing-kit](https://github.com/WyattAu/billing-kit) ([crate](https://crates.io/crates/billing-kit)): Billing primitives : Price with tax/discount, re-exporting decimal-money CurrencyAmount.
- [book-kit](https://github.com/WyattAu/book-kit) ([crate](https://crates.io/crates/book-kit)): Lock-free limit order book : price-time priority, single-writer/multi-reader snapshots, zero-allocation hot path, loom-verified.
- [hdwallet](https://github.com/WyattAu/hdwallet).

## Formats, parsers and conformance (22 repositories)

- [a2l-parse](https://github.com/WyattAu/a2l-parse) ([crate](https://crates.io/crates/a2l-parse)): ASAP2/A2L ECU description parser : PROJECT/MODULE/CHARACTERISTIC/MEASUREMENT/RECORD_LAYOUT/COMPU_METHOD, calibration data model.
- [cal-model](https://github.com/WyattAu/cal-model) ([crate](https://crates.io/crates/cal-model)): A2L calibration data model and session layer : characteristic binding, COMPU_METHOD conversions, limit validation, curve calibration.
- [dbc-parse](https://github.com/WyattAu/dbc-parse) ([crate](https://crates.io/crates/dbc-parse)): DBC file parser : CAN message definitions, signal layout (bit-offset/length/endianness/scaling), value tables, extended multiplexing.
- [can-core](https://github.com/WyattAu/can-core) ([crate](https://crates.io/crates/can-core)): CAN 2.0 and CAN FD frame codec : identifier parsing, DLC handling, bit-timing calculation.
- [xcp-core](https://github.com/WyattAu/xcp-core) ([crate](https://crates.io/crates/xcp-core)): XCP on CAN : Universal Measurement and Calibration Protocol: commands, responses, DAQ lists.
- [id3-core](https://github.com/WyattAu/id3-core) ([crate](https://crates.io/crates/id3-core)): ID3v1/ID3v2 audio tag reader and writer for Rust : CHAP/CTOC chapters, APIC art, no_std.
- [mp4-core](https://github.com/WyattAu/mp4-core) ([crate](https://crates.io/crates/mp4-core)): ISO-BMFF (MP4/M4A/M4B) box reader and writer for Rust : ilst metadata, chpl chapters, no_std.
- [cuesheet-core](https://github.com/WyattAu/cuesheet-core) ([crate](https://crates.io/crates/cuesheet-core)): CDRWIN cue sheet reader and writer : tracks, indices, MM:SS:FF at 75 fps, CD-TEXT, no_std.
- [font-parse](https://github.com/WyattAu/font-parse) ([crate](https://crates.io/crates/font-parse)): SFNT/OTF/TrueType/WOFF/WOFF2 binary font parser : offset tables, character maps, glyph outlines, variable fonts.
- [font-model](https://github.com/WyattAu/font-model) ([crate](https://crates.io/crates/font-model)): Typed owned editable font model : glyph outlines, cmap formats 4 and 12, metrics, validation, subsetting.
- [font-shape](https://github.com/WyattAu/font-shape).
- [font-conformance](https://github.com/WyattAu/font-conformance) ([crate](https://crates.io/crates/font-conformance)): Independent differential oracle for the estate text stack: font-parse vs fontations, font-shape vs the rival rasterizers, Err-not-panic over a hostile corpus.
- [sheet-core](https://github.com/WyattAu/sheet-core) ([crate](https://crates.io/crates/sheet-core)): Spreadsheet data model : sparse cells, dependency DAG, topological order, formula reference extraction.
- [sheet-engine](https://github.com/WyattAu/sheet-engine) ([crate](https://crates.io/crates/sheet-engine)): Spreadsheet calculation engine : dependency-driven incremental recalculation, Excel-compatible semantics, volatile function tracking.
- [sheet-xlsx](https://github.com/WyattAu/sheet-xlsx) ([crate](https://crates.io/crates/sheet-xlsx)): XLSX codec : workbook, worksheets, shared strings, styles, calc chain.
- [formula-lang](https://github.com/WyattAu/formula-lang) ([crate](https://crates.io/crates/formula-lang)): Spreadsheet formula language : tokenizer, Pratt parser, AST, evaluator core. Excel-compatible function semantics.
- [audiobook-core](https://github.com/WyattAu/audiobook-core) ([crate](https://crates.io/crates/audiobook-core)): Audiobook domain model for Rust : format-independent titles, parts and chapters from MP3 and M4B.
- [audiobook-conformance](https://github.com/WyattAu/audiobook-conformance) ([crate](https://crates.io/crates/audiobook-conformance)): Conformance harness for the WyattAu audiobook stack : cross-checks mp4-core/id3-core/audiobook-core against ffmpeg and ffprobe.
- [audiobook-shelf](https://github.com/WyattAu/audiobook-shelf) ([crate](https://crates.io/crates/audiobook-shelf)): Audiobook-first library manager : decides which files form one book, orders them by disc then track, parses the folder-name conventions a library is actually named with, and reports what is inconsistent.
- [ldir](https://github.com/WyattAu/ldir) ([crate](https://crates.io/crates/ldir)): LDIR (Low-level document intermediate representation), a universal document that compiles from an IR lang.
- [wire-kit](https://github.com/WyattAu/wire-kit) ([crate](https://crates.io/crates/wire-kit)): Zero-copy binary wire codecs : SBE block encoding and FIX 4.4 tag=value, bounds-checked, allocation-free decode, SIMD-assisted scanning.
- [sensors_rpi_pico](https://github.com/WyattAu/sensors_rpi_pico): this contains source code for taking measurements from the TMP117 temperature sensor, CMPS12 compass, VEML6075, ICP10125.

## Audio, DSP and media (3 repositories)

- [dsp-core](https://github.com/WyattAu/dsp-core) ([crate](https://crates.io/crates/dsp-core)): Foundational audio DSP primitives : biquad filters, FFT, convolution, windowing, dynamics, oscillators : allocation-free process paths.
- [dsp-spectral](https://github.com/WyattAu/dsp-spectral) ([crate](https://crates.io/crates/dsp-spectral)): Spectral audio analysis and restoration : STFT/ISTFT, mel/MFCC features, spectral gating, HPSS source separation.
- [media-kit](https://github.com/WyattAu/media-kit) ([crate](https://crates.io/crates/media-kit)): Full image pipeline : sniff, meta, resize, encode, composite, variants with bomb-guard and async support.

## Web frontends, UI and Leptos (19 repositories)

- [plychart](https://github.com/WyattAu/plychart) ([crate](https://crates.io/crates/plychart)): High-performance WASM charting library for Rust.
- [leptos-stale-indicator](https://github.com/WyattAu/leptos-stale-indicator) ([crate](https://crates.io/crates/leptos-stale-indicator)): Data freshness indicator for Leptos : shows LIVE/DATA STALE status based on fetch timestamps.
- [leptos-map-search](https://github.com/WyattAu/leptos-map-search) ([crate](https://crates.io/crates/leptos-map-search)): Map search/typeahead component for Leptos : filter and select countries with keyboard navigation.
- [leptos-sparkline](https://github.com/WyattAu/leptos-sparkline) ([crate](https://crates.io/crates/leptos-sparkline)): Leptos component (see repo).
- [leptos-capital-markers](https://github.com/WyattAu/leptos-capital-markers) ([crate](https://crates.io/crates/leptos-capital-markers)): Capital city markers for leptos-leaflet : renders weather-aware markers on a Leaflet map.
- [leptos-crypto-ws](https://github.com/WyattAu/leptos-crypto-ws) ([crate](https://crates.io/crates/leptos-crypto-ws)): Leptos component (see repo).
- [leptos-leaflet](https://github.com/WyattAu/leptos-leaflet).
- [leptos-macro](https://github.com/WyattAu/leptos-macro).
- [theme-kit](https://github.com/WyattAu/theme-kit) ([crate](https://crates.io/crates/theme-kit)): Typed design-token contract for the estate : DTCG 2025.10 in/out, semantic role vocabulary, build-failing WCAG contrast gate, derived CVD/high-contrast/monochrome variants, data-only emitters (CSS, VS Code, ANSI-16).
- [theme-egui](https://github.com/WyattAu/theme-egui) ([crate](https://crates.io/crates/theme-egui)): egui/epaint lowering for theme-kit : the adapter that makes the estate token contract real in chisel-doc, chisel-platform's future front-end, and any egui app. One file of placement, zero colour maths.
- [shroom-theme](https://github.com/WyattAu/shroom-theme): VS Code colour theme with 7 variants: dark, light, high-contrast, monochrome, and 3 dichromacy adaptations (deuteranopia, protanopia, tritanopia). 1049 tokens, alpha-composited WCAG 2.1 AA, APCA lightness separation, CVD simulation in linear RGB.
- [a11y-kit](https://github.com/WyattAu/a11y-kit) ([crate](https://crates.io/crates/a11y-kit)): Accessibility semantics layer for the estate : platform-free semantic node model (role, name, states, relations), tree audit as a CI gate, AccessKit conversion behind a feature. The layer nobody funds, owned.
- [color-kit](https://github.com/WyattAu/color-kit) ([crate](https://crates.io/crates/color-kit)): Colour science leaf for Rust : linear-sRGB core, Oklab/OkLCH, WCAG 2.1 AA contrast, perceptual lightness contrast, dichromat simulation, deterministic quantisation. no_std.
- [tauri-preset](https://github.com/WyattAu/tauri-preset).
- [i18n-kit](https://github.com/WyattAu/i18n-kit) ([crate](https://crates.io/crates/i18n-kit)): Runtime i18n for Rust: BCP 47 locales, flat catalogs with dot-notation keys, fallback chains, interpolation, simple pluralization.
- [polyfont](https://github.com/WyattAu/polyfont) ([crate](https://crates.io/crates/polyfont)): A multi font plugin for vscode and other editors.
- [tao](https://github.com/WyattAu/tao): The TAO of cross-platform windowing. A library in Rust built for Tauri.
- [tauri](https://github.com/WyattAu/tauri) ([crate](https://crates.io/crates/tauri)): Build smaller, faster, and more secure desktop and mobile applications with a web frontend.
- [wry](https://github.com/WyattAu/wry) ([crate](https://crates.io/crates/wry)): Cross-platform WebView library in Rust for Tauri.

## Sites and documentation (17 repositories)

- [pediment](https://github.com/WyattAu/pediment): Shared design tokens, components, hooks, and utilities for Astro+SolidJS+Starlight+Cloudflare projects.
- [starlight-sites](https://github.com/WyattAu/starlight-sites): Wyatt's Notes new site with starlight.
- [starlight-kit](https://github.com/WyattAu/starlight-kit).
- [starlight-progress](https://github.com/WyattAu/starlight-progress).
- [starlight-katex](https://github.com/WyattAu/starlight-katex).
- [starlight-content-guard](https://github.com/WyattAu/starlight-content-guard).
- [starlight-multi-site](https://github.com/WyattAu/starlight-multi-site).
- [starlight-interactive-islands](https://github.com/WyattAu/starlight-interactive-islands): Dont know why theres no standardized plugin.
- [starlight-cross-domain-sync](https://github.com/WyattAu/starlight-cross-domain-sync).
- [starlight-dse-test](https://github.com/WyattAu/starlight-dse-test): DSE study and test platform built with Astro Starlight.
- [docs-core](https://github.com/WyattAu/docs-core) ([crate](https://crates.io/crates/docs-core)): Rust docs pipeline core : CommonMark+GFM to static HTML with astro-island-compatible island emission, so a Rust shell hydrates the estate's existing SolidJS bundles. Consolidates Tachyon + docs-pipeline + the starlight-* stack (ADR-0004 §2.5).
- [docs-pipeline](https://github.com/WyattAu/docs-pipeline) ([crate](https://crates.io/crates/docs-pipeline)): Markdown rendering and tree-sitter syntax highlighting pipeline for documentation sites.
- [Tachyon](https://github.com/WyattAu/Tachyon): JIT documentation server with internal developer portal, the build step latency inherently in traditional SSG can be eliminated by reactive file watching on the host file system, while still able to compile as SSG if needed.
- [hydrated-personal-site](https://github.com/WyattAu/hydrated-personal-site).
- [WyattsNotes](https://github.com/WyattAu/WyattsNotes): Deprecated, new repo at https://github.com/WyattAu/starlight-sites. A list of personal notes modified for public use, require a high degree of contributions to polish.
- [forgeyard](https://github.com/WyattAu/forgeyard): Standardized repository templates with CI/CD for Rust, Astro+SolidJS, Starlight, and TypeScript projects.
- [cf-worker-utils](https://github.com/WyattAu/cf-worker-utils).

## AI, agents and search (8 repositories)

- [model-router](https://github.com/WyattAu/model-router) ([crate](https://crates.io/crates/model-router)): Cost-aware LLM routing core: per-model pricing, USD budget tracking, task-class routing with fallback chains.
- [simd-tokenizer](https://github.com/WyattAu/simd-tokenizer) ([crate](https://crates.io/crates/simd-tokenizer)): Safe SWAR-accelerated whitespace token estimator with optional exact tiktoken backend.
- [latent-oracle](https://github.com/WyattAu/latent-oracle): Searchless neural chess research engine : strictly 0-ply policy with symbolic invariants.
- [latent-oracle-data](https://github.com/WyattAu/latent-oracle-data): Data pipeline for latent-oracle: Lichess PGN to shards to Stockfish labels.
- [ironclaw](https://github.com/WyattAu/ironclaw) ([crate](https://crates.io/crates/ironclaw)): Fork of nearai/ironclaw : WyattAu staging with validkit adoption and clippy fixes.
- [morph](https://github.com/WyattAu/morph): The specification for a agentic programming language.
- [contact-miner](https://github.com/WyattAu/contact-miner) ([crate](https://crates.io/crates/contact-miner)): Multi-engine web contact discovery: emails, phones, WhatsApp/Telegram/Signal handles from public pages.
- [trendkit](https://github.com/WyattAu/trendkit) ([crate](https://crates.io/crates/trendkit)): Dev-trend crawler in Rust: GitHub/HN/crates.io snapshots, velocity scoring, personal relevance, Telegram digest.

## Mail and messaging (5 repositories)

- [mailkit](https://github.com/WyattAu/mailkit).
- [mail-sync-kit](https://github.com/WyattAu/mail-sync-kit) ([crate](https://crates.io/crates/mail-sync-kit)): Protocol-agnostic mail sync engines: IMAP (QRESYNC/CONDSTORE/IDLE), JMAP, SMTP submission (XOAUTH2), outbox queue.
- [barbican](https://github.com/WyattAu/barbican).
- [ws-barbican](https://github.com/WyattAu/ws-barbican) ([crate](https://crates.io/crates/ws-barbican)): Barbican wrapper for ws-kit : JWT auth via header/query/cookie.
- [kestrel](https://github.com/WyattAu/kestrel) ([crate](https://crates.io/crates/kestrel)): tui+gui email client in Rust.

## Applications and products (15 repositories)

- [ferro](https://github.com/WyattAu/ferro) ([crate](https://crates.io/crates/ferro)): High-performance, self-hosted file storage platform in Rust. WebDAV, OIDC, WASM, S3, full-text search.
- [suture](https://github.com/WyattAu/suture) ([crate](https://crates.io/crates/suture)): Core logic of suture.
- [clawdius](https://github.com/WyattAu/clawdius) ([crate](https://crates.io/crates/clawdius)): Faster then openclaw, remote agentic coding without worries with wasm sandbox and system bubble wrap to allow reading and prevent writing to system.
- [aileron](https://github.com/WyattAu/aileron) ([crate](https://crates.io/crates/aileron)): A blazingly fast, keyboard-driven web environment for developers. Native tiling. Lua-configurable. Zero-extension ad-blocking. And an integrated AI MCP server so your LLMs can finally see the web. Built in Rust, powered by Servo.
- [aperture-vault](https://github.com/WyattAu/aperture-vault) ([crate](https://crates.io/crates/aperture-vault)): A photo and video vault : single binary, content-addressed, Immich-compatible API. Faster ingest, less overhead.
- [CivitForge](https://github.com/WyattAu/CivitForge): Federated software forge, build for scaling to Petabytes of data, actions with kubernetes podmans, build in rust.
- [chisel-doc](https://github.com/WyattAu/chisel-doc) ([crate](https://crates.io/crates/chisel-doc)): Chisel Docs : an industrial-hardening fork of PdfCraft: a PDF reader/editor in pure Rust, built to a FAANG/defence-grade gate matrix.
- [chisel-platform](https://github.com/WyattAu/chisel-platform) ([crate](https://crates.io/crates/chisel-platform)): Platform side of Chisel Docs: identity, assets, and the tamper-evident document audit trail : composed from the WyattAu kit estate.
- [vane](https://github.com/WyattAu/vane): L4/L7 reverse proxy,edge gateway, micro sidecar monorepo.
- [estate-integration](https://github.com/WyattAu/estate-integration) ([crate](https://crates.io/crates/estate-integration)): Cross-crate dogfooding suite proving the WyattAu crate estate composes.
- [homebrew-clawdius](https://github.com/WyattAu/homebrew-clawdius): Homebrew tap for Clawdius.
- [homebrew-suture-merge-driver](https://github.com/WyattAu/homebrew-suture-merge-driver).
- [continuwuity](https://github.com/WyattAu/continuwuity): A community-driven Matrix homeserver.
- [aether-core](https://github.com/WyattAu/aether-core) ([crate](https://crates.io/crates/aether-core)): Aether-core is the open core logic for aether and the exact logic for Aether community edition.
- [warploom](https://github.com/WyattAu/warploom): A data-oriented C++ engine with deterministic simulation, Vulkan rendering, an ECS, and a time-warp editor.

## Infrastructure and hosting (12 repositories)

- [traefik-setup](https://github.com/WyattAu/traefik-setup): Docker-compose repository for setting up traefik.
- [traefik-stack](https://github.com/WyattAu/traefik-stack).
- [EvergreenImageRegistry](https://github.com/WyattAu/EvergreenImageRegistry): LTS images by community efforts.
- [EvergreenShims](https://github.com/WyattAu/EvergreenShims): Shims for building images with, especially those ones without a healthcheck.
- [RunnerImages](https://github.com/WyattAu/RunnerImages): A list of base images usable for CI.
- [forgejo-k8s-runner](https://github.com/WyattAu/forgejo-k8s-runner).
- [gitea-setup](https://github.com/WyattAu/gitea-setup).
- [hosting-api](https://github.com/WyattAu/hosting-api) ([crate](https://crates.io/crates/hosting-api)): Control-plane API for the WyattAu hosting platform : tenant state, backup triggers, metrics. Dogfoods telemetry-init, metrics-kit, testkit.
- [hosting-dashboard](https://github.com/WyattAu/hosting-dashboard): Customer dashboard for the WyattAu hosting platform : tenants, backup jobs, health. Astro + SolidJS, dogfoods pediment.
- [SimpleInfrastructureStack](https://github.com/WyattAu/SimpleInfrastructureStack): Simple truenas infrasturcture stack with terraform.
- [cachyos_sys_dotfiles](https://github.com/WyattAu/cachyos_sys_dotfiles).
- Private: `windows-dotfiles`.

## Templates and estate governance (25 repositories)

- [OmniRust-template](https://github.com/WyattAu/OmniRust-template): Maximalist Rust monorepo template : cargo workspace, estate tier-a gates (clippy pedantic/loom/miri/llvm-cov/deny/vet), nix + dual devcontainers.
- [OmniTS-template](https://github.com/WyattAu/OmniTS-template): Maximalist TypeScript monorepo template : bun workspaces, Astro shell + SolidJS islands, biome, vitest + playwright, changesets.
- [OmniGo-template](https://github.com/WyattAu/OmniGo-template): Maximalist Go monorepo template : go.work anchor, golangci-lint v2, govulncheck, native fuzzing, goreleaser with homebrew tap.
- [OmniPython-template](https://github.com/WyattAu/OmniPython-template): A starting point for python projects.
- [OmniHaskell-template](https://github.com/WyattAu/OmniHaskell-template): Maximalist Haskell monorepo template : cabal multi-package, nix-owned GHC 9.8 (9.6/9.10 legs), HLS, fourmolu + hlint + weeder, tasty + hedgehog.
- [OmniCPP-template](https://github.com/WyattAu/OmniCPP-template): A starter template for CMake projects.
- [OmniCPP-docker](https://github.com/WyattAu/OmniCPP-docker): Docker containing CPP and CMake tooling.
- [OmniEmbedded-template](https://github.com/WyattAu/OmniEmbedded-template): Maximalist embedded C/C++ template : RP2040/RP2350, pinned pico-sdk, CMake presets, PIO scaffold, flash/RAM budget gates, HIL smoke.
- [OmniInfra-template](https://github.com/WyattAu/OmniInfra-template): Maximalist OpenTofu infrastructure template : tflint, fail-closed conftest/OPA policy gates, terraform-docs, sops, human-gated apply.
- [OmniDotfiles-template](https://github.com/WyattAu/OmniDotfiles-template): Maximalist dotfiles template : chezmoi-first, shellcheck + shfmt + bats, ubuntu+arch container CI for OS parity.
- [OmniDocs-template](https://github.com/WyattAu/OmniDocs-template): Maximalist Starlight documentation site template : Astro + Starlight, bun, biome, Pages deploy on every merge.
- [OmniLean-template](https://github.com/WyattAu/OmniLean-template): Maximalist Lean 4 template : Lake, pinned toolchain, kernel-checked theorems as gates, lean-action CI, mathlib toggle.
- [OmniLaTeX-template](https://github.com/WyattAu/OmniLaTeX-template): A LaTeX template design to provide a universal template matching formatting needs for different institutes.
- [OmniLaTeX-CV](https://github.com/WyattAu/OmniLaTeX-CV): CV template derive from my OmniLaTeX-template repository, probably over engineered due to the original template mainly for academic and book writing .
- [OmniLaTeX-coverletter](https://github.com/WyattAu/OmniLaTeX-coverletter): Cover letter usage displaying OmniLaTeX-template multi document capabilities.
- [OmniLaTeX-docker](https://github.com/WyattAu/OmniLaTeX-docker): The docker image for https://github.com/WyattAu/OmniLaTeX-template.
- [OmniR-template](https://github.com/WyattAu/OmniR-template): A starter monorepo template for R projects.
- [engineering-standards](https://github.com/WyattAu/engineering-standards): Engineering standards : shared CI, policies, templates for the WyattAu kit ecosystem.
- [PatentSafePermissiveLicense](https://github.com/WyattAu/PatentSafePermissiveLicense): Patent-Safe Permissive License is inspired by Apache-2 for better readibility and more explicit clause declarations.
- [omni-copier-e2e](https://github.com/WyattAu/omni-copier-e2e).
- [omni-python-e2e](https://github.com/WyattAu/omni-python-e2e): E2E derived repo for OmniPython-template update channel (ADR-0001).
- [conan-center-index](https://github.com/WyattAu/conan-center-index): Recipes for the ConanCenter repository.
- [latex2e](https://github.com/WyattAu/latex2e): The LaTeX2e kernel.
- [luaotfload](https://github.com/WyattAu/luaotfload): OpenType font loader for LuaTeX.
- Private: `OmniFlutter-template`.

## Personal and private (9 repositories)

- [uofg_r_mono](https://github.com/WyattAu/uofg_r_mono).
- Private: `wyatt-cv`, `coa`, `uofg_sml_soc_docs`, `phys-maths-gypt-notes`, `FlutterSSG`, `homebite_docs`, `pediment-pro`, `peptide-web`.

## License

Individual projects are licensed under MIT, Apache-2.0, or AGPL-3.0 as specified in their repositories.


## Provenance of this document

Generated on 2026-10-18 from the GitHub repository listing (203 public repositories via the API plus 16 private repositories named from account metadata), with per-repository descriptions taken verbatim from each repository's own metadata, em-dash characters removed, and headings annotated with per-heading counts so completeness is checkable by inspection.
