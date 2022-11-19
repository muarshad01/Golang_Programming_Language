

# Concurrency

* [sync.WaitGroup](https://pkg.go.dev/sync#WaitGroup)
```go
type WaitGroup
	func (wg *WaitGroup) Add(delta int)
	func (wg *WaitGroup) Done()
	func (wg *WaitGroup) Wait()
```

* [sync/atomic](https://pkg.go.dev/sync/atomic#pkg-index)
```go
func AddInt64(addr *int64, delta int64) (new int64)
func LoadInt64(addr *int64) (val int64)
```
