# Go-Programming-Language
Learn How To Code: Google's Go (golang) Programming Language [GitHub code link](https://github.com/goestoeleven)

* [Grit - Angela Duckworth](https://www.youtube.com/watch?v=H14bBuluwB8)
* Bill Gates & Warren Buffet -> ONE Attribute for success (_FOCUS_)

***

# Install the latest version of Go

* [Go download & Install](https://go.dev/doc/install)

Open the package file you downloaded and follow the prompts to install Go. The package installs the Go distribution to `/usr/local/go`. The package should put the `/usr/local/go/bin` directory in your `PATH` environment variable. You may need to restart any open Terminal sessions for the change to take effect.

Verify that you've installed Go by opening a command prompt and typing the following command:
`$ go version`

Confirm that the command prints the installed version of Go.

```
$ go version
$ go env
$ go env GOROOT
$ go env GOPATH

$ vim ~./bash_profile
$ export GOROOT=/usr/local/go
$ export GOPATH=$HOME/go
$ export PATH=$PATH:$GOPATH/bin
$ source ~/.bash_profile
```

***

# Go Modules

```
$ cd $GOPATH/src
$ mkdir project && cd project
$ touch main.go

$ go run main.go
$ go mod init
$ go mod tidy
```
OR

```
Example:
--------
$ mkdir -p $GOPATH/src/github.com/muarshad01
$ cd $GOPATH/src/github.com/muarshad01
$ git clone git@github.com:muarshad01/GoLang_Web_Dev.git
$ cd GoLang_Web_Dev
$ touch main.go   # Create other files & folders
$ go mod init
$ go mod tidy
```

***

## Useful commands
```
$ go help
$ go fmt <filename>
$ go fmt ./...          # formats `go` code
$ go vet                # reports suspicious structs
$ go lint               # reports poor coding style
$ go run <filename>			# builds -> run your code -> gets rid of any of the files
$ go build				# if there are no errors, it puts an executable into the "current folder"
$ go install <filename>			# puts the executable in $GOPATH / bin

```

## Packages & Documentation
```
https://godoc.org/<pkg-name>
https://godoc.org/fmt
https://godoc.org/net/http
https://godoc.org/text/template
https://godoc.org/html/template

https://golang.org --> Documents (Docs) --> Package Documentation --> fmt --> index
```

## NOTES
```
1. Go is STATIC programming language
2. Everything in Go is "passed by value"
3. There is no "while" or "do-while"
4. Go has "fallthrough" in switch statement
5. "default" case may appear anywhere in a switch statement
6. case can be presented in comma-seperted lists.
7. Everything in Go is PASS BY VALUE (PASS BY COPY or PASS BY REFERENCE throw them away!)
8. There is no try-catch-finally in go
```

## Books & Courses
* [Web Development w/ Google’s Go (golang) Programming Language -- Udemy(~20 hrs)](https://www.udemy.com/course/go-programming-language/)
* [Go: The Complete Developer's Guide (Golang) -- Udemy(~9 hrs)](https://www.udemy.com/course/go-the-complete-developers-guide/)
* [Learn How To Code: Google's Go (golang) Programming Language -- Udemy(~22 hrs)](https://www.udemy.com/course/learn-how-to-code/)
* [The Go Programming Lanauge by Brian W. Kernighan - Book](https://beyondkmp.com/books/golang/The.Go.Programming.Language.pdf) & [code](https://github.com/GoesToEleven/gopl.io)
* [Welcome to Golang Programs](https://www.golangprograms.com/)
* [Learn Go with Tests](https://quii.gitbook.io/learn-go-with-tests/)
* [Go Language Patterns](http://www.golangpatterns.info/)
* [Go By Example](https://gobyexample.com/)
* [Go Language Specifiction](https://go.dev/ref/spec)
* [Effective Go](https://go.dev/doc/effective_go)
* [An Introduction to Progrmming in Go by Caleb Doxey](https://www.golang-book.com/public/pdf/gobook.pdf)
* [Pro Go: The Complete Guide to Programming Reliable and Efficient Software Using Golang 1st ed. Edition](https://www.amazon.com/Pro-Go-Complete-Programming-Efficient/dp/1484273540)
* [Practical Go: Building Scalable Network and Non-Network Applications 1st Edition](https://amsaha.bitbucket.io/)
* [Efficient Go - 2022](https://www.oreilly.com/library/view/efficient-go/9781098105709/)
* [Concurrency in Go; Tools and Techniques for Developers by Katherine Cox-Buday (O’Reilly 2017)](https://www.amazon.com/Concurrency-Go-Tools-Techniques-Developers/dp/1491941197)
* [Go in Action](https://www.manning.com/books/go-in-action)
* [How to Write a Book: Introduction](https://www.doxsey.net/blog/how-to-write-a-book--introduction/)
* [Mastering Go: Harness the power of Go to build professional utilities and concurrent servers and services, 3rd Edition 3rd ed. Edition]()
* [Learning Go: An Idiomatic Approach to Real-World Go Programming 1st Edition]() 
* [Design Patterns](https://golangbyexample.com/all-design-patterns-golang/)
* [All Design Patterns in Go (Golang)](https://golangbyexample.com/all-design-patterns-golang/)
* [GoF Design patterns that still make sense in Go](https://dev.to/mauriciolinhares/gof-design-patterns-that-still-make-sense-in-go-27k5)
* [Learn Go with tests](https://quii.gitbook.io/learn-go-with-tests/)
* [Learn Web Programming in Go by Examples](https://gowebexamples.com/)

## Tools
* [JSON-to-Go Convert](https://mholt.github.io/json-to-go/)
* [Go online Playground](https://play.golang.org/)
* [Better Go Playground](https://goplay.tools/)

## Useful Articles
* [Error handling and Go](https://go.dev/blog/error-handling-and-go)
* [Defer, Panic, and Recover](https://go.dev/blog/defer-panic-and-recover)
* [Frequently Asked Questions (FAQ)](https://go.dev/doc/faq#exceptions)
* [Go Forum](https://forum.golangbridge.org/)
* [G BLog](https://go.dev/blog/)
* [Using Go Modules](https://go.dev/blog/using-go-modules)
* [JSON and Go](https://go.dev/blog/json)
