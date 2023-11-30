## 132. Introduction to functions

* "abstract" code
* code reusability
* more understandable

***

## 133. Syntax of functions in Go

```go
func (r receiver) identifier(p parameter(s)) (r return(s)) {...}
```

### Parameters & arguments
* We define our `func` with **parameters** (if any)
* We call our `func` and pass in **arguments** (in any)
* Everything in Go is **PASS BY VALUE**

```

func syntx

no params, no returns
1 param, no returns
1 param, 1 return
2 params, 2 returns
```

* code:
    * https://play.golang.org/p/Ou7esJnAkv
    * https://play.golang.org/p/dpINmrlSsQ
    * https://play.golang.org/p/eh2Aud2jyr
    * https://play.golang.org/p/7Xl9uVH2pO

***

## 134. Variadic parameter

```go
func (r receiver) identifier(p parameter(s)) (r return(s)) { ... }
```

* You can create a `func` which takes an **unlimited number of arguments**. 
* We use the lexical element operator `...T` to signify a variadic parameter (there `T` represents some type).
* `...T`: Unlimited number of arguments of type `T`
* A function with a parameter (`...T`) is called **variadic** and maybe invoked with zero or more arguments for that parameter
* Final incoming parameter in the function signature
* https://play.golang.org/p/Yi0FsQ2tKq

```go
package main

import (
	"fmt"
)

func main() {
	x := sum(2, 3, 4, 5, 6, 7, 8, 9)
	fmt.Println("The total is", x)
}

func sum(x ...int) int {
	fmt.Println(x)
	fmt.Printf("%T\n", x)

	sum := 0
	for i, v := range x {
		sum += v
		fmt.Println("for item in index position", i, "we are now adding", v, "to the total which is now", sum)
	}
	fmt.Println("The total is", sum)
	return sum
}
```

***

## 135. Unfurling a slice

When you have a slice of some type (`[]T`), you can pass in the individual values in a slice by using the `...` operator.

* https://play.golang.org/p/T-mm6-SH71
* https://play.golang.org/p/Qc5sq_AK_T
* https://play.golang.org/p/euQ8PDQ8RN

***

## 136. Defer

* A `defer` statement invokes a function whose execution is deferred to the moment the surrounding function returns, 
    * either because the surrounding function executed a return statement, 
    * reached the end of its function body, 
    * or because the corresponding **goroutine is panicking**.

* https://play.golang.org/p/AYY3AN4LQ6

```go
package main

import (
	"fmt"
)

func main() {
	defer foo()
	bar()
}

func foo() {
	fmt.Println("foo")
}

func bar() {
	fmt.Println("bar")
}
```

***

## 137. Methods

* A method is nothing more than a FUNC attached to a TYPE. When you attach a func to a
type it is a method of that type. You attach a func to a type with a RECEIVER.
    * https://play.golang.org/p/HIBt2HHiIm

***

## 138. Interfaces & polymorphism

***

## 139. Exploring the stringer interface

***

## 140. Expanding on the stringer interface- wrapper func for logging

***

## 141. Writer interface & writing to a file

***

## 142. Writer interface & writing to a byte buffer

***

## 143. Writer interface & writing to a file or a byte buffer

***

## 144. Anonymous func

```go
func(){
	...
}()
```

```go
func(x int){
	...
}(42)
```

* https://play.golang.org/p/54U7XWrNwZ

***

## 145. func expression

* Assigning a func to a variable
    * https://play.golang.org/p/2ekrbY9SAm

***

## 146. Returning a func

* You can return a func from a func. Here is what that looks like. 

* returning a string
    * step 0: https://play.golang.org/p/w3S9B1Vtyx

* returning a func
    * step 1: https://play.golang.org/p/3Xk0wLFre8
    * step 2 - cleaned up: https://play.golang.org/p/NocmYezUP2
    * step 3 - cleaned up: https://play.golang.org/p/FSjvOfY0wW
    * step 4 - cleaned up: https://play.golang.org/p/7wbv9KNlhK
    * step 5 - cleaned up: https://play.golang.org/p/vW0IGeIAox

***

## 147. Callback

* Passing a func as an argument
* Functional programming not something that is recommended in go, however, it is good to be aware of callbacks
* idiomatic go: write clear, simple, readable code

* pre lecture prep: https://play.golang.org/p/j6IXDY_6H2
* math operators: https://play.golang.org/p/sTDJ3l_rlj
* just sum func: https://play.golang.org/p/TEZChnAYIq
* even numbers: https://play.golang.org/p/RKHjy9Bl6j
* odd numbers: https://play.golang.org/p/Nf3_KrpidO

***

## 148. Closure

* Closure helps us limit the scope of variables
    * scope of x: https://play.golang.org/p/YWuniJtu2R
    * scope of x narrowed to func main: https://play.golang.org/p/4hqrzybcFc
    * code block in code block with y: https://play.golang.org/p/6Hyqe_aU-R
    * enclosing a variable in a block of code: https://play.golang.org/p/fHez3lg8wc

***

## 149. Function fundamentals

***

## 150. Recursion

***

## 151. Wrapper function

***