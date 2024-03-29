## 115. Map - introduction

* Composite or aggregate data structure(s): slice, map, ...
* maps are unordered; they'll print out in random order

```go
am := map[string]int{
    "Todd":   42,
    "Henry":  16,
    "Padget": 14,
}
fmt.Println(am)
fmt.Println("%#v\n", am)
```

* Just like we can create slice using a `make()`, we can create a map using `make()` command as well.

```go
an := make(map[string]int)
an["Lucas"] = 28
an["Steph"] = 37
fmt.Println(an)
fmt.Println("%#v\n", an)
```

***

## 116. Map - for range over map

```go
for k, v := range an {
    fmt.Println(k, v)
}
```
* We don't want the key, just the values, then use (`_`)
```go
for _, v := range an {
    fmt.Println(v)
}
```
* We only want to print the keys, then just one variable is defined:
```go
for k := range an {
    fmt.Println(k)
}
```
*** 

* It is very similar to slices as well. Instead of `k` for key, use `i` for index

***

## 117. Map - `delete` element

```go
m := map[string]int{
    "James": 32,
    "Todd":  27,
}
delete(m, "James")

delete(m, "James") // This don't panic
```

***

## 118.  Map - `comma ok` idiom

* If you look up a non-existent key, a zero value will be returned as the value associated with that non-existent key.
```go
v, ok := an["Georgey"]

if ok {
    fmt.Println(v)
} else {
    fmt.Println("key didn't exist")
}
```
* the `comma, ok` idiom is combined with `statement; statement` idiom

```go
if v, ok := an["Georgey"]; !ok {
    fmt.Println("Key didn't exist")
} else {
    fmt.Println("The value prints", v)
}
```

* The reason `statement;statement` idiom is used is because this limits the scope of `v` and `ok` to `if-else {}` block
***

## 119. Map - counting words in a book

* [Word count example](https://github.com/GoesToEleven/learn-to-code-go-version-03/tree/main/117-map-count-words)

***
