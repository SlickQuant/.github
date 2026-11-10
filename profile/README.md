# SlickQuant

**Open-source building blocks for algorithmic trading.**

We build software for market data, exchange simulation, and order execution,
along with the messaging, networking, and observability tools underneath.
Modern C++ is at the core, with Python interoperability and components for web
and desktop trading interfaces.

Use the libraries independently or combine them into a trading system.
Premium subscriptions add CME and ICE trading, simulation, and live market data
through licensed compiled libraries for slick-trader and slick-sim, with ongoing
updates and integration support.

[Website](https://www.slickquant.com) · [Trading systems](#trading-systems) · [Premium venues](#premium-venues) · [Exchange SDKs](#exchange-sdks) · [Infrastructure](#infrastructure) · [Python](#python-interoperability) · [Get involved](#get-involved)

## Trading systems

| Project | What it does |
| --- | --- |
| [slick-trader](https://github.com/SlickQuant/slick-trader) | Multi-broker trading engine with strategy plugins, position tracking, pre-trade risk checks, and a live dashboard. Premium adds CME and ICE order entry and live market data. |
| [slick-sim](https://github.com/SlickQuant/slick-sim) | Exchange simulator with a FIFO matching engine, optional live market data, and venue-compatible APIs for testing trading clients. Premium adds live CME MDP 3.0 and ICE iMpact feeds, plus venue-native protocol simulation. |
| [slick-orderbook](https://github.com/SlickQuant/slick-orderbook) | C++ order books for aggregated price levels and individual orders across multiple instruments. |
| [slick-stacker](https://github.com/SlickQuant/slick-stacker) | Maintains a ladder of orders around a target quote as acknowledgements, fills, cancels, and rejects arrive. |
| [slick-ladder](https://github.com/SlickQuant/slick-ladder) | Price ladder UI for web, WASM, and desktop, with aggregated and Market-By-Order views. |

## Premium venues

The core projects remain open source. Premium subscriptions cover both
slick-trader and slick-sim through licensed compiled libraries. Subscribe to CME,
ICE, or the CME + ICE bundle, with monthly or annual billing.

| Venue | Trading with slick-trader | Simulation with slick-sim |
| --- | --- | --- |
| CME | iLink 3 order entry, amendment and cancellation; MDP 3.0 price levels, order-by-order updates and trades; instrument discovery and trading status; feed and session recovery; persisted working orders and fill journaling. | Uses a live CME MDP 3.0 market data feed to build an order-by-order book for simulated execution; simulated iLink 3 sessions per market segment; MDP 3.0 multicast publishing with incremental A/B feeds, MBO/MBP snapshots and instrument definitions. |
| ICE | Binary Order Entry (BOE); Binary Utility Service (BUS) gateway and instrument discovery; iMpact full-order-depth data, price levels, trades and status; snapshot and session recovery; persisted working orders and fill journaling. | Uses a live ICE iMpact market data feed to build a full-order-depth book for simulated execution; simulated BUS discovery, Binary Order Gateway sessions and BOE order entry for outright futures; iMpact multicast publishing and snapshots. |

The CME subscription includes compiled libraries for `slick-trader-cme` and
`slick-sim-cme`; the ICE subscription includes `slick-trader-ice` and
`slick-sim-ice`. Delivery includes public headers and integration examples;
implementation source code is not included.

A valid runtime license is required to use the Premium integrations. Your
subscription includes license renewals, updates and integration support for
your selected venues. Cancel anytime: your license remains valid through the
end of your paid period, and continued use requires renewal.

Live feeds require your own venue market data access. All execution in slick-sim
is simulated. It does not place orders on CME or ICE or model your trades'
impact on the live market.

[See Premium features and pricing](https://slickquant.com/#premium).

To [request a Premium license](https://slickquant.com/#premium), open the request
form on our website and choose your venue and billing preference, then enter
your email address. We'll follow up to arrange payment, compiled library
delivery and your runtime license.
Premium subscriptions are separate from open-source sponsorship.

## Exchange SDKs

C++ clients for trading, market data, and account access.

| Project | Integration |
| --- | --- |
| [alpaca-cpp](https://github.com/SlickQuant/alpaca-cpp) | Alpaca Trading and Market Data APIs, with streaming support. |
| [coinbase-advanced-cpp](https://github.com/SlickQuant/coinbase-advanced-cpp) | Coinbase Advanced Trade REST and WebSocket APIs. |
| [hyperliquid-cpp](https://github.com/SlickQuant/hyperliquid-cpp) | Hyperliquid REST and WebSocket APIs, with native EIP-712 signing. |

## Infrastructure

Reusable libraries for applications where throughput, latency, and memory
behavior matter, including applications outside trading.

| Project | What it does |
| --- | --- |
| [slick-queue](https://github.com/SlickQuant/slick-queue) | Lock-free multi-producer, multi-consumer queues with optional shared memory. |
| [slick-stream-buffer](https://github.com/SlickQuant/slick-stream-buffer) | Lock-free byte streams that publish message records from one producer to multiple consumers. |
| [slick-stream-buffer-multiplexer](https://github.com/SlickQuant/slick-stream-buffer-multiplexer) | Combines multiple producer streams into one ordered stream for multiple consumers. |
| [slick-shm](https://github.com/SlickQuant/slick-shm) | Cross-platform shared memory for C++. |
| [slick-dynamic-buffer](https://github.com/SlickQuant/slick-dynamic-buffer) | Boost.Asio DynamicBuffer adapters for Slick buffer backends. |
| [slick-net](https://github.com/SlickQuant/slick-net) | HTTP, HTTPS, and WebSocket clients built on Boost.Beast. |
| [slick-socket](https://github.com/SlickQuant/slick-socket) | TCP and UDP multicast networking. |
| [slick-object-pool](https://github.com/SlickQuant/slick-object-pool) | Lock-free object pooling for predictable allocation behavior. |
| [slick-logger](https://github.com/SlickQuant/slick-logger) | Asynchronous logging with deferred formatting, multiple sinks, and shared-memory support. |
| [slick-perfmon](https://github.com/SlickQuant/slick-perfmon) | Latency instrumentation with statistics and collection in a background thread or separate process. |

## Python interoperability

Share queues and byte streams between Python and C++ processes through shared
memory:

- [slick-queue-py](https://github.com/SlickQuant/slick-queue-py) — multi-producer, multi-consumer queues.
- [slick-stream-buffer-py](https://github.com/SlickQuant/slick-stream-buffer-py) — single-producer, multi-consumer byte streams.
- [slick-stream-buffer-multiplexer-py](https://github.com/SlickQuant/slick-stream-buffer-multiplexer-py) — multiple producer streams with a shared ordering point.

See each project's README for compatible versions, memory layouts, and platform
requirements.

## Get involved

Start with a project's README for installation, examples, and current status.
Bug reports, documentation improvements, focused pull requests, and reproducible
benchmarks are welcome in the relevant repository. For performance reports,
include the workload, hardware, compiler, and build settings.

Each repository documents its own license and dependencies.

[Explore all repositories](https://github.com/orgs/SlickQuant/repositories) · [Sponsor SlickQuant](https://github.com/sponsors/SlickQuant)
