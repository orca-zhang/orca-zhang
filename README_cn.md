<div align="center">

# Orca Zhang

**分布式系统 · 存储 · AI 基础设施**

15 年研发经验 · Tech Leader / Architect

[English](README.md) · [邮箱](mailto:orca.zhang@yahoo.com)

</div>

设计、研发并长期维护分布式存储、企业数据保护、社区服务与 AI 推理基础设施。能够快速进入新领域，从核心实现一路推进到上线及长期运维，专注**性能、高可用与成本优化**。

## 工程履历与成果

### 分布式存储与企业数据保护

- **备份与容灾**：优化核心存储引擎，推动商用备份容灾系统**整体性能提升 100%**，达到**世界领先水平**。
- **企业级网盘**：主导核心引擎研发，支撑基于**第四代分布式文件系统**构建的企业级网盘；其厂商**连续 8 年获得 Gartner 上榜认可**，为该类别**亚太地区唯一上榜厂商**。
- **分布式对象存储**：参与承载 **1.5 PB+ 数据**的对象存储研发，优化基于 **Paxos / Gossip / LevelDB** 的存储系统，并主导归档存储服务从零到上线。
- **I/O 链路优化**：在 N100 / SSD / 千兆网络环境，将 4 KB 小文件传输从 **3–4 提升至 13,000+ files/s**；通过自研裸磁盘读取库，使文件系统操作提升 **5–6 倍**、备份审计提升 **1.9–2.2 倍**。

### 社区服务与通信平台

- **经长期运行验证的服务**：交付**私信、站内信、动态等社区服务**，上线后**稳定运行多年**。
- **直播服务架构**：完成服务改造，单接口达到**百万级 QPS**，改造期间 **0 线上事故**。
- **社区中台从零交付**：主导架构设计与研发，**3 个月交付 10+ 微服务**，支撑 **130+ 应用**接入，新业务上线周期从 **3 周缩短到 1 周**。
- **推送基础设施**：整合 **3 套推送系统**，支撑**日 PV 上亿**，千万级用户 APNs 推送 **3 秒内送达**。送达率从 **20% 提升至 50%（+30 个百分点）**，每月推送成本从**人民币 100 万元降至 5 万元（降低 95%）**。业内率先落地**完整业务漏斗与快速排查定位系统**，并率先支持**全渠道推送撤销与覆盖**。

### 安全与生产基础架构

- **安全平台**：研发维护**反作弊、合规检测与实时风控系统**，完成账户体系国际化及合规改造。
- **基础架构长期维护**：维护公共服务、核心基础库与存储基础设施，覆盖 **C10K 连接处理**、单体向微服务演进、单元测试与 CI/CD。
- **可用性与连接质量**：优化 P2P / 中继网络连接，通过多源、双栈、DNS / IP 故障切换增强分发链路可用性。

### AI 推理、原生运行时与模型接入

- **交付原生推理栈**：开源 [**Orca L0**](https://github.com/orca-zhang/Strata-A770/tree/main/orca-l0)，交付可独立构建、MIT 授权的 **Level Zero 运行时与内核编译适配器**，接入 **A770 16 GB 显存 + 系统内存上的 125B MoE 推理**；宿主执行不链接 SYCL、Unified Runtime 或 oneMKL。
- **671B 完整模型部署**：优化 ktransformers，**DeepSeek R1 671B 完整模型单请求 decode 达 28 tok/s**；Q2_K_XL，双路 EPYC 9275F、1 TB 内存与单张 RTX 4090 48 GB。
- **有实测依据的原生后端收益**：Windows / A770 固定短代码 decode 从 **41.42 提升至 50.54 tok/s（+22.01%）**，45 次请求的完整输出一致；另一次独立对照中，XMX 双专家 prefill 使 **Code2K / Long8K 的 TTFT 分别降低 14.46% / 9.36%**。[Decode 记录](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/orca-anchor50-2026-10-31.md) · [Prefill 记录](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/orca-prefill-2026-10-31.md)。
- **交付体积与 Embedding 效率**：将 Intel SYCL 推理分发包从 **10.6 GB 精简至 59 MB**；将 BGE-M3 蒸馏为 **4 层 INT8，体积 2.27 GB → 150 MB**，本地 Embedding 实测延迟 **200 → 20 ms/text**。
- **LLM 协议互通**：实现 **4 种入口 × 4 种上游协议转换**，兼容第三方中转站在工具 schema、参数载荷、调用 ID 与流式事件上的差异。

## 精选作品

### 📂 [filens](https://github.com/IceWhaleTech/filens)

连接 Agent CLI 与浏览器本地预览的文件理解层。

- **同一转换核心，两个运行宿主**：原生 CLI 与浏览器复用 Rust / WASM 处理能力，解析与渲染**无需上传文件**。
- **深入文件格式本身**：直接解析 PPTX 与现代 iWork，分别处理 CAD / STEP 几何、RAW 显影与依赖元数据的全景内容。
- **给 Agent 提供证据**：输出原文片段、文档结构、可用的 OCR 坐标、嵌套压缩包搜索结果及 JSON / Markdown。
- **按能力加载**：格式引擎与 Worker 按需加载；独立单 JS 预览运行时 **Brotli 后 2.83 MB**，包含 Vue、样式、Worker 与 WASM。[构建体积记录](https://github.com/IceWhaleTech/filens#pure-frontend-previews)。

### 🧠 [Strata-A770](https://github.com/orca-zhang/Strata-A770)

在 Intel Arc A770 上运行 **125B MoE 模型**的本地推理引擎。

- **显存与内存协作**：**16 GB 显存 + 系统内存**运行 Qwen3.8-Flash-Next，热点专家驻留显存。
- **原生推理后端**：自研 **Orca L0** Level Zero 后端，优化专家缓存、XMX 计算与 MTP 推测解码。
- **实测性能提升**：Windows / A770 固定短代码预热后，原 SYCL → Orca L0 **41.42 → 50.54 tok/s（+22.01%）**。[测试条件与记录](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/orca-anchor50-2026-10-31.md)。

### 🤖 [ZimaOS-Blue](https://github.com/IceWhaleTech/ZimaOS-Blue)

本地优先的 Go Agent 运行时，闲时内存 **19 MB**。核心思路是**执行可观测、预算可控制、变更有证据**。

- **把协议兼容做成可用能力**：打通 **OpenAI Chat Completions、Responses、Anthropic Messages 与 Gemini**，处理不同中转站的工具 schema、空参数、调用 / 结果 ID 和 SSE 事件差异，并与供应商验证、故障切换及熔断协同。[Schema 归一化实现](https://github.com/IceWhaleTech/ZimaOS-Blue/blob/HEAD/server/internal/toolschema/openai_compat.go)。
- **评估覆盖完整执行链路**：同一候选与固定基线贯穿 selector、execution、budget、cutover-readiness 门禁，让路由决策和执行结果可以比较。
- **原生能力优先于模型调用**：语音、OCR、PDF、文档转换与媒体任务优先走本地工具，在工作流真正需要时使用模型推理。
- **把网页访问当作有状态执行**：以 `HTTP → 代理提取 → 浏览器` 回退，结合挑战识别、Cookie / 会话复用和多浏览器引擎，处理真实站点的失败场景。
- **受控的技能演进**：失败与反复验证的经验生成候选修订，经后续评估、人工采纳及带谱系校验的回滚机制控制变更。[Harness 与演进设计](https://github.com/IceWhaleTech/ZimaOS-Blue/blob/HEAD/docs/guides/harness-evolution.mdx)。

### ⚙️ ZimaOS-AI

与 Blue 协同探索的本地推理 Go 控制面，处于实验分支阶段。

- **可复用的引擎接入**：Go SDK 与服务入口、原生后端绑定及硬件发现，为本地模型执行提供统一基础。
- **已落地的评测工具**：工具调用与基于上下文的知识问答 Harness 用例、执行器，以及模型 / 运行时候选的性能与质量对照。
- **后续规划**：网络 GPU；基于 Harness、结合本地硬件、内存与任务质量预算的动态量化；AI BMC 套件；设备无感休眠与唤醒编排。

### 🐋 [orcas](https://github.com/orcastor/orcas)

围绕**客户端数据处理与默认批量操作**设计的轻量内容寻址对象存储。**开发中。**

- **端到端加密**：用户掌控密钥，SDK 在上传前逐块加密，读取时在客户端解密。
- **压缩要有实际收益**：跳过已识别的压缩格式，首块试压无收益便关闭压缩；先压缩，再加密。
- **分阶段内容去重**：先按文件大小与头部 XXH3 筛选，再以全量 XXH3 / SHA-256 校验；通过内容引用实现秒传与多版本复用。
- **批量贯穿存储链路**：批量查重与元数据更新，识别同一上传批次内的重复内容，小文件打包、大文件分块，减少往返与逐文件 I/O 开销。

## 底层工具与关键设计

### 💉 [yapi](https://github.com/ez8-co/yapi)

- **跨越进程与位宽边界**：用统一调用接口处理 x86 / x64 / WOW64，包括跨位宽的远程调用。
- **接口像本地调用，底层处理 ABI**：封装多参数传递与 64 位返回值，保持普通函数调用语法；单头文件，无需辅助 DLL 或外部 LIB。

### 🐞 [emock](https://github.com/ez8-co/emock)

- **一个宏覆盖六类函数**：虚函数、普通成员、静态、全局、变参及模板函数，无需为生产类添加 Mock 接口。
- **重载匹配与跳转安全**：结合 Windows PDB 符号匹配和近跳转 / 跳板，处理重载成员函数，避免 x64 长跳转覆盖短函数。

### 🔓 [unlocker](https://github.com/ez8-co/unlocker)

- **文件句柄与映射视图是两种占用**：分别检查打开的句柄与内存映射视图，处理关闭文件句柄后仍然存在的锁定，全程工作在用户态。
- **覆盖 Windows 边界情况**：保留名 / 畸形文件名、尾部点或空格、UNC 路径及跨位宽操作；避免特殊阻塞句柄拖住扫描。

### 💜 [influxdb-cpp](https://github.com/orca-zhang/influxdb-cpp)

- **小体积，完整传输链路**：单头文件 C++ 查询 / 写入客户端，支持 HTTP、UDP 和批量写入，**不到 300 行**，仅使用标准库与系统库。
- **一套 HTTP 响应解析路径**：通过 **Duff's device 风格的状态机**复用 Content-Length 与 chunked 响应的正文处理逻辑。[实现源码](https://github.com/orca-zhang/influxdb-cpp/blob/HEAD/influxdb.hpp)。

### 🦄 [ecache](https://github.com/orca-zhang/ecache) / [ecache2](https://github.com/orca-zhang/ecache2)

- **优化应用的完整路径**：直接存对象指针，省掉序列化；预分配节点、紧凑索引链表与槽位复用，降低分配及 GC 压力。
- **低开销分片**：2 的幂次分桶分散锁竞争，以位掩码选桶；ecache2 支持泛型 key，整数直接选桶，双整数 key 通过异或选桶。
- **让过期处理开销可控**：共享 **100 ms 精度、每秒校准的时钟**，避免每次访问读取系统时间；惰性过期与槽位复用，省去定时全量清理。
- **保护热点命中率**：`LRU-2` 将重复访问的条目晋升至独立队列，避免遍历请求冲掉热数据；可选 Redis 失效同步缩小不一致窗口。[对比基准](https://benchplus.github.io/gocache/dev/bench/)覆盖吞吐、分配、GC 停顿与命中率。

### 🏎️ [borm](https://github.com/orca-zhang/borm) / [zorm](https://github.com/IceWhaleTech/zorm)

- **性能来自数据路径**：通过 `reflect2` 数据绑定、SQL / 元数据复用、按调用点和数据形状缓存，减少重复反射、SQL 构建与分配。
- **有明确基线的复用优化**：zorm 已发布的复用路径微基准，相比原实现从 **10,320 降至 1,200 ns/op（8.6 倍）**，分配从 **15 降至 2 allocs/op**。[基准细节](https://github.com/IceWhaleTech/zorm#reuse-function-performance-optimization) · [ORM 横向对比](https://github.com/benchplus/goorm)。

### ✂️ [cad2x](https://github.com/orcastor/cad2x-converter)

- **提取 CAD 引擎，裁掉桌面框架**：衍生自 LibreCAD，深度裁剪 QtCore / QtGui，移除 QtWidgets、QtPrintSupport、GUI 平台、OpenGL 与 Boost 依赖。
- **约 2.9 MB 完成 CAD 转换**：DWG / DXF → DXF / PDF / PNG / SVG；Linux ARM64 可执行文件经 `strip` + UPX 后约 2.9 MB，字体资源另计。按需加载 TTF / TTC，复用系统字体。

### 🔬 [ezpp](https://github.com/ez8-co/ezpp)

- **量到函数、代码块与对象生命周期**：单头文件 C++ 剖析器，通过 RAII 作用域埋点与原子统计支持递归和多线程，可在运行时打印、保存和清空统计。
- **持续用于实战的优化工具**：为内部瓶颈定位而开发，现用于 Strata-A770 的 verifier、MTP、专家执行与缓存耗时分析，指导融合与调度实验；性能收益通过关闭剖析后的复测确认。[实际剖析记录](https://github.com/orca-zhang/Strata-A770/blob/main/bench/results/a770/ezpp-decode2k-2026-10-26.md)。

## 硬件产出与实践学习

- **AI BMC Lite：样板设计**：完成 **42 × 40 mm、四层 ESP32-S3 控制板**设计，覆盖 **8 路 NTC、2 路 PWM**、主机电源键及外置 GPU 电源同步；交付原理图、PCB、Gerber、BOM 与装配文档，原生 **ERC / DRC 记录均为 0**。固件、主机服务联调与样板实测待完成。
- **GPU 供电转接板：原型工程**：设计 **5 类 EPS / PCIe / 线缆输入转接板，15 块拼入 100 × 100 mm 面板**，包含 MI210 EPS 转向板；完成布局与导出检查，连接器装配和满载温升仍待实测。
- **SXM2 / NVLink：互连研究**：推进多 GPU 载板 / 桥接板布局与布线工具，实践引脚映射交叉核对、差分等长、阻抗 / 叠层计算与回流路径分析；布线继续推进，通道 SI 与实卡链路训练待验证。
- **算力硬件实机实践**：围绕 NVIDIA Tesla、AMD Instinct MI50 等算力卡开展风冷 / 水冷、供电适配及硬件改装，贯通驱动、运行库与推理框架部署排障；持续积累**供电、热设计、嵌入式控制与高速互连**经验。

## 更多开源项目

| 项目 | 核心能力 |
| --- | --- |
| [idgen](https://github.com/orca-zhang/idgen) | 雪花算法发号器；Redis / 本地内存降级、NTP 同步、回跳保护与 JS 53 位精度安全。 |
| LRUCache · [Go](https://github.com/orca-zhang/lrucache) / [C++](https://github.com/ez8-co/linked_hash) / [JS](https://github.com/orca-zhang/cache.js) | 三种语言实现，C++ 通过 key 重载避免拷贝。 |
| [xpjson](https://github.com/ez8-co/xpjson) | C++ JSON 库，约 **1,500 行**、无外部依赖，基于 C++11 / TMP，支持 SSO / COW。 |

## 技术栈

`C++` · `Go` · `Python` · `Rust / WASM` · `TypeScript / JavaScript` · `Vue` · `Linux / Windows`

## 代码之外

<p align="center">
  <a href="./BeefWellington.jpeg">
    <img src="./BeefWellington.jpeg" alt="2022 年学做的惠灵顿牛排" width="240" />
  </a>
</p>

这是 2022 年学做的惠灵顿牛排。小愿望是开一家无锡小吃店，卖泡泡小馄饨、小笼馒头、玉兰饼、酸辣汤、苏式面。

## 联系

欢迎技术交流与开源合作：[orca.zhang@yahoo.com](mailto:orca.zhang@yahoo.com)。

<p align="right"><sub>正在寻找新的工程机会 · <a href="mailto:orca.zhang@yahoo.com">联系我</a></sub></p>
