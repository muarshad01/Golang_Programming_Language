## 189. JSON documentation

* [package json](https://pkg.go.dev/encoding/json?utm_source=godoc)

***

## 190. JSON marshal

* https://play.golang.org/p/jtE_n16cQO

***

## 191. JSON unmarshal

https://mholt.github.io/json-to-go/
https://github.com/goestoeleven

code: https://play.golang.org/p/O9q0DmpzsZ

***

## 192. Writer interface

Understanding the writer interface from package io.

code: https://play.golang.org/p/3Txh-dKQBf video: 121

package main

import (
	"fmt"
	"io"
	"os"
)

func main() {
	fmt.Println("Hello, playground")
	fmt.Fprintln(os.Stdout, "Hello, playground")
	io.WriteString(os.Stdout, "Hello, playground")
}

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
