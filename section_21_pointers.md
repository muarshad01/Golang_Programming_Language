## 169. What are pointers (reference types)

* All values are stored in memory. 
    * Post office boxes are good analogy for memory
        * Every location in memory has an address. 
        * $\color{red}{A\ pointer\ is\ a\ memory\ address.}$

* Lexical elements
    * Address operator (`&`) 
        * The `&` operator is used to get the memory address of a variable. If `x` is an integer variable then `&x` will give you a pointer to `x` - that is, a memory address where the integer `x` is stored.
    * Dereferencing operator(`*`)
        * The `*` operate is used to get the value stored at the memory address. If `p` is a pointer to an integer then `*p` gives you the integer that `p` points to.

***

## 170. Seeing type & value for pointers

* https://go.dev/play/p/9m9q3ej5zdK

```go
func main() {
	a := 42
	fmt.Println(a)
	fmt.Println(&a) // & gives you the address

	fmt.Printf("%T\n", a)
	fmt.Printf("%T\n", &a)
}
```

***

## 171. Dereferencing pointers

```go
func main() {
	a := 42
	fmt.Println(a)
	fmt.Println(&a) // & gives you the address

	fmt.Printf("%T\n", a)
	fmt.Printf("%T\n", &a)

	b := &a
	fmt.Println(b)
	fmt.Println(*b) // * gives you the value stored at an address when you have the address
	fmt.Println(*&a)

	*b = 43
	fmt.Println(a)
}
```

* `b` is of type int pointer (`*int`)
    * b points to the memory address where an int is stored
	* to see the value in that memory address, add a `*` in front of b
	* `*int` -- the * is part of the type

***

## 172. Pass by value, pointers / reference types, and mutability

* **Pointers**: A pointer holds the memory address of a value. It allows you to directly access and modify the memory location of a value.

* **Slices**: A slice is a descriptor of an array segment. It includes a pointer to the array, the length of the segment, and its capacity (the maximum length of the segment).

* **Maps**: A map is a powerful data structure that associates values of one type (the key) with values of another type (the value). It's an unordered collection of key-value pairs.

* **Channels**: Channels are used for communication between goroutines (Go's term for threads). They allow you to pass data from one goroutine to another.

* **Functions**: In Go. function are first-class citizens, meaning they can be assigned to variables, passed as arguments to other functions, and returned as values form other functions. When a function is assigned to a variable, the variable stores a reference to the function.

* **Interfaces**: An interface type represents a set of method signatures. It provides a way to specify the behavior of an object. If something can do this, then it can be used here.

## 173. Pointer & value semantics defined

* **Value Semantics**: Value semantics in Go refers to when the actual data of a variable is passed to a function or assigned to another variable. This means that the new variable or function parameter gets completely $\color{red}{independent\ copy\ of\ data.}$

```go
package main

func main() {
    // value semantic
    a := 1
    fmt.Println(a)  // 1
    addOne(1)       // 2
    fmt.Println(a)  // 1
    
    // pointer semantic
    b := 1
    fmt.Println(b)  // 1
    addOne(&b)
    fmt.Println(b)  // 2
}

// value semantics
func addOne(v int) int {
    return v + 1
}

// pointer semantics
func addOneP(v *int) int {
    return *v += 1
}
```
 
***

## 174. Pointer & value semantics heuristics

* **Pointer Semantics**: Pointer semantics in Go, on the other hand, involve passing the memory address (a "pointer") rather than the data itself. This means that you can modify the original data, not just a copy of it.

* There are some general guidelines you can follow when deciding whether to use pointer or value semantics in Go:
    * **Value semantics** are simpler and usually safer, since they don't involve shared state or require you to think about memory management.
        * if a function doesn't need to modify its input, or the data you're working with is small (like built-in types or small structs), use value semantics.
        * use value semantics for builtin types (numeric, string, bool) and reference types (slices, maps, channels, pointer, interfaces, functions)

2. Use Pointer Semantics for Large Data:
● Copying large structs or arrays can be inefficient.
● If the data you're working with is large, you might want to use pointer semantics to
avoid the cost of copying the data. A rule of thumb: 64 bytes or larger, use pointers.
3. Use Pointer Semantics for Mutability:
● If a function or method needs to modify its receiver or an input parameter, you'll need
to use pointer semantics.
● This is a common use case for methods that need to update the state of a struct.
4. Consistency:
● It's important to be consistent. If some functions on a type use pointer semantics and
others use value semantics, it can lead to confusion. Typically,
5. Pointer Semantics When Interfacing With Other Code:
● If you're interfacing with other code (like a library or a system call), you might need to
use pointer semantics. For example, the `json.Unmarshal` function in the Go standard library requires a pointer to a value to populate it with unmarshalled data.
Remember, these are just guidelines. The specifics can depend on the situation, and sometimes you may have good reasons to make different choices. But these guidelines provide a good starting point.

***

## 175. Pointers, values, the stack, & the heap

***

## 176. Exploring method sets part 1

***

## 177. Exploring method sets part 2

***

# -----------------------
133. When to use pointers
# -----------------------

* code
    * https://play.golang.org/p/lxsWkhTaYv
    * https://play.golang.org/p/XuI19kjFmb

# --------------
134. Method Sets
# --------------

* Method sets determine what methods attach to a TYPE. It is exactly what the name says: What is the set of methods for a given type? That is its method set.

* IMPORTANT: “The method set of a type determines the INTERFACES that the type implements.....”

* NON-POINTER RECEIVER
    * works with values that are POINTERS or NON-POINTERS.
* POINTER RECEIVER
    * only works with values that are POINTERS.

* Receivers 
---------
(t  T) -- T and *T 
(t *T) -- *T

code
* NON-POINTER RECEIVER & NON-POINTER VALUE: https://play.golang.org/p/2ZU0QX12a8
* NON-POINTER RECEIVER & POINTER VALUE: https://play.golang.org/p/glWZmm0gY6
* POINTER RECEIVER & POINTER VALUE: https://play.golang.org/p/pWFxsg6MSe
* POINTER RECEIVER & NON-POINTER VALUE: https://play.golang.org/p/G3lEy-4Mc8 ( code does not run )
    * this codes does run - notice the difference - method set determines the 
* INTERFACES that the type implements
    * https://play.golang.org/p/KK8gjsAWBZ
