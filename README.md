# Awsome-RAG-LLM-Inference-System
RAG-based LLM inference: a survey about systematic designs

## 1. GPU Accelerate
* [RAGO: Systematic Performance Optimization for Retrieval-Augmented Generation Serving](https://arxiv.org/abs/2503.14649), ISCA 2025
* [Hermes: Algorithm-System Co-design for Efficient Retrieval Augmented Generation At Scale](https://michaeltshen.github.io/Files/Hermes.pdf), ISCA 2025
* [Fast Vector Query Processing for Large Datasets Beyond GPU Memory with Reordered Pipelining](https://xinjin.github.io/files/NSDI24_Rummy.pdf), NSDI 2024
* [CAGRA: Highly Parallel Graph Construction and Approximate Nearest Neighbor Search for GPUs](https://arxiv.org/pdf/2308.15136), ICDE 2024
* [Towards High-throughput and Low-latency Billion-scale Vector Search via CPU/GPU Collaborative Filtering and Re-ranking](https://www.usenix.org/system/files/fast25-tian-bing.pdf), FAST 2025
* [GGNN: Graph-Based GPU Nearest Neighbor Search](https://ieeexplore.ieee.org/document/9739943/), TBD 2023
* [An Adaptive Vector Index Partitioning Scheme for Low-Latency RAG Pipeline](https://arxiv.org/pdf/2504.08930), Arxiv 2025
* [BANG: Billion-Scale Approximate Nearest Neighbor Search using a Single GPU](https://arxiv.org/pdf/2401.11324v1), Arxiv 2025 #
* [PilotANN: Memory-Bounded GPU Acceleration for Vector Search](https://arxiv.org/pdf/2503.21206), Arxiv 2025
* [VecFlow: A High-Performance Vector Data Management System for Filtered-Search on GPUs](https://arxiv.org/pdf/2506.00812), SIGMOD 2026


## 2. Data Reuse and Pipeline Parallelism
### 2.1 Data Reuse
* [Cache-Craft: Managing Chunk-Caches for Efficient Retrieval-Augmented Generation](https://arxiv.org/pdf/2502.15734v1), SIGMOD 2025
* [CacheBlend: Fast Large Language Model Serving for RAG with Cached Knowledge Fusion](https://arxiv.org/abs/2405.16444), Eurosys 2025 (Best Paper)
* [Leveraging Approximate Caching for Faster Retrieval-Augmented Generation](https://arxiv.org/pdf/2503.05530), EuroMLSys 2025
* [SPFresh: Incremental In-Place Update for Billion-Scale Vector Search](https://dl.acm.org/doi/abs/10.1145/3600006.3613166), SOSP 2023
* [Revisiting the Index Construction of Proximity Graph-Based Approximate Nearest Neighbor Search](https://arxiv.org/pdf/2410.01231), VLDB 2025
* [EdgeRAG: Online-Indexed RAG for Edge Devices](https://arxiv.org/pdf/2412.21023), Arxiv 2024
### 2.2 Pipeline Parallelism
* [PipeRAG: Fast Retrieval-Augmented Generation via Adaptive Pipeline Parallelism](https://arxiv.org/pdf/2403.05676), KDD 2025 #
* [RAGDoll: Efficient Offloading-based Online RAG System on a Single GPU](https://arxiv.org/abs/2504.15302), Arxiv 2025 #
* [Quake: Adaptive Indexing for Vector Search](https://arxiv.org/pdf/2506.03437), OSDI 2025
* [iQAN: Fast and Accurate Vector Search with Efficient Intra-Query Parallelism on Multi-Core Architectures](https://dl.acm.org/doi/abs/10.1145/3572848.3577527), PPoPP 2023
* [ParlayANN: Scalable and Deterministic Parallel Graph-Based Approximate Nearest Neighbor Search Algorithms](https://www.cs.ucr.edu/~yihans/papers/2024/PPoPP24/parlayann.pdf), PPoPP 2024
* [DGRAG: Distributed Graph-based Retrieval-Augmented Generation in Edge-Cloud Systems](https://arxiv.org/abs/2505.19847), Arxiv 2025
* [RAGServe: Fast Quality-Aware RAG Systems with Configuration Adaptation](https://arxiv.org/pdf/2412.10543), Arxiv 2025
* [RAGCache: Efficient Knowledge Caching for Retrieval-Augmented Generation](https://arxiv.org/pdf/2404.12457), Arxiv 2025
* [ELERAG: Efficient Retrieval-Augmented Generation Inference with Lookahead Retrieval](https://arxiv.org/abs/2502.20969), Arxiv 2025
* [Patchwork: A Unified Framework for RAG Serving](https://arxiv.org/pdf/2505.07833), Arxiv 2025
* [AquaPipe: A Quality-Aware Pipeline for Knowledge Retrieval and Large Language Models](https://dl.acm.org/doi/abs/10.1145/3709661), SIGMOD 2025
* [VSAG: An Optimized Search Framework for Graph-based Approximate Nearest Neighbor Search](https://arxiv.org/pdf/2503.17911), VLDB 2025
* [Efficient Graph-Based Approximate Nearest Neighbor Search Achieving: Low Latency Without Throughput Loss](https://arxiv.org/pdf/2504.20461), Arxiv 2025

## 3. External Memory Accelerating
### 3.1 Processing in memory
* [Scalable Billion-point Approximate Nearest Neighbor Search Using SmartSSDs](https://www.usenix.org/system/files/atc24-tian.pdf), ATC 2024
* [Accelerating large-scale graph-based nearest neighbor search on a computational storage platform](https://ieeexplore.ieee.org/document/9726805), TC 2022
* [Accelerating Retrieval-Augmented Generation](https://dl.acm.org/doi/10.1145/3669940.3707264), ASPLOS 2025
* [NDSEARCH: Accelerating Graph-Traversal-Based Approximate Nearest Neighbor Search through Near Data Processing](https://arxiv.org/pdf/2312.03141), ISCA 2024 #
* [Fast Graph Vector Search via Hardware Acceleration and Delayed-Synchronization](https://arxiv.org/pdf/2406.12385), VLDB 2025 #
* [Chameleon: a Heterogeneous and Disaggregated Accelerator System for Retrieval-Augmented Language Models](https://www.vldb.org/pvldb/vol18/p42-jiang.pdf), VLDB 2025 #
* [A SmartSSD-based Near Data Processing Architecture for Scalable Billion-point Approximate Nearest Neighbor Search](https://dl.acm.org/doi/10.1145/3736589), ToS 2025
* [REIS: A High-Performance and Energy-Efficient Retrieval System with In-Storage Processing](https://www.iscaconf.org/isca2025/program/), ISCA 2025
* [DReX: Accurate and Scalable Dense Retrieval Acceleration via Algorithmic-Hardware Codesign](https://arg.csl.cornell.edu/) ISCA 2025
* [Robust Implementation of Retrieval-Augmented Generation on Edge-based Computing-in-Memory Architectures](https://dl.acm.org/doi/10.1145/3676536.3676674), ICCAD 2024
* [Compute-Enabled CXL Memory Expansion for Efficient Retrieval Augmented Generation](https://ieeexplore.ieee.org/document/11022767), IEEE Micro 2025
* [HDANNS: In-Memory Hyperdimensional Computing for Billion-Scale Approximate Nearest Neighbour Search Acceleration](https://ieeexplore.ieee.org/document/10880114), TCSAI 2025
* [DRIM-ANN: An Approximate Nearest Neighbor Search Engine based on Commercial DRAM-PIMs](https://arxiv.org/pdf/2410.15621), Arxiv 2024
* [Co-design Hardware and Algorithm for Vector Search](https://dl.acm.org/doi/pdf/10.1145/3581784.3607045), SC 2023
* [DF-GAS: a Distributed FPGA-as-a-Service Architecture towards Billion-Scale Graph-based Approximate Nearest Neighbor Search](https://dl.acm.org/doi/abs/10.1145/3613424.3614292), MICRO 2023
* [Accelerating Graph-based Vector Search via Delayed-Synchronization Traversal](https://arxiv.org/pdf/2406.12385), VLDB 2025
### 3.2 Second-tier Memory
* [Starling: An I/O-Efficient Disk-Resident Graph Index Framework for High-Dimensional Vector Similarity Search on Data Segment](https://arxiv.org/pdf/2401.02116), SIGMOD 2024
* [Characterizing the Dilemma of Performance and Index Size in Billion-Scale Vector Search and Breaking It with Second-Tier Memory](https://arxiv.org/pdf/2405.03267), Arxiv 2024
* [HM-ANN: Efficient Billion-Point Nearest Neighbor Search on Heterogeneous Memory](https://papers.nips.cc/paper/2020/hash/788d986905533aba051261497ecffcbb-Abstract.html), NIPS 2020
* [LM-DiskANN: Low Memory Footprint in Disk-Native Dynamic Graph-Based ANN Indexing](https://ieeexplore.ieee.org/document/10386517),  BigData 2023
* [DiskANN: Fast Accurate Billion-point Nearest Neighbor Search on a Single Node](https://papers.nips.cc/paper_files/paper/2019/hash/09853c7fb1d3f8ee67a61b6bf4a7f8e6-Abstract.html), NIPS 2019
* [LSM-VEC: A Large-Scale Disk-Based System for Dynamic Vector Search](https://arxiv.org/pdf/2505.17152), SOSP 2025
* [FreshDiskANN: A Fast and Accurate Graph-Based ANN Index for Streaming Similarity Search](https://arxiv.org/abs/2105.09613), Arxiv 2021
