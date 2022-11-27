## 178. Understanding

[type error](https://pkg.go.dev/builtin#error)
```go
type error interface {
	Error() string
}
```
`error` in Go is an interface.

package errors

[func New](https://pkg.go.dev/errors#New)
```go
func New(text string) error {
	return &errorString{text}
}
```
`func New()` returns an `error` that formats as the given text. Each call to `New()` returns a distinct `error` value even if the text is identical.

```go
type errorString struct {
	s string
}
```
`errorString` is a trivial implementation of error.

```
func (e *errorString) Error() string {
	return e.s
}
```
Any other type that implements "Error() string" is also of type "error" in Go.

***

# ------------------
179. Checking errors
# ------------------

code: https://go.dev/play/p/flMiN9rZtnC
code: https://go.dev/play/p/SHxi-AdsJT9
code: https://go.dev/play/p/fSqQ0Q1uLhu
code: https://go.dev/play/p/NdQkbOK909r

## Lecture 180. Printing and logging

[log](https://pkg.go.dev/log#pkg-index)
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

func SetOutput(w io.Writer)
```
* For `log.Println()`, default is *stdout* similar to `fmt.Println()` but can also write to a logfile.
* For  `log.Fatal()`, `os.Exit()` is executed, i.e., exit status 1; deferred functions are not run.
* For `log.Panic()`, deferred functions are run; i.e., can use *recover*.
* code
  - https://go.dev/play/p/y_ozMejQuBD
  - https://go.dev/play/p/u9bXYTxWod7

# ----------
181. Recover
# ----------

blog: https://blog.golang.org/defer-panic-and-recover

code: https://play.golang.org/p/HI4uG55ait
code: https://play.golang.org/p/ZocncqtwaK

# -------------------
182. Errors with info
# -------------------

1. errors.New()
2. fmt.Errorf()
3. builtin.error
