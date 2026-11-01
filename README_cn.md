[English README | 英文说明](README.md)

> 我目前正在寻求新的机会，如有意向，可以与我取得联系：orca.zhang@yahoo.com

### 我的作品

<p align="center">
  <a href="https://github.com/orca-zhang/orca-zhang/blob/master/BeefWellington.jpeg">
    <img src="./BeefWellington.jpeg" width="20%" />
  </a>
</p>
  
> 这是2022年学做的惠灵顿牛排🥩（Beef Wellington），小愿望是能开一家无锡小吃店，卖泡泡小馄饨、小笼馒头、玉兰饼、酸辣汤、苏式面。

- 📂【[filens](https://github.com/IceWhaleTech/filens)】面向 AI Agent 的文件 CLI 与纯前端多格式预览引擎
  - 🤖 本地文件理解：读取、搜索、OCR、转换与关键原文提取，支持 JSON / Markdown 输出
  - 🖼️ 纯前端预览：Office / PDF / iWork、CAD / 3D、RAW 与全景媒体，**文件无需上传**
  - 🪶 轻量接入：原生 CLI **1.78–2.15 MiB**（不含 WASM / OCR 资源），支持 JS 单文件 / 分包与 Vue 组件
- 🧠【[Strata-A770](https://github.com/orca-zhang/Strata-A770)】在 Intel Arc A770 上运行 **125B MoE 模型**的本地推理引擎
  - 💾 **16 GB 显存 + 系统内存**运行 Qwen3.8-Flash-Next，热点专家驻留显存
  - ⚙️ 自研 **Orca L0** 原生 Level Zero 后端，优化专家缓存、XMX 计算与 MTP 推测解码
  - 🚀 Windows / A770 固定短代码预热后实测：原 SYCL → Orca L0 **41.42 → 50.54 tok/s（+22.01%）**
- 🤖 [ZimaOS-Blue](https://github.com/IceWhaleTech/ZimaOS-Blue) 面向 NAS / 边缘设备的本地优先纯 Go AI Agent 运行时
  - 🪶 无 Python / 容器依赖，闲时内存仅 **19 MB**，支持 Linux / macOS / Windows / ARM64
  - ⚡ 评估驱动开发：内置 Harness 回归 / 评估框架，每个 PR 通过回放 + 评分门禁
  - 🔍 Deep Research 与浏览器自动化：统一规划、并行检索与引用报告，浏览器采用 `HTTP → 代理提取 → 浏览器引擎` 三层回退
  - 🧩 技能与本地多模态：技能市场、GitHub 集成、CLI / 远程控制，支持 STT / TTS / OCR / PDF 与本地 Qwen3.5 离线推理
- 🐋【[orcas](https://github.com/orcastor/orcas)】轻量、高性能的内容寻址对象存储 **（开发中）**
  - 🔐 **端到端加密**：用户掌控密钥，客户端完成加解密
  - 🗜️ **智能压缩**：按文件类型选择压缩策略，避免重复压缩，先压缩再加密
  - ♻️ **基于内容的去重**：相同内容只存一份，支持秒传与多版本复用
  - ⚡ **默认批量处理**：小文件打包与元数据批量写入，减少 I/O 和数据库开销
- ❄️【[idgen](https://github.com/orca-zhang/idgen)】一款雪花算法发号器
  - 🚀 Redis / 本地内存降级，支持 NTP 同步、时钟回跳保护与 **JS 53 位精度安全**
- 🦄【[ecache](https://github.com/orca-zhang/ecache)】轻量本地内存缓存
  - 🤏 极简高性能：**不到 300 行**，**30 秒接入**，并发安全
  - 🌈 缓存策略：支持 `LRU` / `LRU-2`，可通过额外组件实现分布式一致性
- 🏎️【[borm](https://github.com/orca-zhang/borm)】更好用的orm库
  - 和写sql类似，几乎**无学习成本**，C++版一行搞定从db到pb/struct的数据load/store工作（暂未开源），golang版本使用reflect2，解决了**类型转换痛点**，性能**接近/略超原生**，应用于两家上市公司**生产环境无bug稳定运行多年**
- 🗂️【LRUCache（[go](https://github.com/orca-zhang/lrucache) / [c++](https://github.com/ez8-co/linked_hash) / [js](https://github.com/orca-zhang/cache.js)）】
  - 实现了三种语言的版本，leetcode都是 **超越100%** 的解法，C++版的key重载**巧妙地直接消除拷贝**，性能**强劲无敌**
- 🐞【[emock](https://github.com/ez8-co/emock)】**下一代mock库**
  - 对标Google的googlemock，跨平台支持mock所有函数（**全部6大类函数**），一个宏搞定一切，**唯一windows pdb文件重载**符号匹配算法，**类反射，API Hook**原理实现，市面上**唯一跳板安全**
- 🚀【[xpjson](https://github.com/ez8-co/xpjson)】迷你跨平台json库
  - 出生于13年，**C++11&模板元编程（TMP，类型萃取）技术实现，仅1500行，无外部依赖**，支持**SSO（小字符串优化）/COW（写时拷贝）**
- 💜【[influxdb](https://github.com/orca-zhang/influxdb-cpp)】github上**最受欢迎**的C和C++版客户端
  - **300行代码裸解**HTTP请求，**唯一无任何依赖**的库，巧妙使用**达夫设备**合并处理普通和chunked返回
- 💉【[yapi](https://github.com/ez8-co/yapi)】**全能进程注入器**
  - windows下消除**x86/x64/wow64**区别，**像编写本地程序一样**注入目标进程，并且不再需要dll支持
- 🔓【[unlocker](https://github.com/ez8-co/unlocker)】Ring3层（用户态，非驱动）文件解锁库
  - 可能是**全世界唯一**非暴力解畸形目录删除的方案（网上搜不到该方案），**唯一内存映射文件解锁方法**（handle和mapfile的关联关系有断层），支持跨x86/x64/wow64操作，支持快速跳过管道等可能导致卡死的特殊句柄
- 🔍【[ezpp](https://github.com/ez8-co/ezpp)】超好用的C++支持**在线剖析的代码级打点**性能剖析器
  - 唯一支持**递归和多线程**（对比Google gprofiler和Intel VTune），公司内部广泛应用，协助建立性能**优化功勋诸多次**
- 🔲【[jsqrcode](https://github.com/ez8-co/jsqrcode)】纯js版二维码解析库（zxing移植）
  - **多处bug修复**，添加支持**日文码表/汉字解码**（按需延迟加载），**大幅提高**解码成功率
- 🆙【[AutoUpdate](https://github.com/MFCer/AutoUpdate)】基于MFC实现的自动更新模块
  - **极简设计**（仅气泡交互），**多国语言**，**自更新**，**多种更新策略**，**多节点部署**，**全屏检测**，提供SDK**即插即用**

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=orca-zhang&hide=html&layout=compact)![Stats](https://github-readme-stats.vercel.app/api?username=orca-zhang&count_private=true&line_height=20)

[![GitHub Roast score card](https://ghfind.com/api/card/mini/orca-zhang?variant=radar)](https://ghfind.com/u/orca-zhang?ref=badge)
