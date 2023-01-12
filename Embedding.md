# [Embedding](https://go.dev/doc/effective_go#embedding)

## Interface Embedding

[io.Reader](https://pkg.go.dev/io#Reader)

```go
type Reader interface {
    Read(p []byte) (n int, err error)
}
```

[io.Writer](https://pkg.go.dev/io#Writer)

```go
type Writer interface {
    Write(p []byte) (n int, err error)
}
```

[io.ReadWriter](https://pkg.go.dev/io#ReadWriter)

`ReadWriter` is the interface that combines the `Reader` and `Writer` interfaces.

```go
type ReadWriter interface {
    Reader
    Writer
}
```

* It is a union of the embedded interfaces. 
* Only interfaces can be embedded within interfaces.

***

[bufio.Reader](https://pkg.go.dev/bufio#Reader)

```go
type Reader struct {
	// contains filtered or unexported fields
}
```

[bufio.Writer](https://pkg.go.dev/bufio#Writer)

```go
type Writer struct {
	// contains filtered or unexported fields
}
```

[bufio.ReadWriter](https://pkg.go.dev/bufio#ReadWriter)

```go
type ReadWriter struct {
	*Reader
	*Writer
} 
```

The `ReadWriter struct` could be written as

```go
type ReadWriter struct {
    reader *Reader
    writer *Writer
}
```

```go
func (rw *ReadWriter) Read(p []byte) (n int, err error) {
    return rw.reader.Read(p)
}
```

* The methods of embedded types come along for free, which means that `bufio.ReadWriter` 
not only has the methods of `bufio.Reader` and `bufio.Writer`, 
it also satisfies all three interfaces: `io.Reader`, `io.Writer`, and `io.ReadWriter`.
