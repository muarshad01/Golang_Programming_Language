## 178. Understanding

[type error](https://pkg.go.dev/builtin#error)
```go
type error interface {
	Error() string
}
```
* `error` in Go is an interface.

[type errorString](https://cs.opensource.google/go/go/+/refs/tags/go1.19.3:src/errors/errors.go;l=66;drc=d5de62df152baf4de6e9fe81933319b86fd95ae4;bpv=1;bpt=0)
```go
type errorString struct {
	s string
}
```
`errorString` is a trivial implementation of `error` interface.

```go
func (e *errorString) Error() string {
	return e.s
}
```
Any other type (e.g., type `errotString` struct) that implements `Error()` method is also of type `error` interface in Go.

[func New(...)](https://pkg.go.dev/errors#New)
```go
func New(text string) error {
	return &errorString{text}
}
```
`func New(...)` returns an `error` that formats as the given text. Each call to `New()` returns a distinct `error` value even if the text is identical.

***

## 179. Checking errors

* code
  - https://go.dev/play/p/flMiN9rZtnC
  - https://go.dev/play/p/SHxi-AdsJT9
  - https://go.dev/play/p/fSqQ0Q1uLhu
  - https://go.dev/play/p/NdQkbOK909r

***

## Lecture 180. Printing and logging

[package log](https://pkg.go.dev/log#pkg-index)
```go
func Print(v ...any)
func Printf(format string, v ...any)
func Println(v ...any)

func Fatal(v ...any)
func Fatalf(format string, v ...any)
func Fatalln(v ...any)

func Panic(v ...any)
func Panicf(format string, v ...any)
func Panicln(v ...any)

```
* For `log.Println()`, default is **stdout** similar to `fmt.Println()` but can also write to a logfile.
* For  `log.Fatal()`, `os.Exit()` is executed, i.e., exit status 1; deferred functions are not run.
* For `Panic()`, deferred functions are run; i.e., can use *recover*.
* code
  - https://go.dev/play/p/y_ozMejQuBD
  - https://go.dev/play/p/u9bXYTxWod7

```go
func Errorf(format string, a ...any) error
func New(text string) error
```
Note: `fmt.Errorf(...)` & `errors.New()` both return `error`

***

## 181. Recover

* [Defer, Panic, and Recover](https://blog.golang.org/defer-panic-and-recover)

* code
  - https://play.golang.org/p/HI4uG55ait
  - https://play.golang.org/p/ZocncqtwaK

***

## 182. Errors with info

`errors.New()`
`fmt.Errorf()`
`builtin.error`
