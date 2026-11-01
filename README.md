[Simplified Chinese README | 简体中文说明](README_cn.md)

> Open to new opportunities. Reach me at orca.zhang@yahoo.com.

### My Masterpieces

<p align="center">
  <a href="https://github.com/orca-zhang/orca-zhang/blob/master/BeefWellington.jpeg">
    <img src="./BeefWellington.jpeg" width="20%" />
  </a>
</p>

> This is a Beef Wellington I learned to make in 2022. My small dream is to open a Wuxi snack shop, selling bubble wontons, small steamed buns, magnolia cakes, hot and sour soup, and Suzhou-style noodles.

- 📂\[[filens](https://github.com/IceWhaleTech/filens)\] File CLI for AI Agents and pure frontend multi-format preview engine
  - 🤖 Local file understanding: Reading, search, OCR, conversion and key passage extraction, with JSON / Markdown output
  - 🖼️ Browser previews: Office / PDF / iWork, CAD / 3D, RAW and panoramic media, with **no file uploads**
  - 🪶 Lightweight integration: Native CLI **1.78–2.15 MiB** (excluding WASM / OCR assets), standalone single-file / split JS builds and Vue components
- 🧠\[[Strata-A770](https://github.com/orca-zhang/Strata-A770)\] Local inference engine for running a **125B MoE model** on Intel Arc A770
  - 💾 **16 GB VRAM + system RAM** runs Qwen3.8-Flash-Next, keeping hot experts in VRAM
  - ⚙️ Custom **Orca L0** native Level Zero backend, with optimized expert caching, XMX compute and MTP speculative decoding
  - 🚀 Windows / A770 fixed short-code benchmark after warmup: original SYCL → Orca L0 **41.42 → 50.54 tok/s (+22.01%)**
- 🤖 [ZimaOS-Blue](https://github.com/IceWhaleTech/ZimaOS-Blue) Local-first pure-Go AI Agent Runtime for NAS / edge devices
  - 🪶 No Python/container dependency, only **19 MB** idle memory; supports Linux / macOS / Windows / ARM64
  - ⚡ Evaluation-driven development: Built-in Harness regression/evaluation framework, with replay + scoring gates for every PR
  - 🔍 Deep Research and browser automation: Planning, parallel retrieval and cited reports; three-layer fallback (`HTTP → proxy extraction → browser engine`)
  - 🧩 Skills and local multimodal processing: Skill marketplace, GitHub integration and CLI/remote control; STT / TTS / OCR / PDF and offline Qwen3.5 inference
- 🐋\[[orcas](https://github.com/orcastor/orcas)\] Lightweight, high-performance content-addressable object storage **(WIP)**
  - 🔐 **End-to-end encryption**: User-controlled keys, with encryption and decryption on the client
  - 🗜️ **Smart compression**: Select compression by file type, avoid recompressing compressed data, then encrypt
  - ♻️ **Content-based deduplication**: Store identical content once, with instant uploads and reuse across versions
  - ⚡ **Batching by default**: Pack small files and batch metadata writes to reduce I/O and database overhead
- ❄️\[[idgen](https://github.com/orca-zhang/idgen)\] A snowflake algorithm ID generator
  - 🚀 Redis or local memory with fallback, NTP synchronization, clock rollback protection and **JS-safe 53-bit IDs**
- 🦄\[[ecache](https://github.com/orca-zhang/ecache)\] Lightweight local memory cache
  - 🤏 Minimal and fast: **Under 300 LOC**, **30-second integration**, concurrency safe
  - 🌈 Cache policies: `LRU` / `LRU-2`, with distributed consistency through optional components
- 🏎️\[[borm](https://github.com/orca-zhang/borm)\] A better ORM library
  - Similar to writing SQL, almost **no learning overhead**. The C++ version (not yet open-sourced) can handle data load/store from db to pb/struct in one line . The Go version uses reflect2 to solve **type conversion pain points**, with performance **close to or slightly better than native**, and has been used in production environments of two listed companies **without bugs** for many years.
- 🗂️\[LRUCache（[go](https://github.com/orca-zhang/lrucache) / [c++](https://github.com/ez8-co/linked_hash) / [js](https://github.com/orca-zhang/cache.js))\]
  - Implementations in three languages, all **beats 100%** in leetcode. The C++ version **cleverly avoid copying** by overloading the `key`, with **powerful** performance.
- 🐞\[[emock](https://github.com/ez8-co/emock)\] **Next-generation mock library**
  - Comparable to Google's googlemock, cross-platform support for mocking all functions (all **6 kinds of functions**), with one macro handling everything. **Unique solution of windows pdb file overload** symbol matching algorithm, **reflection-like, API Hook** principle implementation, and the only one **trampoline safe** on the Internet.
- 🚀\[[xpjson](https://github.com/ez8-co/xpjson)\] Mini cross-platform json library
  - Born in 2013, implemented with **C++11 & template metaprogramming (TMP, type extraction)** techniques, **only 1500 lines**, **no external dependencies**, support **SSO (Small String Optimization)/COW (Copy On Write)**
- 💜\[[influxdb](https://github.com/orca-zhang/influxdb-cpp)\] The **most popular** C and C++ client on GitHub
  - **Less than 300 LOC to decode** HTTP requests, with **no dependencies**, cleverly using **Duff's device** to merge processing ordinary and chunked returns
- 💉\[[yapi](https://github.com/ez8-co/yapi)\] **yet another process injector**
  - Eliminate the difference between **x86/x64/wow64** under Windows, injects the target process just **like writing a local program**, and no longer requires dll support
- 🔓\[[unlocker](https://github.com/ez8-co/unlocker)\] Ring3 layer (user mode, non-driver) file unlocking library
  - Possibly the **unique non-violent** solution in the world to unlock malformed directory deletion (this solution cannot be found on the Internet), the **unique memory-mapped file unlocking method** (the association between handle and mapfile has a fault line), supports cross-x86/x64/wow64 operations, supports skipping pipelines and other special handles that may cause deadlock
- 🔍\[[ezpp](https://github.com/ez8-co/ezpp)\] A very easy-to-use C++ **code-level performance profiler** with **online profiling**
  - The only one to support **recursion and multithreading** (compared to Google gprofiler and Intel VTune), widely used internally by the company, and has **resulted in performance optimization contributions many times**
- 🔲\[[jsqrcode](https://github.com/ez8-co/jsqrcode)\] Pure JS version QR code parsing library (zxing port)
  - **Several bugs fixed**, added support for **Japanese code table/Chinese character decoding** (loaded on demand), **greatly improved** decoding success rate
- 🆙\[[AutoUpdate](https://github.com/MFCer/AutoUpdate)\] Automatic update module implemented based on MFC
  - **Minimalist design** (only bubble interaction), **multilingual support**, **self-update**, **multiple update strategies**, **multi-node deployment**, **full-screen detection**, and provided SDK **plug-and-play**

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=orca-zhang&hide=html&layout=compact)![Stats](https://github-readme-stats.vercel.app/api?username=orca-zhang&count_private=true&line_height=20)

[![GitHub Roast score card](https://ghfind.com/api/card/mini/orca-zhang?variant=radar)](https://ghfind.com/u/orca-zhang?ref=badge)
