# Uninitialized Map Access in Go

This repository demonstrates a common error in Go: accessing a map before it has been initialized.  This results in a runtime panic.

The `bug.go` file contains the buggy code. The `bugSolution.go` file provides a corrected version.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `go run bug.go` (this will panic).
4. Run `go run bugSolution.go` (this will print 10).

## Explanation

In Go, maps are reference types.  Before you can use a map to store key-value pairs, you must initialize it using `make(map[KeyType]ValueType)`.  Attempting to access or assign to a non-initialized map causes a runtime panic.

## Solution

Always initialize your maps using `make()` before using them:

```go
map[string]int = make(map[string]int)
```