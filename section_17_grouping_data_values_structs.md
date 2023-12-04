## 124. Struct introduction

A struct is an composite data type. (composite data types, aka, aggregate data types, aka,
complex data types). Structs allow us to compose together values of different types. 

* https://play.golang.org/p/hNI_rSK-C6

***

## 125.Embedded structs

We can take one struct and embed it in another struct. When you do this the inner type gets
promoted to the outer type.

* https://play.golang.org/p/u6b3qTr1CH

***

## 126. Anonymous structs

We can create anonymous structs also. An anonymous struct is a struct which is not
associated with a specific identifier.

* NAMED: https://play.golang.org/p/O7DiZX_e1R
* ANONYMOUS: https://go.dev/play/p/OfqUspH-JIw

***

## 127. Composition

***

# --------------
104.Housekeeping
# --------------

It’s all about type

Is go an object oriented language? 
	Go has OOP aspects. But it’s all about TYPE. We create TYPES in Go; user-defined TYPES. 
We can then have VALUES of that type. We can assign VALUES of a user-defined TYPE to VARIABLES. 

Go is Object Oriented
	Encapsulation
		a. state ("fields")
		b. behavior ("methods")
		c. exported & unexported; viewable & not viewable

	Reusability
		a. inheritance ("embedded types")
	Polymorphism 
		a. interfaces
	Overriding
		a. "promotion"

Traditional OOP 
1. Classes
	a. data structure describing a type of object
	b. you can then create "instances"/"objects" from the class / blueprint
	c. classes hold both:
		i. state / data / fields
		ii. behavior / methods
	d. public / private
2. Inheritance

InGo:
1. you don't create classes, you create a TYPE
2. you don't instantiate, you create a VALUE of a TYPE

