# HALO
Handwritten AVX-512 Implementations of SneakySnake Pre-Alignment Filter

## 1. Overview
This repository contains the handwritten AVX-512 implementations of the SneakySnake DNA pre-alignment filter.

---

## 2. Byte-aligned Handwritten
This folder contains *Testing-ByteAligned* and *Testing-FullyAligned-Additional*, which contains the byte-aligned handwritten AVX-512 implementation. 

**Metrics tracked include:**
* Number of similar and dissimilar sequences.
* Execution time.

---

## 3. Nibble-aligned Handwritten
This folder contains *Testing_NibblesVer* and *HANDWRITTEN_NIBBLESVER_ADDITIONALTEST*, which contains the nibble-aligned handwritten AVX-512 implementation.

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
* **Pre-computed Results:** For convenience, several test cases have already been executed within the provided notebook. You can verify these recorded performance metrics by referencing the [Excel link](https://docs.google.com/spreadsheets/d/1N6rS9DcO2w-w125h6w7prfowPQLwNy5LJp_1nJ99RWw/edit?gid=2008330343#gid=2008330343) to cross-reference the output data.
