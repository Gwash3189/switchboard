# switchboard

Central index and status dashboard for our suite of zero-dependency, fluent TypeScript concurrency, resilience, and caching libraries.

## Libraries

| Library | Description | CI Status | npm | Links |
| :--- | :--- | :--- | :--- | :--- |
| **[semafor](https://github.com/Gwash3189/semafor)** | Keyed semaphores for bounding concurrent work with wait and execution timeouts | [![CI](https://github.com/Gwash3189/semafor/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/semafor/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/semafor.svg)](https://www.npmjs.com/package/@gwash3189/semafor) | [GitHub](https://github.com/Gwash3189/semafor) · [npm](https://www.npmjs.com/package/@gwash3189/semafor) |
| **[doover](https://github.com/Gwash3189/doover)** | Fluent retry policies with exponential, linear, and constant backoff | [![CI](https://github.com/Gwash3189/doover/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/doover/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/doover.svg)](https://www.npmjs.com/package/@gwash3189/doover) | [GitHub](https://github.com/Gwash3189/doover) · [npm](https://www.npmjs.com/package/@gwash3189/doover) |
| **[fusebox](https://github.com/Gwash3189/fusebox)** | Keyed circuit breakers with sliding failure windows, cooldowns, and fallbacks | [![CI](https://github.com/Gwash3189/fusebox/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/fusebox/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/fusebox.svg)](https://www.npmjs.com/package/@gwash3189/fusebox) | [GitHub](https://github.com/Gwash3189/fusebox) · [npm](https://www.npmjs.com/package/@gwash3189/fusebox) |
| **[coalesce](https://github.com/Gwash3189/coalesce)** | Singleflight request coalescing to deduplicate concurrent in-flight work | [![CI](https://github.com/Gwash3189/coalesce/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/coalesce/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/coalesce.svg)](https://www.npmjs.com/package/@gwash3189/coalesce) | [GitHub](https://github.com/Gwash3189/coalesce) · [npm](https://www.npmjs.com/package/@gwash3189/coalesce) |
| **[drip](https://github.com/Gwash3189/drip)** | Keyed rate limiting and token bucket throttling with optional wait queues | [![CI](https://github.com/Gwash3189/drip/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/drip/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/drip.svg)](https://www.npmjs.com/package/@gwash3189/drip) | [GitHub](https://github.com/Gwash3189/drip) · [npm](https://www.npmjs.com/package/@gwash3189/drip) |
| **[pantry](https://github.com/Gwash3189/pantry)** | Pluggable cache (in-process default) with TTL, LRU eviction, and `stale-while-revalidate` | [![CI](https://github.com/Gwash3189/pantry/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/pantry/actions/workflows/ci.yml) | [![npm](https://img.shields.io/npm/v/@gwash3189/pantry.svg)](https://www.npmjs.com/package/@gwash3189/pantry) | [GitHub](https://github.com/Gwash3189/pantry) · [npm](https://www.npmjs.com/package/@gwash3189/pantry) |

---

## Quick Reference

### 1. `@gwash3189/semafor` — Concurrency Bounding
[![CI](https://github.com/Gwash3189/semafor/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/semafor/actions/workflows/ci.yml) [![npm](https://img.shields.io/npm/v/@gwash3189/semafor.svg)](https://www.npmjs.com/package/@gwash3189/semafor)

```bash
npm install @gwash3189/semafor
```

```ts
import { semafor } from '@gwash3189/semafor'

const { release } = await semafor(
  'key',
  { wait: 5_000, workers: 35, limit: 2_500 },
  async (release) => {
    try {
      // ... do work
    } finally {
      await release()
    }
  }
)
```

### 2. `@gwash3189/doover` — Retries & Backoff
[![CI](https://github.com/Gwash3189/doover/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/doover/actions/workflows/ci.yml) [![npm](https://img.shields.io/npm/v/@gwash3189/doover.svg)](https://www.npmjs.com/package/@gwash3189/doover)

```bash
npm install @gwash3189/doover
```

```ts
import Retry from '@gwash3189/doover'

const result = await Retry.exponential
  .attempts(3)
  .work(async () => fetchRemoteResource())
  .on('retry', (err) => true)
  .on('exhausted', (err) => console.error('Out of retries', err))
```

### 3. `@gwash3189/fusebox` — Circuit Breaker
[![CI](https://github.com/Gwash3189/fusebox/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/fusebox/actions/workflows/ci.yml) [![npm](https://img.shields.io/npm/v/@gwash3189/fusebox.svg)](https://www.npmjs.com/package/@gwash3189/fusebox)

```bash
npm install @gwash3189/fusebox
```

```ts
import Breaker from '@gwash3189/fusebox'

const customer = await Breaker.for('stripe-api')
  .threshold({ failures: 5, within: 10_000 })
  .cooldown(30_000)
  .fallback(() => ({ cached: true }))
  .work(async () => fetchStripeCustomer(id))
```

### 4. `@gwash3189/coalesce` — Singleflight Request Coalescing
[![CI](https://github.com/Gwash3189/coalesce/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/coalesce/actions/workflows/ci.yml) [![npm](https://img.shields.io/npm/v/@gwash3189/coalesce.svg)](https://www.npmjs.com/package/@gwash3189/coalesce)

```bash
npm install @gwash3189/coalesce
```

```ts
import { Coalesce } from '@gwash3189/coalesce'

const user = await Coalesce.key(`user:${id}`)
  .ttl(2_000)
  .work(async () => db.users.find(id))
```

### 5. `@gwash3189/drip` — Rate Limiting & Throttling
[![CI](https://github.com/Gwash3189/drip/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/drip/actions/workflows/ci.yml) [![npm](https://img.shields.io/npm/v/@gwash3189/drip.svg)](https://www.npmjs.com/package/@gwash3189/drip)

```bash
npm install @gwash3189/drip
```

```ts
import Drip from '@gwash3189/drip'

const response = await Drip.key(`api:${orgId}`)
  .allow(100)
  .per('1m')
  .wait(5_000)
  .work(async () => callExternalApi())
```

### 6. `@gwash3189/pantry` — Pluggable Cache & Stale-While-Revalidate
[![CI](https://github.com/Gwash3189/pantry/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/pantry/actions/workflows/ci.yml) [![npm](https://img.shields.io/npm/v/@gwash3189/pantry.svg)](https://www.npmjs.com/package/@gwash3189/pantry)

```bash
npm install @gwash3189/pantry
```

```ts
import Pantry from '@gwash3189/pantry'

const stats = await Pantry.key('dashboard:stats')
  .ttl('1m')
  .staleWhileRevalidate('5m')
  .fetch(async () => computeHeavyStats())
```

---

## Tooling & Standards

Every library in this collection adheres to the same engineering standards:
- **Zero runtime dependencies**
- **Build**: Dual ESM + CJS + `.d.ts` bundles via [`tsdown`](https://github.com/rolldown/tsdown)
- **Linting**: [`oxlint`](https://oxc.rs/docs/guide/usage/linter.html) with strict TypeScript & Vitest rules
- **Testing**: [`vitest`](https://vitest.dev/) following [Even Better Specs](https://evenbetterspecs.github.io/) (`1` `expect` per `it`, no hooks, no `.each`, self-contained Arrange-Act-Assert)
- **CI**: GitHub Actions running lint, type-check, test, and build on `main`

## License

MIT
