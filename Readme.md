# README of Selection Sorting Program

Author: Kaibin LU (HKUST)

## 1. Algorithms Included in This Project
This project implements a basic comparison-based sorting algorithm.

- Sorting Algorithm: 
  The sorting approach follows a naive algorithm similar to Selection Sort, comparing each element with the remaining ones and swapping when necessary. 
  The total number of swaps performed is recorded for statistical output.

---

## 2. Usage Setup
Ensure the following files are placed in the same directory:

| Purpose             | Filename                                  |
| ------------------- | ----------------------------------------- |
| Main source program | sort.c                                    |
| Configuration file  | config.txt                                |
| Data file           | Specified in the first line of config.txt |

Example directory structure:

```
project/
├── sort.c
├── config.txt
├── numbers.txt
```

---

## 3. Compilation Instruction

### Linux / macOS
```bash
gcc sort.c -o sort
```

### Windows (MinGW)
```bash
gcc sort.c -o sort.exe
```

Note: Execution time measurements using `getrusage()` are enabled only on non-Windows systems.

---

## 4. Execution Instruction

### Linux / macOS
```bash
./sort
```

### Windows
```bash
sort.exe
```

The program automatically reads configuration from `config.txt` and proceeds without requiring command-line arguments.

---

## 5. Input Files

| File       | Description                                                  |
| ---------- | ------------------------------------------------------------ |
| config.txt | Defines configuration parameters including the data filename |
| Data file  | Contains integer values to be sorted                         |

The data filename is obtained from the first line in `config.txt`.

---

## 6. Output Files

| Output File | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| output.txt  | Contains the sorted list of integers                         |
| stat.txt    | Contains the number of swap operations performed             |
| time.txt    | Contains execution timing results (only generated on non-Windows platforms) |

---

## Appendix

### A. Format of Input Files

#### config.txt Format

The configuration file contains five lines in the following order:

| Line | Content                                  |
| ---- | ---------------------------------------- |
| 1    | Name of the data file                    |
| 2    | Number of integers to be read            |
| 3    | Parameter2 (unused by the sorting logic) |
| 4    | Parameter3 (unused by the sorting logic) |
| 5    | Parameter4 (float, unused but stored)    |

Example:

```
numbers.txt
1000
5
10
0.75
```

---

#### Data File Format

A space-separated list of integers. 
The total number of integers must match the value specified in line 2 of config.txt.

Example:

```
9 2 5 1 7 4
```

---

### B. Format of Output Files

#### output.txt
Contains the sorted integers in ascending order separated by spaces and terminated with a newline.

Example:

```
1 2 4 5 7 9
```

#### stat.txt
Contains a single integer representing the total number of swap operations.

Example:

```
15
```

#### time.txt (Linux/macOS only)
Contains four lines with user time and system time:

|Line | Meaning| 
| ---- | ---------------------------------------- |
|1 | Time spent reading the input| 
|2 | Time spent sorting| 
|3 | Time spent writing the output| 
|4 | Total execution time| 

Example:

```
0.0000145 0.0000003
0.0032402 0.0000001
0.0000102 0.0000005
0.0033509 0.0000009
```

---