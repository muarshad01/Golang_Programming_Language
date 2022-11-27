

# Concurrency

* [sync.WaitGroup](https://pkg.go.dev/sync#WaitGroup)
```go
type WaitGroup
	func (wg *WaitGroup) Add(delta int)
	func (wg *WaitGroup) Done()
	func (wg *WaitGroup) Wait()
```

***

* [sync.Mutex](https://pkg.go.dev/sync#Mutex)
```go
type Mutex
	func (m *Mutex) Lock()
	func (m *Mutex) TryLock() bool
	func (m *Mutex) Unlock()
```

***

* [sync/atomic](https://pkg.go.dev/sync/atomic#pkg-index)
```go
func AddInt64(addr *int64, delta int64) (new int64)
func LoadInt64(addr *int64) (val int64)
```

***

[runtim](https://pkg.go.dev/runtime)
```go
const GOOS string = goos.GOOS
const GOARCH string = goarch.GOARCH
func NumCPU() int
func NumGoroutine() int
func GOMAXPROCS(n int) int
func Gosched()
```

***

```
// go run -race main.go
// vs
// go run main.go
```