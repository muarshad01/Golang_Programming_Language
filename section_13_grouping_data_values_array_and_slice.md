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

Arrays are mostly used as a building block in the Go programming language. In some instances, we might use an array, but mostly the recommendation is to use slices instead. 

* https://play.golang.org/p/f-7aufl2DO

***

## 97. Slice - composite literal

We will use a COMPOSITE LITERAL to create a slice. A composite literal is created by having the TYPE followed by CURLY BRACES and then putting the appropriate values in the curly brace area.

* https://play.golang.org/p/XtUEPJFgqD

## 99. Slice - for range & access values by index position

* https://play.golang.org/p/O7cCALNFsH

## 101. Slice - slicing a slice

* https://play.golang.org/p/AXGTEEn92M

## 83. Slice - append to a slice

* https://play.golang.org/p/oQnjP5Ka3F

102. Slice - deleting from a slice

We can delete from a slice using both append and slicing. This is a wonderful and elegant
example of why Go is great and how Go provides ease of programming.

* https://play.golang.org/p/VTZ2Bof6bN

## 103. Slice - make

Slices are built on top of arrays. A slice is dynamic in that it will grow in size.
The underlying array, however, does not grow in size. When we create a slice, we can use the built in function make to specify how large our slice should be and also how large the underlying array should be. This can enhance performance a little bit.

```go
make([]T, length, capacity)
make([]int, 50, 100)
```

* https://play.golang.org/p/07hH1b-hvD

## 104. Slice - multidimensional slice

A multi-dimensional slice is like a spreadsheet. You can have a slice of a slice of some type. Does that sound confusing? Watch this video and it will all be clarified.

* https://play.golang.org/p/S4cyB89Zpm

