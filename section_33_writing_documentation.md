## 240. Introduction

***

## 241. `go doc`
```
$ go help doc

$ go doc
$ go doc fmt 
$ go doc fmt Print

$ go doc -src fmt Print
$ go doc -src errors New
```

***

## 242. `godoc`

```go
$ godoc
```

***

## 243. `godoc.org`

* [godoc.org](godoc.org)
    * https://godoc.org/fmt
    * https://godoc.org/net/http
    * https://godoc.org/text/template
    * https://godoc.org/html/template

### Documentation on a Local Server 
```linux
$ mkdir -p $GOPATH/src/test
$ cd $GOPATH/src/test
$ go mod init test
$ go get golang.org/x/tools/cmd/godoc
$ go install golang.org/x/tools/cmd/godoc
$ echo $GOBIN | grep godoc
$ godoc -http=:8080
```

***

## 244. Writing documentation

* Write comments above your code
* Those comments become documentation
* Begin with the name of the element

***
