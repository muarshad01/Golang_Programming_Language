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

***

## 117. Map - delete element

* https://play.golang.org/p/t5g_-8wgOL

***

## 118.  Map - comma ok idiom

* https://play.golang.org/p/RTuBRiW087

***

## 119. Map - counting words in a book

***
