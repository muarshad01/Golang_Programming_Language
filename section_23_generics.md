## 182. Type constraint

* DRY - don't repeat yourself
* repetitive and redundant code

```go
package main

func addI(a, b int) int {
    return a + b
}

func addF(a, b float64) float64 {
    return a + b
}


func addT[T int | float](a, b T) T {
    return a + b
}

func main(){
    fmt.Println(addI(1, 2))
    fmt.Println(addF(1.2, 2.2))

    fmt.Println(addT(1, 2))
    fmt.Println(addT(1.2, 2.2))
}
```

***

## 183. Type constraint & type set interface example

```go
type myNumbers interface {
    int | float64
}

func addT[T myNumbers](a, b T) T {
    return a + b
}
```

***

## 184. Type alias & underlying type constraints

***

## 185. Package constraints

***

## 186. Generics tutorial

***

## 187. Concrete type vs interface type

***
