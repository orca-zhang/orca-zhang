### 我的作品


<p align="center">
  <a href="https://github.com/orca-zhang/orca-zhang/blob/master/BeefWellington.jpeg">
    <img src="./BeefWellington.jpeg" width="20%" />
  </a>
</p>
  
> 这是2022年学做的惠灵顿牛排🥩（Beef Wellington），小愿望是能开一家无锡小吃店，卖泡泡小馄饨、小笼馒头、玉兰饼、酸辣汤、苏式面。

> This is a Beef Wellington I learned to make in 2022. My small dream is to open a Wuxi snack shop, selling bubble wontons, small steamed buns, yulan cakes, hot and sour soup, and Suzhou-style noodles.

- 🐋【[orcas](https://github.com/orcastor)】更聪明、更现代的轻量级NAS解决方案🗄️ **（开发中）** Lightweight NAS solution that is smarter and more modern.🗄️ (WIP)
  - 💸 低成本：自制热插拔背板成本低至25%，超高性能准系统仅￥745.6（无盘），3\~18TB垂直存储仅￥1225.6\~3115.6
  - 💸 Low cost: Homemade hot-swappable backplane costs as low as 25%, ultra-high-performance quasi-system only ¥745.6 (without disk), 318TB vertical storage only ¥1225.6\~3115.6
  - 🚧 跨平台：支持Win、Linux、MacOSX等主流操作系统以及廉价低功耗🔋（6块盘仅30W）设备（RPi / ARM64）
  - 🚧 Cross-platform: Supports Win, Linux, MacOSX and other mainstream operating systems as well as low-cost, low-power consumption devices (RPi / ARM64) with only 30W for 6 disks
  - 📚 存储引擎可替换：默认sqlcipher + 自研存储
  - 📚 Replaceable storage engine: Default sqlcipher + self-developed storage
  - 📤 支持多种访问协议：http1.1/http2.0/http3.0/nfs/smb
  - 📤 Supports multiple access protocols: http1.1/http2.0/http3.0/nfs/smb
- ❄️【[idgen](https://github.com/orca-zhang/idgen) 】一款雪花算法发号器 A snowflake algorithm ID generator
  - 🚀 支持基于redis或本地内存（失败降级）
  - 🚀 Supports redis-based or local memory (fallback on failure)
  - ⌚ ntp同步和时钟回跳安全（默认1分钟）
  - ⌚ NTP synchronization and secure clock rollback (default 1 minute)
  - 🦖 js精度安全（不超过53位安全范围）
  - 🦖 JS precision security (not exceeding 53 bits)
- 🦄【[ecache](https://github.com/orca-zhang/ecache) 】轻量本地内存缓存 Lightweight local memory cache
  - 🤏 代码量<300行、30s完成接入
  - 🤏 Less than 300 lines of code, ready to be integrated in 30s
  - 🚀 高性能、极简设计、并发安全
  - 🚀 High performance, minimalist design, concurrency safe
  - 🌈 支持`LRU` 和 `LRU-2`两种模式
  - 🌈 Supports `LRU` and `LRU-2` modes
  - 🦖 额外小组件支持分布式一致性
  - 🦖 Additional components support distributed consistency
- 🏎️【[borm](https://github.com/orca-zhang/borm)】更好用的orm库 A better ORM library
  - 和写sql类似，几乎**无学习成本**，C++版一行搞定从db到pb/struct的数据load/store工作（暂未开源），golang版本使用reflect2，解决了**类型转换痛点**，性能**接近/略超原生**，应用于两家上市公司**生产环境无bug稳定运行多年**
  - Similar to writing SQL, almost **no learning cost**. The C++ version can handle data load/store from db to pb/struct in one line (not yet open-sourced). The Go version uses reflect2 to solve **type conversion pain points**, with performance **close to or slightly better than native**, and has been used in production environments of two listed companies **without bugs** for many years.
- 🗂️【LRUCache（[go](https://github.com/orca-zhang/lrucache) / [c++](https://github.com/ez8-co/linked_hash) / [js](https://github.com/orca-zhang/cache.js)）】
  - 实现了三种语言的版本，leetcode都是 **超越100%** 的解法，C++版的key重载**巧妙地直接消除拷贝**，性能**强劲无敌**
  - Implementations in three languages, all **exceeding 100%** in leetcode. The C++ version **cleverly eliminates copying** by overloading the key, with **powerful** performance.
- 🐞【[emock](https://github.com/ez8-co/emock)】**下一代mock库** **Next-generation mock library**
  - 对标Google的googlemock，跨平台支持mock所有函数（**全部6大类函数**），一个宏搞定一切，**唯一windows pdb文件重载**符号匹配算法，**类反射，API Hook**原理实现，市面上**唯一跳板安全**
  - Comparable to Google's googlemock, cross-platform support for mocking all functions (all **6 kinds of functions**), with one macro handling everything. **Unique solution of windows pdb file overload** symbol matching algorithm, **reflection-like, API Hook** principle implementation, and the only one **trampoline-safe** on the Internet.
- 🚀【[xpjson](https://github.com/ez8-co/xpjson)】迷你跨平台json库 Mini cross-platform json library
  - 出生于13年，**C++11&模板元编程（TMP，类型萃取）技术实现，仅1500行，无外部依赖**，支持**SSO（小字符串优化）/COW（写时拷贝）**
  - Born in '13, implemented with **C++11 & template metaprogramming (TMP, type extraction)** techniques, **only 1500 lines**, **no external dependencies**, supporting **SSO (Small String Optimization)/COW (Copy On Write)**
- 💜【[influxdb](https://github.com/orca-zhang/influxdb-cpp)】github上**最受欢迎**的C和C++版客户端 The **most popular** C and C++ client on GitHub
  - **300行代码裸解**HTTP请求，**唯一无任何依赖**的库，巧妙使用**达夫设备**合并处理普通和chunked返回
  - **300 lines of code to bare decode** HTTP requests, the **only** library with **no dependencies**, cleverly using **Duff's device** to merge processing ordinary and chunked returns
- 💉【[yapi](https://github.com/ez8-co/yapi)】**全能进程注入器** **Universal process injector**
  - windows下消除**x86/x64/wow64**区别，**像编写本地程序一样**注入目标进程，并且不再需要dll支持
  - Reduce the difference between **x86/x64/wow64** under Windows, injects the target process just **like writing a local program**, and no longer requires dll support
- 🔓【[unlocker](https://github.com/ez8-co/unlocker)】Ring3层（用户态，非驱动）文件解锁库 Ring3 layer (user mode, non-driver) file unlocking library
  - 可能是**全世界唯一**非暴力解畸形目录删除的方案（网上搜不到该方案），**唯一内存映射文件解锁方法**（handle和mapfile的关联关系有断层），支持跨x86/x64/wow64操作，支持快速跳过管道等可能导致卡死的特殊句柄
  - Possibly the **unique non-violent** solution in the world to unlock malformed directory deletion (this solution cannot be found on the Internet), the **unique memory-mapped file unlocking method** (the association between handle and mapfile has a fault line), supports cross-x86/x64/wow64 operations, supports skipping pipelines and other special handles that may cause deadlock
- 🔍【[ezpp](https://github.com/ez8-co/ezpp)】超好用的C++支持**在线剖析的代码级打点**性能剖析器 A very easy-to-use C++ **code-level profiler** with **online profiling**
  - 唯一支持**递归和多线程**（对比Google gprofiler和Intel VTune），公司内部广泛应用，协助建立性能**优化功勋诸多次**
  - The only one to support **recursion and multithreading** (compared to Google gprofiler and Intel VTune), widely used internally by the company, and has **contributed to performance optimization many times**
- 🔲【[jsqrcode](https://github.com/ez8-co/jsqrcode)】纯js版二维码解析库（zxing移植） Pure JS version QR code parsing library (zxing port)
  - **多处bug修复**，添加支持**日文码表/汉字解码**（按需延迟加载），**大幅提高**解码成功率
  - **Multiple bugs fixed**, added support for **Japanese code table/Chinese character decoding** (loaded on demand), **greatly improved** decoding success rate
- 🆙【[AutoUpdate](https://github.com/MFCer/AutoUpdate)】基于MFC实现的自动更新模块 Automatic update module implemented based on MFC
  - **极简设计**（仅气泡交互），**多国语言**，**自更新**，**多种更新策略**，**多节点部署**，**全屏检测**，提供SDK**即插即用**
  - **Minimalist design** (only bubble interaction), **multilingual support**, **self-update**, **multiple update strategies**, **multi-node deployment**, **full-screen detection**, and provided SDK **plug-and-play**

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=orca-zhang&hide=html&layout=compact)![Stats](https://github-readme-stats.vercel.app/api?username=orca-zhang&count_private=true&line_height=20)
