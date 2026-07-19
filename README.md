# HALO: Accelerating the SneakySnake DNA Pre-Alignment Algorithm with AVX-512 Assembly
Handwritten AVX-512 Implementations of SneakySnake Pre-Alignment Filter

## 1. Overview
This repository contains the handwritten AVX-512 implementations of the SneakySnake DNA pre-alignment filter.

---

## 2. Byte-aligned Handwritten
This folder contains *Testing-ByteAligned*, which contains the byte-aligned handwritten AVX-512 implementation. 

**Metrics tracked include:**
* Number of similar and dissimilar sequences.
* Execution time.

---

## 3. Nibble-aligned Handwritten
This folder contains *HALO- Nibble-Align Handwritten AVX-512*, which contains the nibble-aligned handwritten AVX-512 implementation.

**Metrics tracked include:**
* Number of similar and dissimilar sequences.
* Execution time.

---

## 4. How to Run and Check Results

### Compilation
To compile the assembly and C files, use the following commands (example shown for the byte-aligned version):

```bash
nasm -f elf64 byte_aligned_test.asm -o byte_aligned_test.o
gcc -c byte_aligned_test.c -o byte_aligned_test_c.o -mavx512f -mavx512bw
gcc byte_aligned_test.o byte_aligned_test_c.o -o byte_aligned -mavx512f -mavx512bw

```

### Execution

Run the executable using the following syntax:

```bash
./byte_aligned <file> <threshold> <seq_len> <kmer_size> [limit] [debug_limit] [debug_show_len]

```

**Example:**

```bash
./byte_aligned "../THES3/DNAPAIRS/ERR240727_1_E2_30million.txt" 0 100 100 30000 0

```

### Results Verification

* **Console Output:** Upon execution, the program outputs performance metrics (sequence classification, timing, throughput, and hardware statistics) directly to the console.

## 5. Datasets
This repository also contains some datasets that were used for testing both implementations. As the original dataset is too large to be uploaded, smaller versions of the datasets are included. The genomic datasets are *E.coli K-12* and *Drosophila melanogaster*, both have basepair lengths of 100bp.
