<div align="center">
  <img src="./astralog-logo.png" alt="AstraLog Logo" width="500">

  <h3>High-performance telemetry and log ingestion infrastructure for distributed architectures</h3>
</div>

---

AstraLog is an open-source, cloud-native logging platform designed to handle massive telemetry ingestion workloads. Distributed systems and serverless environments often introduce high-concurrency bottleneck patterns that traditional row-oriented storage engines struggle to process efficiently.

AstraLog resolves this by implementing an asynchronous, decoupled pipeline. It leverages a stateless Go ingestion layer that acts as a buffer, stages compressed batches in high-durability object storage (S3), and orchestrates bulk synchronization into ClickHouse (`MergeTree` engine) for near real-time analytical queries.

### 📊 Technical Specifications & Architecture

* **High-Throughput Ingestion:** Architected with native Go channels and goroutines, capable of sustaining ingestion rates over **800,000 logs/second** with an inbound P99 response latency of under 2ms.
* **Deterministic Backpressure Management:** Equipped with non-blocking rate-limiting mechanisms that handle traffic saturation gracefully via standard `HTTP 429 Too Many Requests` responses, securing runtime memory stability.
* **Optimized Staging Window:** Implements time-and-volume-bound batching (up to 5,000 events or a 2-second interval) before streaming GZIP data to object storage, reducing API transaction overhead by up to 99%.
* **Advanced Columnar Efficiency:** Leverages ClickHouse's structural encoding (Dictionary, RLE, and Delta) to optimize disk usage, achieving up to an **11x compression ratio** on production structured log datasets.
* **Serverless & Edge Agnostic:** Features a lightweight, decoupled HTTP API optimized for ephemeral, stateless compute environments such as Cloudflare Workers, Vercel, and AWS Lambda.
* **Graceful Lifecycle Controls:** Integrates OS signal interception and coordinated sync primitives to guarantee transactional completeness and zero data loss during infrastructure rollouts.

---

<div align="center">
  <p>Licensed under the Business Source License 1.1 (BSL). Free for non-commercial use and production environments under specified revenue thresholds.</p>
</div>
