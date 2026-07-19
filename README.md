# HALO
Handwritten AVX-512 Implementations of SneakySnake Pre-Alignment Filter

## 1. Overview
This repository contains the handwritten AVX-512 implementations of the SneakySnake DNA pre-alignment filter. The implementations are categorized by their memory alignment strategy: **Byte-aligned** and **Nibble-aligned**. These versions are optimized for performance and include comprehensive testing procedures to measure throughput, latency, and hardware performance metrics.

---

## 2. Byte-aligned Handwritten
This folder contains *Testing-ByteAligned* and *Testing-FullyAligned-Additional*, which house the byte-aligned handwritten AVX-512 implementation. 

**Metrics tracked include:**
* Number of similar and dissimilar sequences.
* Execution time.
* Throughput (cycles/read and cycles/base).
* Average cycles per function.
* Instruction count and IPC (Instructions Per Cycle).
* Branch and cache misses.

---

## 3. Nibble-aligned Handwritten
This folder contains *Testing_NibblesVer* and *HANDWRITTEN_NIBBLESVER_ADDITIONALTEST*, which house the nibble-aligned handwritten AVX-512 implementation.

**Metrics tracked include:**
* Number of similar and dissimilar sequences.
* Execution time.
* Throughput (cycles/read and cycles/base).
* Average cycles per function.
* Instruction count and IPC (Instructions Per Cycle).
* Branch and cache misses.
