## 214. Understanding channels

# Channels

Channels BLOCK  # Example: Relay RACE example, one runner is waiting for another...

* [Channel types](https://go.dev/ref/spec#Channel_types)
* [Channels](https://go.dev/doc/effective_go#channels)

***

## 215. Directional channels

```go
c := make(chan int)     // bi-directional
cr := make(<-chan int)  // receive
cs := make(chan<- int)  // send

// specific to general doesn't assign
c = cr
c = cs

// specific to specific doesn't assign
cs = cr

// general to specific assigns
cr = c
cs = c

// general to specific converts
(<-chan int)(c)
(chan<- int)(c)
```

***

## 216. Using channels

```go
package main

func main() {
    c := make(chan int) // bi-directional

    // send
    go foo(c)    
    
    // receive
    bar(c)      // This blocks (waits for send channel data to arrive!)
    
    fmt.Println("about to exist")
}

// send
func foo(c chan<- int) {    // general to specific
    c<- 42
}

// receive
func bar(c <-chan int) {      // general to specific
    fmt.Println(<-c)
}
```

***

## 217. Range

***

## 218. Select

***

## 219. Comma ok idiom

***

## 220. Fan in

***

## 221. Fan out

***

## 222. Context

[type Context](https://pkg.go.dev/context#Context)
```go
type Context
  func Background() Context
  func TODO() Context
  func WithValue(parent Context, key, val any) Context
```

***
