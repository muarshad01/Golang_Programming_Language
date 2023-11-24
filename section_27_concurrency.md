## 201. Concurrency vs parallelism

* [Concurrency is not Parallelism by Rob Pike](https://www.youtube.com/watch?v=oV9rvDllKEg)

* Multi-core CPU
    * In 2006, Intel released the first dual-core CPU
    * In 2007, Google started the first effort to natively-take-advantage for multiple-cores
    * March 2012, The Go Programming Language Version 1.0 is released

* Concurrency
    * One CPU
    * Design Pattern
    * Multiple-threads run sequentially
* Parallelism
    * Multiple CPUs (Cores)

***

## 202. `WaitGroup`

* [runtime](https://pkg.go.dev/runtime?utm_source=godoc)
    * [runtime#NumCPU](https://pkg.go.dev/runtime#NumCPU)
    * [func#NumGoroutine](https://pkg.go.dev/runtime#NumGoroutine) 

```go
fmt.Println("OS\t\t",       runtime.GOOS)
fmt.Println("ARCH\t\t",     runtime.GOARCH)
fmt.Println("CPUs\t\t",     runtime.NumCPU())
fmt.Println("Goroutine\t",  runtime.NumGoroutine())
```

* [sync.WaitGroup](https://pkg.go.dev/sync#WaitGroup)

```go
var wg sync.WaitGroup
```

```go
type WaitGroup
    func (wg *WaitGroup) Add(delta int)
    func (wg *WaitGroup) Done()
    func (wg *WaitGroup) Wait()
```

***

## 203. Method sets revisited

***

## 204. Documentation

***

## 205. Race condition

***

## 206. Mutex

* [sync.Mutex](https://pkg.go.dev/sync#Mutex)

```go
var mu sync.Mutex
```

```go
type Mutex
    func (m *Mutex) Lock()
    func (m *Mutex) TryLock() bool
    func (m *Mutex) Unlock()
```

***

## 207. Atomic

* [sync/atomic](https://pkg.go.dev/sync/atomic#pkg-index)

```go
func AddInt64(addr *int64, delta int64) (new int64)
func LoadInt64(addr *int64) (val int64)
func AddInt32(addr *int32, delta int32) (new int32)
func LoadInt32(addr *int32) (val int32)
```
***

## Miscellaneous

* [Singleton Example](https://refactoring.guru/design-patterns/singleton/go/example)
```go
var lock = &sync.Mutex{}

lock.Lock()
defer lock.Unlock()
```

* [ConnPool Example](https://golangbyexample.com/golang-object-pool/)
```go
mulock *sync.Mutex

mulock : new(sync.Mutex)

mulock.Lock()
mulock.Unlock()
```

* [runtime](https://pkg.go.dev/runtime)
```go
const GOOS string = goos.GOOS
const GOARCH string = goarch.GOARCH
func NumCPU() int
func NumGoroutine() int
func GOMAXPROCS(n int) int
func Gosched()		            # Gosched() yields the processor, allowing other goroutines to run.
```

```go
func init() {
	runtime.GOMAXPROCS(runtime.NumCPU())
}
```

***
