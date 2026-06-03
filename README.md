<div align="center">
  <img src="https://raw.githubusercontent.com/astraloghq/.github/main/profile/astralog.png" alt="AstraLog Logo" width="500">

  <h3>The hyper-efficient log ingestion pipeline for modern architectures</h3>
  
  <p>
    <a href="https://astralog.cloud"><strong>astralog.cloud</strong></a> | 
    <a href="https://github.com/astraloghq/astralog"><strong>Core Engine (V1)</strong></a> |
    <a href="#sdks"><strong>Official SDKs</strong></a>
  </p>

  ---
</div>

AstraLog is an open-source, high-performance logging platform built to solve the fundamental problem of log ingestion at scale: analytical databases are not designed for thousands of concurrent, single-row inserts.

By decoupling ingestion from analytical storage using an S3-backed **"Shock Absorber"** pattern, AstraLog provides ultra-low latency ingestion and blistering-fast analytical queries while cutting infrastructure bills down to a fraction.

### ⚡ Key Features

* **The Shock Absorber Pattern:** High-concurrency Go ingestion layer that acts as a buffer, pushing logs directly to memory.
* **Cost-Efficient Staging:** Temporary, highly-durable object storage (S3/MinIO) absorbs massive traffic spikes using GZIP compression.
* **Blazing Fast Analytics:** Bulk-consolidated writes directly into ClickHouse (`MergeTree` engine) for sub-millisecond query execution.
* **Designed for Edge & Serverless:** Built to handle stateless, efímeras connections (Cloudflare Workers, Vercel, AWS Lambda) with standard HTTP/gRPC.
* **Resilience Built-in:** Graceful shutdowns with Go `sync.WaitGroup` ensures zero data loss during server restarts.

---

<h3 id="sdks">📦 Official SDKs</h3>

Integrate AstraLog into your applications with our lightweight, non-blocking native clients:

* [**astralog-go**](https://github.com/astraloghq/astralog-go) – High-performance client optimized for concurrent environments and Zero-Allocation logs.
* [**astralog-js**](https://github.com/astraloghq/astralog-js) – Isomorphic client designed for Node.js and Edge/Serverless runtimes (Cloudflare Workers, Vercel).

---

<div align="center">
  <p>Protected under the Business Source License 1.1 (BSL). Free for development, testing, and startups under $100k/year.</p>
  <p>Looking for Enterprise BYOB (Bring Your Own Cloud) or SaaS? Contact us at <a href="https://astralog.cloud">astralog.cloud</a></p>
</div>
