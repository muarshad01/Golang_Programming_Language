## 230. Understanding

* [Error handling and Go](https://go.dev/blog/error-handling-and-go)

[type error](https://pkg.go.dev/builtin#error)
```go
type error interface {
	Error() string
}
```
* `type error` in Go is an interface.
* Any other type that has `Error() string` method attached to it is also of `type error interface{}` in Go, i.e., it will implicitly implement `type error interface{}` and it will be an `error`.


```go
package errors

// New returns an error that formats as the given text.
// Each call to New returns a distinct error value even if the text is identical.
func New(text string) error {
	return &errorString{text}
}

// errorString is a trivial implementation of error.
type errorString struct {
	s string
}

func (e *errorString) Error() string {
	return e.s
}
```
* Any other type (e.g., `type errotString struct{}`) that implements `Error() string` method is also of `type error interface{}` in Go.

***

## 231. Checking `errors`

* Examples
    * https://go.dev/play/p/flMiN9rZtnC
    * https://go.dev/play/p/SHxi-AdsJT9
    * https://go.dev/play/p/fSqQ0Q1uLhu
    * https://go.dev/play/p/NdQkbOK909r

***

## 232. Printing and logging

* [package log](https://pkg.go.dev/log#pkg-index)
```go
func Print(v ...any)
func Println(v ...any)
func Printf(format string, v ...any)

func Fatal(v ...any)
func Fatalln(v ...any)
func Fatalf(format string, v ...any)

func Panic(v ...any)
func Panicln(v ...any)
func Panicf(format string, v ...any)
```
* For `log.Println()`
    * default is **stdout** similar to `fmt.Println()`
    * but can also write to a logfile.
* For  `log.Fatal()`
    * `os.Exit()` is executed, i.e., exit status 1
    * deferred functions are NOT run.
* For `Panic()`
    * deferred functions are run
    * i.e., can use RECOVER
* Examples
    * https://go.dev/play/p/y_ozMejQuBD
    * https://go.dev/play/p/u9bXYTxWod7

* [func panic](https://pkg.go.dev/builtin@go1.21.4#panic)
```go
func panic(v any)
```
* [func recover](https://pkg.go.dev/builtin@go1.21.4#recover)
```go
func recover() any
```

***

## 233. Recover

* [Defer, Panic, and Recover](https://blog.golang.org/defer-panic-and-recover)

* Example code
    * https://play.golang.org/p/HI4uG55ait
```go
package main

import "fmt"

func main() {
	var x int
	x++
	fmt.Println(x)
	i := c()
	fmt.Println(i)
}

func c() (i int) {
	defer func() { i++ }()
	return 1
}
```
    * https://play.golang.org/p/ZocncqtwaK
```go
package main

import "fmt"

func main() {
	f()
	fmt.Println("Returned normally from f.")
}

func f() {
	defer func() {
		if r := recover(); r != nil {
			fmt.Println("Recovered in f", r)
		}
	}()
	fmt.Println("Calling g.")
	g(0)
	fmt.Println("Returned normally from g.")
}

func g(i int) {
	if i > 3 {
		fmt.Println("Panicking!")
		panic(fmt.Sprintf("%v", i))
	}
	defer fmt.Println("Defer in g", i)
	fmt.Println("Printing in g", i)
	g(i + 1)
}
```

***

## 234. Errors with info

```go
func Errorf(format string, a ...any) error
func New(text string) error
```
Note: `fmt.Errorf(...)` & `errors.New()` both return `builtin.error`

***

## Useful Article

[map CRUD example that uses const errs](https://quii.gitbook.io/learn-go-with-tests/go-fundamentals/maps)
