# Survey Outline for RAG-based LLM Inference Systems

This document turns the repository paper list into a survey-writing scaffold. It is designed to help you move from a curated reading list to a structured survey paper draft with clear sections, comparison points, and writing priorities.

## 1. Suggested survey title

**Systematic Design of RAG-based LLM Inference Systems: A Survey**

Alternative titles:
- **RAG-based LLM Inference Systems: A System and Architecture Survey**
- **Efficient Retrieval-Augmented Generation Inference: A Survey of Systematic Designs**

## 2. Core survey message

The main message of the survey can be:

> Recent work on retrieval-augmented generation (RAG) is shifting from model-only improvements to end-to-end system design. Performance, cost, and quality now depend on how retrieval, cache management, pipeline scheduling, memory hierarchy, and hardware acceleration are co-designed for LLM inference.

This message matches the current repository organization and can be used as the thesis of the paper.

## 3. Recommended paper structure

### 3.1 Abstract
- Introduce RAG as an inference-time systems problem, not only a model-quality problem.
- Explain that the survey focuses on **systematic designs** for efficient RAG inference.
- Summarize the main design axes:
  - GPU acceleration
  - data reuse and cache reuse
  - pipeline parallelism
  - external-memory and storage-aware acceleration
  - emerging applications
- State the survey contribution: taxonomy, comparison, trends, and open challenges.

### 3.2 Introduction
- Why RAG inference is important for modern LLM systems
- Why system design matters:
  - retrieval latency
  - KV-cache reuse
  - memory capacity limits
  - disaggregated or heterogeneous hardware
  - throughput/latency/quality trade-offs
- What is missing in current literature: a system-centric overview
- Contributions of this survey:
  1. A taxonomy of RAG inference system designs
  2. A comparison of architectural trade-offs
  3. A summary of open problems and future opportunities

### 3.3 Background
- RAG pipeline overview:
  1. query encoding
  2. vector retrieval
  3. reranking or filtering
  4. prompt construction
  5. LLM decoding
- Key system bottlenecks:
  - vector search latency
  - GPU memory pressure
  - CPU/GPU data movement
  - storage I/O
  - pipeline imbalance
  - stale or low-hit-rate caches
- Important evaluation metrics:
  - latency
  - throughput
  - tail latency
  - recall / answer quality
  - cost efficiency
  - memory footprint
  - energy efficiency

### 3.4 Taxonomy of RAG Inference System Design

This can be the central taxonomy figure in the paper.

#### 3.4.1 GPU acceleration
Use papers from **README Section 1**.

Focus questions:
- How is vector search adapted to GPU architectures?
- How do systems overlap computation and data transfer?
- When do GPU-native ANN structures outperform CPU/GPU hybrid designs?

Representative papers:
- RAGO
- Hermes
- CAGRA
- VecFlow
- PilotANN
- CPU/GPU collaborative filtering and re-ranking

#### 3.4.2 Data reuse and cache-centric optimization
Use papers from **README Section 2.1**.

Focus questions:
- What is being reused: retrieved chunks, reranker states, KV cache, configuration state, or memory summaries?
- How do systems balance hit rate, freshness, and storage cost?
- When is cache-augmented generation enough without full retrieval?

Representative papers:
- Cache-Craft
- CacheBlend
- MemoRAG
- HyperRAG
- CacheFocus
- METIS

#### 3.4.3 Pipeline parallelism and scheduling
Use papers from **README Section 2.2**.

Focus questions:
- How are retrieval and generation overlapped?
- Which stages are pipelined across CPU, GPU, and storage?
- How do systems adapt under changing query load or retrieval complexity?

Representative papers:
- PipeRAG
- RAGDoll
- AquaPipe
- Patchwork
- ELERAG
- DGRAG

#### 3.4.4 External-memory and storage-aware acceleration
Use papers from **README Section 3**.

Split the discussion into two parts:

##### 3.4.4.1 Processing-in-memory / near-data processing
- SmartSSD-based systems
- computational storage platforms
- PIM/CIM-based RAG acceleration
- FPGA or accelerator-assisted vector search

##### 3.4.4.2 Second-tier memory and disk-resident vector search
- DiskANN family
- SSD-aligned search designs
- heterogeneous memory systems
- dynamic disk-native ANN indexes

Core comparison points:
- I/O efficiency
- index size versus recall
- cost per query
- storage-compute co-design
- scalability beyond GPU memory

#### 3.4.5 Application-driven RAG systems
Use papers from **README Section 4**.

Focus questions:
- How do domain constraints change system design?
- What retrieval patterns appear in database, table QA, or enterprise settings?
- Which application-specific workloads motivate new optimizations?

### 3.5 Cross-cutting design dimensions

This section can synthesize the entire survey.

Recommended subsections:

#### 3.5.1 Latency vs. quality trade-off
- Approximate retrieval
- cache-based shortcuts
- lookahead retrieval
- configuration adaptation

#### 3.5.2 Throughput vs. memory capacity
- GPU memory limits
- KV-cache growth
- disaggregated memory
- external or second-tier memory

#### 3.5.3 Static indexing vs. dynamic updates
- online indexing
- incremental update
- streaming vector search
- freshness constraints

#### 3.5.4 Monolithic vs. heterogeneous architectures
- CPU/GPU co-design
- GPU + SSD
- SmartSSD / storage compute
- edge-cloud or distributed RAG

#### 3.5.5 Retrieval-centric vs. generation-centric optimization
- ANN speedup
- prompt assembly efficiency
- decode-time cache reuse
- end-to-end pipeline balancing

### 3.6 Suggested comparison table

Create one main table in the survey with the following columns:

| Paper | Year | Main target | Optimization level | Hardware setting | Main benefit | Key trade-off |
| --- | --- | --- | --- | --- | --- | --- |
| RAGO | 2025 | End-to-end RAG serving | system pipeline | GPU | lower latency / higher throughput | system complexity |
| CacheBlend | 2025 | cached knowledge fusion | cache reuse | GPU/LLM serving | faster serving | cache validity and hit rate |
| PipeRAG | 2025 | adaptive pipelining | scheduling | heterogeneous | overlap retrieval and generation | balancing difficulty |
| SmartSSD / NDSEARCH / Chameleon | 2024-2025 | large-scale retrieval | storage or near-data processing | SSD/PIM/accelerator | scalability beyond GPU memory | hardware specialization |
| DiskANN family | 2019-2025 | disk-native ANN | index + I/O design | SSD / second-tier memory | large-scale low-memory search | I/O-sensitive performance |

You can extend the table with:
- retrieval granularity
- dynamic update support
- application domain
- quality metric
- open-source availability

### 3.7 Suggested figures

Recommended figures for the survey:

1. **End-to-end RAG inference pipeline**
   - retrieval, reranking, prompt building, generation

2. **Taxonomy figure**
   - GPU acceleration
   - reuse/caching
   - pipeline scheduling
   - external-memory acceleration
   - application systems

3. **Memory hierarchy figure**
   - GPU HBM
   - CPU DRAM
   - CXL / second-tier memory
   - SSD / SmartSSD / storage compute

4. **Design trade-off map**
   - x-axis: latency / throughput
   - y-axis: memory capacity / scalability

### 3.8 Key research trends to highlight

Based on the current paper list, the survey can emphasize these trends:

1. **RAG is becoming a systems problem**
   - research is moving from standalone retrieval quality to end-to-end inference efficiency

2. **Cache reuse is no longer a minor optimization**
   - many recent works treat caches as a first-class design component

3. **Memory hierarchy is central**
   - GPU memory alone is insufficient for large-scale RAG deployment

4. **Storage and near-data processing are becoming practical**
   - SmartSSD, PIM, CIM, and disk-native ANN are increasingly relevant

5. **Quality-aware adaptation is emerging**
   - newer systems optimize for both quality and efficiency, not just speed

### 3.9 Open challenges and future directions

This section can help make the survey forward-looking.

#### 3.9.1 Unified evaluation methodology
- Different papers use different datasets, metrics, and serving assumptions.
- A survey should call for more standardized end-to-end RAG benchmarks.

#### 3.9.2 Joint optimization of retrieval and decoding
- Many systems still optimize retrieval and generation separately.
- Future systems may co-optimize chunk selection, prompt layout, and decode scheduling.

#### 3.9.3 Dynamic and continuously updated knowledge bases
- Freshness remains difficult in large-scale ANN indexes and caches.
- This is especially important for production RAG systems.

#### 3.9.4 Hardware/software co-design for long-context RAG
- Long contexts amplify memory pressure and KV-cache costs.
- Future work may combine compression, reuse, and near-data acceleration.

#### 3.9.5 Multi-tenant and production serving
- The current literature is still limited in multi-tenant isolation, SLO management, and cost-aware scheduling.

#### 3.9.6 Application-specific RAG inference
- Database systems, enterprise QA, coding assistants, and edge deployment may require different RAG architectures.

## 4. Writing plan

Recommended workflow:

1. **Use README.md as the master paper list**
2. **Draft the taxonomy section first**
3. **Build the comparison table while reading papers**
4. **Write one synthesis paragraph per subsection**
5. **Finish with open challenges and future directions**

For each paper, extract:
- target problem
- system bottleneck
- key optimization
- hardware assumptions
- main reported benefit
- limitation or trade-off

## 5. Minimum survey deliverables

To turn this repository into a first survey draft, aim to complete:

- [ ] title
- [ ] abstract
- [ ] introduction
- [ ] background section
- [ ] taxonomy section
- [ ] comparison table
- [ ] open challenges section
- [ ] conclusion

## 6. Optional next repository improvements

If you want to continue extending the repository later, useful additions would be:

- a `paper-summary` template for note taking
- a CSV table of papers and attributes
- a `bibtex` file for citation management
- tags for hardware, workload, and optimization type
- a timeline figure or chronological appendix
