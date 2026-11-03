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
| **[cr-coalesce](https://github.com/Gwash3189/cr-coalesce)** | Singleflight request coalescing to deduplicate concurrent in-flight work with optional TTL caching | [![CI](https://github.com/Gwash3189/cr-coalesce/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-coalesce/actions/workflows/ci.yml) | [GitHub](https://github.com/Gwash3189/cr-coalesce) |
| **[cr-drip](https://github.com/Gwash3189/cr-drip)** | Sliding window rate limiting and token bucket throttling with wait budgets and declarative macro wrappers | [![CI](https://github.com/Gwash3189/cr-drip/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-drip/actions/workflows/ci.yml) | [GitHub](https://github.com/Gwash3189/cr-drip) |

---

### Quick Reference

### 1. `cr-semafor` — Concurrency Bounding
[![CI](https://github.com/Gwash3189/cr-semafor/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-semafor/actions/workflows/ci.yml)

```yaml
dependencies:
  cr-semafor:
    github: Gwash3189/cr-semafor
```

```crystal
require "cr-semafor"

class Worker
  include Semafor

  semafor key: :worker_pool, workers: 5, method: :perform

  def perform
    # bounded work
  end
end
```

### 2. `cr-doover` — Retries & Backoff
[![CI](https://github.com/Gwash3189/cr-doover/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-doover/actions/workflows/ci.yml)

```yaml
dependencies:
  cr-doover:
    github: Gwash3189/cr-doover
```

```crystal
require "cr-doover"

class Client
  include Doover

  do_over method: :fetch, strategy: :exponential, attempts: 3, delay: 100.milliseconds

  def fetch
    # guarded against transient errors
  end
end
```

### 3. `cr-fusebox` — Circuit Breaker
[![CI](https://github.com/Gwash3189/cr-fusebox/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-fusebox/actions/workflows/ci.yml)

```yaml
dependencies:
  cr-fusebox:
    github: Gwash3189/cr-fusebox
```

```crystal
require "cr-fusebox"

class Payments
  include Fusebox

  breaker :charge,
    failures: 5,
    within: 10.seconds,
    cooldown: 30.seconds,
    fallback: :charge_fallback

  def charge(amount : Int32)
    # downstream call
  end

  def charge_fallback(error : Exception)
    # graceful fallback
  end
end
```

### 4. `cr-coalesce` — Singleflight Request Coalescing
[![CI](https://github.com/Gwash3189/cr-coalesce/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-coalesce/actions/workflows/ci.yml)

```yaml
dependencies:
  cr-coalesce:
    github: Gwash3189/cr-coalesce
```

```crystal
require "cr-coalesce"

class UserRepo
  include Coalesce

  coalesce key: ->(id : String) { "user:#{id}" }, method: :fetch_user, ttl: 30.seconds

  def fetch_user(id : String) : User
    Database.users.find(id)
  end
end
```

### 5. `cr-drip` — Rate Limiting & Throttling
[![CI](https://github.com/Gwash3189/cr-drip/actions/workflows/ci.yml/badge.svg)](https://github.com/Gwash3189/cr-drip/actions/workflows/ci.yml)

```yaml
dependencies:
  cr-drip:
    github: Gwash3189/cr-drip
```

```crystal
require "cr-drip"

class ApiClient
  include Drip

  drip :fetch_data,
    allow: 100,
    per: 1.minute,
    wait: 5.seconds,
    key: ->(id : String) { "api:#{id}" }

  def fetch_data(id : String) : String
    # rate limited work
  end
end
```

---

### Tooling & Standards

Every Crystal library in this collection adheres to the same engineering standards:
- **Zero runtime dependencies**
- **Fiber-native concurrency** using Crystal channels and mutexes
- **Declarative macros (`include ...`)** with `previous_def` wrapping
- **Testing**: Native `crystal spec` following [Even Better Specs](https://evenbetterspecs.github.io/)
- **Formatting**: Checked with `crystal tool format --check`
- **CI**: GitHub Actions running format check and `crystal spec --error-on-warnings`

## License

MIT
