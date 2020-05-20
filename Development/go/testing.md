# [testing](https://golang.org/pkg/testing/)

## Benchmark

Any benchmark should be careful to prevent **compiler optimization**.

Example `calc.go` in package `calc`:

```go
package calc

import (
	"time"
)

var input float64

func init() {
	if time.Now().Year() > 1900 {
		input = 426942694269
	}
}

func calc() int {
	x := input
	x /= 6.9
	x /= 4.2
	x /= 6.9
	x /= 4.2
	return int(x)
}
```

Example `calc_test.go` in package `calc`:

```go
package calc

import (
	"runtime"
	"testing"
)

func BenchmarkX(b *testing.B) {
	for i := 0; i < b.N; i++ {
		calc()
	}
}

var sink int

func BenchmarkCalcSink(b *testing.B) {
	var result int
	for i := 0; i < b.N; i++ {
		result = calc()
	}

	// prevent compiler optimization
	sink = result
}

func BenchmarkCalcKeepAlive(b *testing.B) {
	for i := 0; i < b.N; i++ {
		result := calc()

		// prevent compiler optimization
		runtime.KeepAlive(result)
	}
}
```

Benchmark result when run with `go test -bench=.`

```txt
goos: linux
goarch: amd64
BenchmarkCalc-4                 1000000000               0.343 ns/op
BenchmarkCalcSink-4             229652618                5.30 ns/op
BenchmarkCalcKeepAlive-4        225297381                5.27 ns/op
```

`BenchmarkCalc` is fast because it has compiler optimization.

There are 2 methods for preventing compiler optimization:
sink (`BenchmarkCalcSink`) or keep alive (`BenchmarkCalcKeepAlive`).
