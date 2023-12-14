## 124. Struct introduction

* A Struct is an aggregate / composite data structure. 
    * Structs allow us to compose together values of different types. 
    * Complex data structures (e.g., slices, maps)

* Composite-literal `{}`: 
    * struct-literal `{}`
    * map-literal `{}`

```go
package main

import (
	"fmt"
)

type person struct {
	first string
	last  string
	age   int
}

func main() {
	p1 := person{
		first: "James",
		last:  "Bond",
		age:   32,
	}

	p2 := person{
		first: "Miss",
		last:  "Moneypenny",
		age:   27,
	}

	fmt.Println(p1)
	fmt.Println(p2)

	fmt.Println(p1.first, p1.last, p1.age)
	fmt.Println(p2.first, p2.last, p2.age)
}
```

***

## 125.Embedded structs

* We can take one struct and embed it in another struct. When you do this the inner type gets
promoted to the outer type.

```go
package main

import (
	"fmt"
)

type person struct {
	first string
	last  string
	age   int
}

type secretAgent struct {
	person
	ltk bool
}

func main() {
	sa1 := secretAgent{
		person: person{
			first: "James",
			last:  "Bond",
			age:   32,
		},
		ltk: true,
	}

	p2 := person{
		first: "Miss",
		last:  "Moneypenny",
		age:   27,
	}

	fmt.Println(sa1)
	fmt.Println(p2)

	fmt.Println(sa1.first, sa1.last, sa1.age, sa1.ltk)
	fmt.Println(p2.first, p2.last, p2.age)
}
```

***

## 126. Anonymous structs

* An anonymous struct is a struct, which is not associated with a specific identifier.

```go
package main

import (
	"fmt"
)

type person struct {
	first string
	last  string
	age   int
}

func main() {

	p1 := struct {
		first string
		last  string
		age   int
	}{
		first: "James",
		last:  "Bond",
		age:   32,
	}

	p2 := person {
		first: "Jenny",
		last:  "Moneypenny",
		age:   27,
    }
    
	fmt.Println(p1)
	fmt.Println(p2)
	
    fmt.Println("%T \n", p1)
	fmt.Println("%T \n", p2)
}
```

***

## 127. Composition

* composite data types, aggregate data types, aka, complex data types
    * e.g., slices, maps, structs

````diff
+ * composition is a way of structuring and building complex types by combining multiple simpler types

```go
type Engine struct {
    // Engine fields
}

//
func (e *Engine) Start() {
    fmt.Println("Engine started")
}

type Car struct {
    Engine // Embedding the Engine struct
    // Car-specific fields
}

func main() {
    car := Car{}
    car.Start() // Calling the Start() method from the embedded Engine struct
}
```

* It’s all about type
    * Is go an object oriented language? 
        * Go has OOP aspects, but it’s all about $\color{red}{TYPE}$. 
        * We create TYPES in Go, i.e. user-defined TYPES. 
        * We can then have VALUES of that type. 
        * We can assign VALUES of a user-defined TYPE to a VARIABLE. 

* Go is Object Oriented
    * Encapsulation
	    * state ("fields")
	    * behavior ("methods")
		* exported & unexported; viewable & not viewable
	* Reusability
	    * inheritance ("embedded types")
	* Polymorphism 
	    * interfaces
	* Overriding
	    * promotion

### Traditional OOP 

* Classes
    * data structure describing a type of object
	* you can then create instances / objects from the class / blueprint
	* classes hold both:
	    * state / data / fields
		* behavior / methods / functions
	* public / private
* Inheritance

* In Go,
    * you don't create classes, you create a TYPE
    * you don't instantiate, you create a VALUE of a TYPE
