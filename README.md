# Awsome-RAG-LLM-Inference-System
RAG-based LLM inference: a survey about systematic designs

## 1. GPU Accelerate
* [RAGO: Systematic Performance Optimization for Retrieval-Augmented Generation Serving](https://arxiv.org/abs/2503.14649), ISCA 2025
* [Hermes: Algorithm-System Co-design for Efficient Retrieval Augmented Generation At Scale](https://michaeltshen.github.io/Files/Hermes.pdf), ISCA 2025
* [Fast Vector Query Processing for Large Datasets Beyond GPU Memory with Reordered Pipelining](https://xinjin.github.io/files/NSDI24_Rummy.pdf), NSDI 2024
* [CAGRA: Highly Parallel Graph Construction and Approximate Nearest Neighbor Search for GPUs](https://arxiv.org/pdf/2308.15136), ICDE 2024
* [Towards High-throughput and Low-latency Billion-scale Vector Search via CPU/GPU Collaborative Filtering and Re-ranking](https://www.usenix.org/system/files/fast25-tian-bing.pdf), FAST 2025
* [GGNN: Graph-Based GPU Nearest Neighbor Search](https://ieeexplore.ieee.org/document/9739943/), TBD 2023

## 2. Data Reuse and Pipeline Parallelism
### Data Reuse
* [Cache-Craft: Managing Chunk-Caches for Efficient Retrieval-Augmented Generation](https://arxiv.org/pdf/2502.15734v1), SIGMOD 2025
* [CacheBlend: Fast Large Language Model Serving for RAG with Cached Knowledge Fusion](https://arxiv.org/abs/2405.16444), Eurosys 2025 (Best Paper)
### Pipeline Parallelism
* [PipeRAG: Fast Retrieval-Augmented Generation via Adaptive Pipeline Parallelism](https://arxiv.org/pdf/2403.05676), KDD 2025
* [RAGDoll: Efficient Offloading-based Online RAG System on a Single GPU](https://arxiv.org/abs/2504.15302), Arxiv 2025
* [Quake: Adaptive Indexing for Vector Search](https://arxiv.org/pdf/2506.03437), OSDI 2025
* [iQAN : Fast and Accurate Vector Search with Efficient Intra-Query Parallelism on Multi-Core Architectures](https://dl.acm.org/doi/abs/10.1145/3572848.3577527), PPoPP 2023
* [ParlayANN: Scalable and Deterministic Parallel Graph-Based Approximate Nearest Neighbor Search Algorithms](https://www.cs.ucr.edu/~yihans/papers/2024/PPoPP24/parlayann.pdf), PPoPP 2024

## 3. External Memory Accelerating
### 3.1 Processing in memory
* [Scalable Billion-point Approximate Nearest Neighbor Search Using SmartSSDs](https://www.usenix.org/system/files/atc24-tian.pdf), ATC 2024
* [Accelerating large-scale graph-based nearest neighbor search on a computational storage platform](https://ieeexplore.ieee.org/document/9726805), TC 2022
* [Accelerating Retrieval-Augmented Generation](https://dl.acm.org/doi/10.1145/3669940.3707264), ASPLOS 2025
### 3.2 Second-tier Memory
* [Starling: An I/O-Efficient Disk-Resident Graph Index Framework for High-Dimensional Vector Similarity Search on Data Segment](https://arxiv.org/pdf/2401.02116), SIGMOD 2024
* [Characterizing the Dilemma of Performance and Index Size in Billion-Scale Vector Search and Breaking It with Second-Tier Memory](https://arxiv.org/pdf/2405.03267), Arxiv 2024
* [HM-ANN: Efficient Billion-Point Nearest Neighbor Search on Heterogeneous Memory](https://papers.nips.cc/paper/2020/hash/788d986905533aba051261497ecffcbb-Abstract.html), NIPS 2020
* [LM-DiskANN: Low Memory Footprint in Disk-Native Dynamic Graph-Based ANN Indexing](https://ieeexplore.ieee.org/document/10386517),  BigData 2023
