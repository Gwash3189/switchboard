# switchboard

Central index and status dashboard for our suite of zero-dependency, fluent TypeScript and Crystal concurrency, resilience, and caching libraries.
## Typescript
### Libraries

| Library | Description | CI Status | npm | Links |
| :--- | :--- | :--- | :--- | :--- |
| **[semafor](https://github.com/Gwash3189/semafor)** | Keyed semaphores for bounding concurrent work with wait and execution timeouts | [![CI](https://github.com/Gwash3189/semafor/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/semafor/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/semafor.svg)](https://www.npmjs.com/package/@gwash3189/semafor) | [GitHub](https://github.com/Gwash3189/semafor) · [npm](https://www.npmjs.com/package/@gwash3189/semafor) |
| **[doover](https://github.com/Gwash3189/doover)** | Fluent retry policies with exponential, linear, and constant backoff | [![CI](https://github.com/Gwash3189/doover/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/doover/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/doover.svg)](https://www.npmjs.com/package/@gwash3189/doover) | [GitHub](https://github.com/Gwash3189/doover) · [npm](https://www.npmjs.com/package/@gwash3189/doover) |
| **[fusebox](https://github.com/Gwash3189/fusebox)** | Keyed circuit breakers with sliding failure windows, cooldowns, and fallbacks | [![CI](https://github.com/Gwash3189/fusebox/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/fusebox/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/fusebox.svg)](https://www.npmjs.com/package/@gwash3189/fusebox) | [GitHub](https://github.com/Gwash3189/fusebox) · [npm](https://www.npmjs.com/package/@gwash3189/fusebox) |
| **[coalesce](https://github.com/Gwash3189/coalesce)** | Singleflight request coalescing to deduplicate concurrent in-flight work | [![CI](https://github.com/Gwash3189/coalesce/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/coalesce/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/coalesce.svg)](https://www.npmjs.com/package/@gwash3189/coalesce) | [GitHub](https://github.com/Gwash3189/coalesce) · [npm](https://www.npmjs.com/package/@gwash3189/coalesce) |
| **[drip](https://github.com/Gwash3189/drip)** | Keyed rate limiting and token bucket throttling with optional wait queues | [![CI](https://github.com/Gwash3189/drip/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/drip/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/drip.svg)](https://www.npmjs.com/package/@gwash3189/drip) | [GitHub](https://github.com/Gwash3189/drip) · [npm](https://www.npmjs.com/package/@gwash3189/drip) |
| **[pantry](https://github.com/Gwash3189/pantry)** | Pluggable cache (in-process default) with TTL, LRU eviction, and `stale-while-revalidate` | [![CI](https://github.com/Gwash3189/pantry/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/pantry/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/pantry.svg)](https://www.npmjs.com/package/@gwash3189/pantry) | [GitHub](https://github.com/Gwash3189/pantry) · [npm](https://www.npmjs.com/package/@gwash3189/pantry) |

## Crystal

### Libraries

| Library | Description | CI Status | Links |
| :--- | :--- | :--- | :--- |
| **[cr-semafor](https://github.com/Gwash3189/cr-semafor)** | Keyed semaphores for bounding concurrent work with acquisition wait and execution timeouts | [![CI](https://github.com/Gwash3189/cr-semafor/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-semafor/actions/workflows/ci.yml) | [GitHub](https://github.com/Gwash3189/cr-semafor) |
| **[cr-doover](https://github.com/Gwash3189/cr-doover)** | Fluent retry policies with exponential, linear, constant, and immediate backoff, plus full jitter | [![CI](https://github.com/Gwash3189/cr-doover/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-doover/actions/workflows/ci.yml) | [GitHub](https://github.com/Gwash3189/cr-doover) |
| **[cr-fusebox](https://github.com/Gwash3189/cr-fusebox)** | Declarative circuit breakers with failure thresholds, sliding windows, cooldowns, fallbacks, and lifecycle hooks | [![CI](https://github.com/Gwash3189/cr-fusebox/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-fusebox/actions/workflows/ci.yml) | [GitHub](https://github.com/Gwash3189/cr-fusebox) |

## License

MIT
