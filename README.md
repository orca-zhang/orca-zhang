<div align="center">

# Orca Zhang

**Distributed Systems · Storage · AI Infrastructure**

15 years of engineering · Tech Leader / Architect

[简体中文](README_cn.md) · [Email](mailto:orca.zhang@yahoo.com)

</div>

I design, build and operate infrastructure for distributed storage, enterprise data protection, community services and AI inference. I learn new domains quickly and take systems from core implementation through rollout and long-term operations, with a focus on **performance, availability and cost**.

## Engineering track record

### Distributed storage & enterprise data protection

- **Backup & disaster recovery**: Optimized the core storage engine to deliver **+100% overall system performance**, bringing a commercial backup and disaster-recovery system to a **world-leading performance level**.
- **Enterprise file sharing**: Led core engine development for an enterprise file-sharing platform built on a **fourth-generation distributed filesystem**. Its vendor earned **8 consecutive years of Gartner recognition**, as the **only Asia-Pacific vendor listed in its category**.
- **Distributed object storage**: Contributed to object storage serving **1.5 PB+ of data**, optimized **Paxos / Gossip / LevelDB** based storage, and led an archival storage service from zero to launch.
- **I/O optimization**: Raised 4 KB file transfer throughput from **3–4 to 13,000+ files/s** on N100 / SSD / gigabit networking; custom raw-disk reading improved filesystem operations **5–6×** and backup audits **1.9–2.2×**.

### Community services & communications

- **Services built to last**: Delivered **private messaging, inbox services and activity feeds** that have operated reliably in production **for years**.
- **Live-streaming architecture**: Reworked services to reach **million-scale QPS on a single endpoint**, with **zero production incidents during the migration**.
- **Community platform from zero**: Led architecture and delivery of **10+ microservices in 3 months**, supporting **130+ applications** and reducing new-business launch cycles from **3 weeks to 1 week**.
- **Push infrastructure**: Unified **3 push systems** serving **100M+ daily PV**, with APNs delivery within **3 seconds at a 10M-user scale**. Raised delivery from **20% to 50% (+30 percentage points)** and reduced push costs from **CNY 1M to CNY 50K per month (-95%)**. Among the first in the industry to deliver **end-to-end business-funnel visibility and rapid fault isolation**, and **recall / replacement across all push channels**.
- **Push-driven engagement**: Raised **push-triggered app-launch UV / DAU from 11.8% to a peak of 15.38%**, keeping the ratio **at or above 13%**.

### Security & production infrastructure

- **Security platforms**: Built and maintained **anti-fraud, compliance-detection and real-time risk-control systems**; delivered account-system internationalization and regulatory compliance changes.
- **Core infrastructure ownership**: Maintained shared services, core libraries and storage infrastructure; supported **C10K connection handling**, monolith-to-microservice evolution, unit testing and CI/CD.
- **Availability & connectivity**: Optimized P2P / relay connectivity and hardened software distribution with multiple sources, dual-stack networking and DNS / IP failover.

### AI inference, native runtimes & model access

- **Native inference stack delivered**: Released [**Orca L0**](https://github.com/orca-zhang/Strata-A770/tree/main/orca-l0), a standalone MIT-licensed **Level Zero runtime and kernel compiler adapter**, integrated into **125B MoE inference on A770 16 GB + system RAM**. Host execution does not link SYCL, Unified Runtime or oneMKL.
- **671B model deployment**: Optimized ktransformers to run the complete **DeepSeek R1 671B** model at **28 tok/s, single request**; Q2_K_XL on dual EPYC 9275F, 1 TB RAM and one RTX 4090 48 GB.
- **Measured native backend gains**: Windows / A770 fixed short-code decode **41.42 → 50.54 tok/s (+22.01%)**, with matching complete outputs across 45 requests. In a separate controlled experiment, XMX two-expert prefill cut TTFT by **14.46% for Code2K / 9.36% for Long8K**. [Decode evidence](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/orca-anchor50-2026-10-31.md) · [Prefill evidence](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/orca-prefill-2026-10-31.md).
- **Deployment & embedding efficiency**: Trimmed the Intel SYCL inference distribution from **10.6 GB to 59 MB**. Distilled BGE-M3 into a **4-layer INT8 model, 2.27 GB → 150 MB**, with measured local embedding latency **200 → 20 ms/text**.
- **LLM protocol interoperability**: Delivered a gateway translating **4 client protocols into 4 upstream formats**, handling third-party relay differences in tool schemas, argument payloads, call IDs and streaming events.

## Selected work

### 📂 [filens](https://github.com/IceWhaleTech/filens)

A file-understanding layer shared by an Agent CLI and browser-local preview engines.

- **One conversion core, two hosts**: Rust / WASM processing shared by the native CLI and browser; parsing and rendering require **no file upload**.
- **Format-specific engineering**: Direct PPTX and modern iWork parsing, CAD / STEP geometry, RAW development and metadata-aware panorama handling.
- **Evidence for Agents**: Original passages, document structure, available OCR coordinates, nested-archive search and JSON / Markdown output.
- **Load by capability**: Format engines and workers load on demand; the standalone single-JS preview runtime is **2.83 MB Brotli**, including Vue, styles, workers and WASM. [Build measurements](https://github.com/IceWhaleTech/filens#pure-frontend-previews).

### 🧠 [Strata-A770](https://github.com/orca-zhang/Strata-A770)

Local inference for a **125B MoE model** on Intel Arc A770.

- **GPU and system memory**: **16 GB VRAM + system RAM** runs Qwen3.8-Flash-Next, keeping hot experts in VRAM.
- **Native inference**: Custom **Orca L0** Level Zero backend, with optimized expert caching, XMX compute and MTP speculative decoding.
- **Measured speedup**: Original SYCL → Orca L0 **41.42 → 50.54 tok/s (+22.01%)**, on a fixed short-code benchmark after warmup on Windows / A770. [Benchmark and conditions](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/orca-anchor50-2026-10-31.md).

### 🤖 [ZimaOS-Blue](https://github.com/IceWhaleTech/ZimaOS-Blue)

A local-first Go Agent runtime with **19 MB** idle memory. The design centers on **observable execution, controlled budgets and evidence before promotion**.

- **Make protocol compatibility operational**: Convert across **OpenAI Chat Completions, Responses, Anthropic Messages and Gemini**; normalize relay-specific tool schemas, empty arguments, call / result IDs and SSE events. Compatibility handling sits alongside provider verification, failover and circuit breakers. [Schema normalization](https://github.com/IceWhaleTech/ZimaOS-Blue/blob/HEAD/server/internal/toolschema/openai_compat.go).
- **Evaluate the whole execution path**: One candidate and a fixed baseline connect selector, execution, budget and cutover-readiness gates, keeping routing decisions and execution results comparable.
- **Native capabilities before model calls**: Route voice, OCR, PDF, document conversion and media work through local tools; use model reasoning where the workflow needs it.
- **Treat web access as stateful execution**: `HTTP → proxy extraction → browser` fallback, challenge detection, cookie / session reuse and multiple browser engines handle real-site failures.
- **Controlled skill evolution**: Failures and repeated grounded lessons produce candidate revisions; follow-up evaluation, human promotion and lineage-checked rollback govern adoption. [Harness and evolution](https://github.com/IceWhaleTech/ZimaOS-Blue/blob/HEAD/docs/guides/harness-evolution.mdx).

### ⚙️ ZimaOS-AI

An experimental Go control plane for local inference, developed alongside Blue.

- **Reusable engine integration**: Go SDK and service entry points, native backend bindings and hardware discovery provide a shared foundation for local model execution.
- **Evaluation tools already built**: Task-level Harness cases and runners for tool calling and grounded QA, alongside performance / quality comparisons for model and runtime candidates.
- **Roadmap**: Network-attached GPUs; Harness-guided dynamic quantization tuned to local hardware, memory and task-quality budgets; an AI BMC suite; transparent device sleep / wake orchestration.

### 🐋 [orcas](https://github.com/orcastor/orcas)

Lightweight content-addressable object storage with **client-side data processing and batching by default**. **Work in progress.**

- **End-to-end encryption**: User-controlled keys; the SDK encrypts each chunk before upload and decrypts it on read.
- **Compression that earns its cost**: Skip recognized compressed formats; test the first chunk and disable compression if it does not shrink. Compress before encrypting.
- **Staged content deduplication**: File size and header XXH3 filter candidates before full XXH3 / SHA-256 checks; content references enable instant uploads and reuse across versions.
- **Batching through the storage path**: Batch reference checks and metadata updates, deduplicate within an upload batch, pack small files and chunk large ones to reduce round trips and per-file I/O.

## Systems libraries & design decisions

### 💉 [yapi](https://github.com/ez8-co/yapi)

- **Bridge process and bitness boundaries**: A common calling interface across x86 / x64 / WOW64, including cross-bitness remote calls.
- **Local-style API, explicit ABI work**: Marshal multiple arguments and 64-bit results behind ordinary call syntax; header-only, with no helper DLL or external LIB.

### 🐞 [emock](https://github.com/ez8-co/emock)

- **Mock six function families with one macro**: Virtual, non-virtual, static, global, variadic and template functions, without adding mock interfaces to production classes.
- **Resolve overloads and patch safely**: Windows PDB symbol matching plus near-jump trampolines address overloaded methods and avoid long-jump overwrites of short x64 functions.

### 🔓 [unlocker](https://github.com/ez8-co/unlocker)

- **A handle and a mapped view are different owners**: Inspect both open handles and memory-mapped views to handle locks that survive closing a file handle, entirely in user mode.
- **Handle Windows edge cases**: Reserved / malformed names, trailing dots or spaces, UNC paths and cross-bitness operations; avoid scan stalls on blocking special handles.

### 💜 [influxdb-cpp](https://github.com/orca-zhang/influxdb-cpp)

- **Small client, complete transport path**: Header-only C++ query / write client with HTTP, UDP and batch writes, under **300 LOC**, using standard and system libraries.
- **One HTTP body parser**: A **Duff's-device-style state machine** shares body handling between Content-Length and chunked responses. [Implementation](https://github.com/orca-zhang/influxdb-cpp/blob/HEAD/influxdb.hpp).

### 🦄 [ecache](https://github.com/orca-zhang/ecache) / [ecache2](https://github.com/orca-zhang/ecache2)

- **Optimize the application's full path**: Store object pointers directly to avoid serialization; preallocated nodes, compact index-based links and slot reuse reduce allocation and GC pressure.
- **Cheap sharding**: Power-of-two buckets reduce lock contention and use bitmask selection. ecache2 adds generic keys: integers select shards directly; paired integer keys use XOR.
- **Keep expiry work predictable**: A shared **100 ms clock, calibrated every second**, avoids per-access clock calls; lazy expiry and slot reuse avoid periodic full-cache cleanup.
- **Protect the hot set**: `LRU-2` promotes reused entries to a separate queue so scans do not displace hot data. Optional Redis invalidation narrows stale-data windows. [Comparative benchmarks](https://benchplus.github.io/gocache/dev/bench/) cover throughput, allocations, GC pauses and hit rate.

### 🏎️ [borm](https://github.com/orca-zhang/borm) / [zorm](https://github.com/IceWhaleTech/zorm)

- **Performance comes from the data path**: `reflect2` data binding, SQL / metadata reuse and shape-aware call-site caches reduce repeated reflection, query construction and allocations.
- **Measured reuse optimization**: zorm's published reuse-path microbenchmark reports **10,320 → 1,200 ns/op (8.6×)** and **15 → 2 allocs/op** against its original implementation. [Benchmark details](https://github.com/IceWhaleTech/zorm#reuse-function-performance-optimization) · [ORM comparisons](https://github.com/benchplus/goorm).

### ✂️ [cad2x](https://github.com/orcastor/cad2x-converter)

- **Extract the CAD engine, trim the desktop stack**: Derived from LibreCAD; deeply trimmed QtCore / QtGui and removed QtWidgets, QtPrintSupport, GUI platform, OpenGL and Boost dependencies.
- **CAD conversion in ~2.9 MB**: DWG / DXF → DXF / PDF / PNG / SVG in a Linux ARM64 executable after `strip` + UPX, with font assets separate. Lazy TTF / TTC loading reuses system fonts.

### 🔬 [ezpp](https://github.com/ez8-co/ezpp)

- **Measure functions, blocks and object lifetimes**: Header-only C++ instrumentation with RAII scopes and atomic statistics, supporting recursion and multiple threads, with runtime print / save / clear controls.
- **An optimization workhorse**: Built for internal bottleneck diagnosis; now used in Strata-A770 to isolate verifier, MTP, expert execution and cache costs, guiding fusion and scheduling experiments. Gains are checked with profiling disabled. [Applied profiling](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/ezpp-decode2k-2026-10-26.md).

## Hardware projects & applied learning

- **AI BMC Lite — prototype design**: Designed a **42 × 40 mm, four-layer ESP32-S3 board** with **8 NTC inputs, 2 PWM outputs**, host power-button control and external GPU power synchronization. Delivered schematics, PCB, Gerbers, BOM and assembly documents; recorded native **ERC / DRC: 0**. Firmware, host-service integration and sample validation remain to be completed.
- **GPU power adapters — prototype artifacts**: Designed **5 EPS / PCIe / wire-input variants in a 100 × 100 mm, 15-board panel**, including an MI210 EPS turn adapter. Completed layout and export checks; connector fit and full-load thermal validation are pending.
- **SXM2 / NVLink — interconnect research**: Developed PCB layouts and routing tools for multi-GPU carrier / bridge designs. Applied pin-map cross-checking, differential-pair matching, impedance / stackup calculations and return-path analysis. Routing is ongoing; channel SI and physical link training are pending.
- **Hands-on GPU systems**: NVIDIA Tesla and AMD Instinct MI50 cooling, power adaptation and hardware modifications, followed through driver, runtime and inference-framework bring-up. These projects deepen my practical understanding of **power delivery, thermals, embedded control and high-speed interconnects**.

## More open source

| Project | Highlights |
| --- | --- |
| [idgen](https://github.com/orca-zhang/idgen) | Snowflake IDs; Redis / local fallback, NTP synchronization, rollback protection and JS-safe 53-bit IDs. |
| LRUCache · [Go](https://github.com/orca-zhang/lrucache) / [C++](https://github.com/ez8-co/linked_hash) / [JS](https://github.com/orca-zhang/cache.js) | Three implementations; the C++ version avoids copying through key overloading. |
| [xpjson](https://github.com/ez8-co/xpjson) | C++11 JSON library; about **1,500 LOC**, no external dependencies, TMP, SSO and COW. |

## Tech stack

`C++` · `Go` · `Python` · `Rust / WASM` · `TypeScript / JavaScript` · `Vue` · `Linux / Windows`

## Beyond code

<p align="center">
  <a href="./BeefWellington.jpeg">
    <img src="./BeefWellington.jpeg" alt="A Beef Wellington I learned to make in 2022" width="240" />
  </a>
</p>

A Beef Wellington I learned to make in 2022. Someday I'd like to open a small Wuxi snack shop, serving bubble wontons, steamed buns, magnolia cakes, hot and sour soup, and Suzhou-style noodles.

## Contact

For technical discussions and open-source collaboration, email [orca.zhang@yahoo.com](mailto:orca.zhang@yahoo.com).

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=orca-zhang&amp;hide=html&amp;layout=compact" alt="Most used languages" />
  <img src="https://github-readme-stats.vercel.app/api?username=orca-zhang&amp;count_private=true&amp;line_height=20" alt="GitHub statistics" />
</p>

<p align="center">
  <a href="https://ghfind.com/u/orca-zhang?ref=badge">
    <img src="https://ghfind.com/api/card/mini/orca-zhang?variant=radar" alt="GitHub Roast score card" />
  </a>
</p>
