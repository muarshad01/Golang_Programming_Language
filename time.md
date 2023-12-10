* [time package](https://pkg.go.dev/time#Duration.Truncate)

```go
d1 := time.Duration(rand.Int63n(250))
time.Sleep(d1*time.Millisecond)
```

```go
time.Sleep(time.Duration(rand.Int63n(250))*time.Millisecond)`
```
* `time.Sleep` takes `type Duration`
* `time.Millisecond` is a constant in the `time` package
* `Int63n` returns `int64`
* `type Duration`'s underlying type is `int64`
* get an `int64`, convert it to `time.Duration`, then use it in `time.Sleep`

```go
type Duration int64
```
