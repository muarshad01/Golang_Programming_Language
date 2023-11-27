## 246. Introduction

* Test must
    * be in a file that ends with `_test.go`
    * put the file in `the same package` as the one being tested
    * be in a `func` with an signature `func TestXxx(t *testing.T)`
* Run a test
    * `go test` 
* Deal with test failure
    * use `t.Error` to signal failure
* Nice idiom
    * expected
    * got

***

## 247. Table tests

***

## 248. Example tests

* [Testable Examples in Go](https://go.dev/blog/examples)

***

## 249. `Golint`

* `go fmt ./...`
    * format go code
* `go vet ./...`
    * reports suspicious constructs
* `golint ./...`
    * reports poor coding style

```
$ mkdir -p $GOPATH/src/test
$ cd $GOPATH/src/test
$ go mod init test
$ go get -u golang.org/x/lint/golint
$ go install golang.org/x/lint/golint       # go install, puts the executable in $GOPATH/bin
$ echo $GOBIN | grep golint
$ golint main.go
```

***

## 250. Benchmark

***

## 251. Coverage

***

## 252. Benchmark examples

***

## 253. Review

***







# dir1/main_test.go
```
package dir1

import (
        "fmt"
        "strings"
        "testing"
)

const s = "Hello, how are you!"

var xs []string

func TestCat(t *testing.T) {
        s := "Shaken not stirred"
        xs := strings.Split(s, " ")
        s = Cat(xs)
        if s != "Shaken not stirred" {
                t.Error("got", s, "want", "Shaken not stirred")
        }
}

func TestJoin(t *testing.T) {
        s := "Shaken not stirred"
        xs := strings.Split(s, " ")
        s = Join(xs)
        if s != "Shaken not stirred" {
                t.Error("got", s, "want", "Shaken not stirred")
        }
}

func ExampleJoin() {
        s := "Shaken not stirred"
        xs := strings.Split(s, " ")
        fmt.Println(Join(xs))
        // Output:
        // Shaken not stirred
}

func ExampleCat() {
        s := "Shaken not stirred"
        xs := strings.Split(s, " ")
        fmt.Println(Cat(xs))
        // Output:
        // Shaken not stirred
}

func BenchmarkCat(b *testing.B) {
        xs := strings.Split(s, " ")
        b.ResetTimer()
        for i := 0; i < b.N; i++ {
                Cat(xs)
        }
}

func BenchmarkJoin(b *testing.B) {
        xs := strings.Split(s, " ")
        b.ResetTimer()
        for i := 0; i < b.N; i++ {
                Join(xs)
        }
}
```

# dir1/main.go
```
import "strings"

func Cat(xs []string) string {
        s := xs[0]
        for _, v := range xs[1:] {
                s += " "
                s += v
        }
        return s
}

func Join(xs []string) string {
        return strings.Join(xs, " ")
}
```

# main.go
```
package main

import (
        "fmt"
        "strings"
        "test_code/dir1"
)

func main() {
        const s = "hell how are you doin g. I'm doing fine. What's new at your end. Nothing special. How about you. Nothing!"
        xs := strings.Split(s, " ")
        fmt.Println(dir1.Cat(xs))
        fmt.Println(dir1.Join(xs))
}
```

```
$ ls
$ dir1	go.mod	main.go
```

```
TestCat(t *testing.T) {...}
BenchmarkCat(b *testing.B) {...}
ExampleCat(t *testing.T) {...}
```
