## 64. Previewing code

* no `default` fall through in go.
* a `select` statement chooses which of a set of possible send or receive operations will proceed. It looks similar to a `switch` statement but with the cases all referring to communication operations.

```go
r := rand.New(rand.NewSource(time.Now().UnixNano()))
```

***

## 65. Understanding control flow

* control flow
    * sequence
        * All `Go` programs start in `package main` and `func main() {...}`
        * `func init() {...}` runs before `func main() {...}`.
            * initialized your program before anything runs.
            * [Program initialization and execution](https://go.dev/ref/spec#Program_initialization_and_execution)
    * conditional
    * loop

* **The stack** is a region of memory used for storing variables that are local to a function or a goroutine. When a function is called or a goroutine is created, a new stack frame is created on the stack to store the function arguments, local variables, and other data.
    * The stack is generally faster than the heap because it is managed automatically by Go runtime system, and memory allocation and deallocation is relatively fast.

* **The heap** is a region of memory for storing variables that have longer lifetime than those stored on the stack. When a variable is allocated on the heap, it remains there until it is explicitly deallocated by the program or until the program exits. 
    * The heap is more flexible data structure than the stack, but it is generally slower because it requires more overhead for memory allocation and deallocation.
    * In Go, the heap is managed automatically by the garbage collector, which frees up memory that is no longer being used by the program.

***

## 66. If statements & comparison operator

***

## 67. Understanding & using Logical operators

***

## 68. The `statement; statement` & `comma, ok` idioms

* [If Statement](https://go.dev/ref/spec#If_statements)
```go
if x := f(); x < y {
	return x
} else if x > z {
	return z
} else {
	return y
}
```
* [comma, ok](https://go.dev/doc/effective_go)
```go
func offset(tz string) int {
    if seconds, ok := timeZone[tz]; ok {
        return seconds
    }
    log.Println("unknown time zone:", tz)
    return 0
}
```
***

## 69. Using `switch` statements to make decision in code

***

## 70. Using select statement for concurrency communication

***

## 71. Understanding & using for statement to create loops

***

## 72. Multiple iteration - nesting a loop within a loop

***

## 73. Understanding & using for range loops

***

## 74. Finding a modulus / reminder

***
