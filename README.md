# Path Normalizer in Go

## Overview
This Go program converts a given **relative path** into an **absolute path** based on a specified **current directory**. It properly handles:
- `..` (moving up one level)
- `.` (current directory, ignored)
- Redundant slashes (`//`)
- Correct path normalization

## Problem Statement
Given a **current directory** and a **relative path**, compute the corresponding **absolute path** without using built-in path resolution functions. The solution should:
- Avoid multiple consecutive slashes (`///` should be normalized to `/`)
- Properly handle `..` and `.` in paths
- Return a valid absolute path

## Example
### **Input:**
```bash
Current Directory: /home/myhome/myfolder1/myfolder2
Relative Path: ../mydocument.txt
```

### **Output:**
```bash
Absolute Path: /home/myhome/myfolder1/mydocument.txt
```

## Implementation
The program:
1. Splits both `currentDir` and `relativePath` into parts.
2. Uses a **stack** to process the path:
   - Pushes valid directory names.
   - Pops the last directory when encountering `..`.
   - Ignores `.` (current directory references).
3. Joins the stack to generate a normalized absolute path.


## How to Run
### **1. Clone the Repository**
```bash
git clone https://github.com/yourusername/path-normalizer-go.git
cd path-normalizer-go
```

### **2. Run the Program**
```bash
go run main.go
```

