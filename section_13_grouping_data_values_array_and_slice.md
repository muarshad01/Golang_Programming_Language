## 93. Review and preview

***

## 94. Introduction to grouping values

* Arrays
    * https://go.dev/ref/spec#Array_types
* Slice
    * https://go.dev/ref/spec#Slice_types
* Map
    * https://go.dev/ref/spec#Map_types
* Struct
    * https://go.dev/ref/spec#Struct_types

***

## 95. Array - an introduction to arrays

* Arrays are mostly used as a building block in the Go programming language. In some instances, we might use an array, but mostly the $\color{red}{recommendation\ is\ to\ use\ slices\ instead\.}$ 

* https://play.golang.org/p/f-7aufl2DO

***

## 96. Hands-on exercise

***

## 97. Slice - composite literal

* We will use a $\color{red}{COMPOSITE\ LITERAL}$ to create a slice. A composite literal is created by having the **TYPE followed by `{}` and then putting the appropriate values in the curly brace area.

```go
xs := []string{"hello", "world"}
```

***

## 99. Slice - for range & access values by index position

```go
for i, v := range xs {
    fmt.Print("index %v - value %v\n", i, v)
}
```

* blank identifier(`_`) to not use a returned  value
```go
for _, v := range xs {
    fmt.Print("value %v\n",v)
}
```

***

## 100. Slice - append to a slice

```go
xi := []int{42,43,44}
xi = append(xi,45,46,47)
```

***

## 101. Slice - slicing a slice

* Cuts part of slice away

```go
func main(){
    xi := []int{0,1,2,3,4,5,6,7,8,9}

    // [inclusive:exclusive]
    fmt.Printf("xi - %#v\n", xi)
    
    // [:exclusive]
    fmt.Printf("xi - %#v\n", xi[:7])
    
    // [inclusive:]
    fmt.Printf("xi - %#v\n", xi[4:])
    
    // [:]
    fmt.Printf("xi - %#v\n", xi[:])
}
```

*** 

## 102. Slice - deleting from a slice

* We can delete from a slice using both append and slicing. 
* This is a wonderful and elegant example of why Go is great and how Go provides ease of programming.

```go
func main() {
	x := []int{0,1,2,3,4,5,6,7,8,9}
	fmt.Println(x)

	// delte 4
	x = append(x[:4], x[5:]...)
	fmt.Println(x)
}
```

***

## 103. Slice - make

* Slices are built on top of arrays. A $\color{red}{slice\ is\ dynamic}$ in that it will grow in size.
* The underlying array, however, does not grow in size. 
* When we create a slice, we can use the built in function `make()` to specify how large our slice should be and also how large the underlying array should be. This can enhance performance a little bit.

```go
make([]T, length, capacity)
make([]int, 50, 100)
```

***

## 104. Slice - multidimensional slice

* A multidimensional slice is like a spreadsheet. 
    * $\color{red}{You\ can\ have\ a\ slice-of-a-slice\ of\ some\ type.}$
    * Does that sound confusing? Watch this video and it will all be clarified.

```go
func main() {
	a := []string{"1", "2", "3", "4"}
	fmt.Println(a)

	b := []string{"5", "6", "7", "8"}
	fmt.Println(b)

	c := [][]string{a, b}
	fmt.Println(c)
}
```

***

## 105. Slice - slice internal & underlying array - 01

***

## 106. Slice - slice internal & underlying array - 02

***

## 105. Slice - slice internal & underlying array - 03
