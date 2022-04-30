# github.com/randolphcyg/gozeropprof

> gozeropprof is a tool used to integrate pprof into go-zero and analyze the running performance of go-zero projects.

## 1. Install

```shell
go get "github.com/randolphcyg/gozeropprof"
```

## 2. Usage

Register pprof agent at the gozero project entry method：

```go
package main

import "github.com/RandolphCYG/gozeropprof"

func main() {
    // ...
    gozeropprof.StartAgent("0.0.0.0", 6060)
	// ...
}
```

## 3. Visualization

- Make sure to install the Graphviz tool first
- Execute the following command on the server where the service is located, and the pprof analysis results will be presented at the address http://127.0.0.1:1357

```shell
go tool pprof -http=:1357 http://127.0.0.1:6060/debug/pprof/goroutine
```