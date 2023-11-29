## 189. JSON documentation

* [package json](https://pkg.go.dev/encoding/json?utm_source=godoc)

***

## 190. JSON marshal

* [func Marshal](https://pkg.go.dev/encoding/json#Marshal)

```go
func Marshal(v any) ([]byte, error)
```
    
* https://play.golang.org/p/jtE_n16cQO

***

## 191. JSON unmarshal

[func Unmarshal](https://pkg.go.dev/encoding/json#Unmarshal)
```go
func Unmarshal(data []byte, v any) error
```

* [JSON to Go](https://mholt.github.io/json-to-go/)
* https://github.com/goestoeleven
* https://play.golang.org/p/O9q0DmpzsZ

***

## 192. Writer interface

[type Writer](https://pkg.go.dev/io#Writer)
```go
type Writer interface {
    Write(p []byte) (n int, err error)
}
```
* `type Writer` is an interface. So, any other type with `Write(p [byte]) (n int, err error)` method attached to it is also of `type Wrtier`.

```go
func Create(name string) (*File, error)

func (f *File) Write(b []byte) (n int, err error)
```
* Any value of `type *File` which has `Write(b []byte) (n int, err error)` method attached to it
    * is value is also of `type Writer`.
* https://play.golang.org/p/3Txh-dKQBf

```go
package main

import (
	"fmt";
	"io";
	"os";
)

func main() {
	fmt.Println("Hello, playground")
	fmt.Fprintln(os.Stdout, "Hello, playground")
	io.WriteString(os.Stdout, "Hello, playground")
}
```

***

## 193. Sort

The sort package allows us to sort slices.
 
starting code:https://play.golang.org/p/igIGnMv6AN
sorted: https://play.golang.org/p/8UkvEdzQOk

## 194. Sort custom

Here is how we sort on fields in a struct. 

code:
● starting code: https://play.golang.org/p/UhXN-G2FwY
● sorted
	○ by age: https://play.golang.org/p/kqmJovOU5V
	○ by name: https://play.golang.org/p/he70VcFmdM

## 195. bcrypt

***
