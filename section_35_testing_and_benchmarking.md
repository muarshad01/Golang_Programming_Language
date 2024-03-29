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

```
package saying

import (
    "testing"
    "fmt"
)

func TestGreet(t *testing.T){
    s := Greet("James")
    if s != "Welcome my dear James" {
        t.Error("got", s, "expected", "Welcome my dear James")
    }
}

func ExampleGreet(){
    fmt.Println(Greet("James"))
    // Output:
    // Welcome my dear James
}

func BenchmarkGreet(b *testing.B){
    for i := 0; i < b.N; i++ {
        Greet("James")
    } 
}
```

```go
$ go test -bench .
```

***

## 251. Coverage

***

## 252. Benchmark examples

```go
$ go test -bench .
```

***

## 253. Review

* Remember to BET
    - Benchmark
    - Example
    - Test

```go
BenchmarkXxx(b *testing.B)
ExampleXxx()
TestXxx(t *testing.T)
```

```
$ go test
$ go test -bench .
$ go test -cover
$ go test -coverprofile c.out
$ go tool cover -html=c.out
$ godoc -http=:8080
```

***
