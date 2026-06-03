<div align="center">
  <img src="/astralog.png" alt="AstraLog Logo" width="500">

  <h3>The hyper-efficient log ingestion pipeline for modern architectures</h3>
</div>

---

AstraLog is an open-source, high-performance logging platform built to solve the fundamental problem of log ingestion at scale: analytical databases are not designed for thousands of concurrent, single-row inserts.

By decoupling ingestion from analytical storage using an S3-backed **"Shock Absorber"** pattern, AstraLog provides ultra-low latency ingestion and blistering-fast analytical queries while cutting infrastructure bills down to a fraction.

### ⚡ Key Features

* **The Shock Absorber Pattern:** High-concurrency Go ingestion layer that acts as a buffer, pushing logs directly to memory.
* **Cost-Efficient Staging:** Temporary, highly-durable object storage (S3/MinIO) absorbs massive traffic spikes using GZIP compression.
* **Blazing Fast Analytics:** Bulk-consolidated writes directly into ClickHouse (`MergeTree` engine) for sub-millisecond query execution.
* **Designed for Edge & Serverless:** Built to handle stateless, ephemeral connections (Cloudflare Workers, Vercel, AWS Lambda) with standard HTTP/gRPC.
* **Resilience Built-in:** Graceful shutdowns with Go `sync.WaitGroup` ensures zero data loss during server restarts.

---

<div align="center">
  <p>Protected under the Business Source License 1.1 (BSL).</p>
</div>
