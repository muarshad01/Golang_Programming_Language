# Go-Programming-Language
Learn How To Code: Google's Go (golang) Programming Language [GitHub code link](https://github.com/goestoeleven)

* [The Go Programming Language and Environment- CACM 2022](https://cacm.acm.org/magazines/2022/5/260357-the-go-programming-language-and-environment/fulltext)
* [Grit - Angela Duckworth](https://www.youtube.com/watch?v=H14bBuluwB8)
* Bill Gates & Warren Buffet -> **ONE Attribute for success (*FOCUS*)**

***

## Install the latest version of Go

* https://go.dev
  - [Download](https://go.dev/dl/)
* [Go download & Install](https://go.dev/doc/install)

Open the package file you downloaded and follow the prompts to install Go. The package installs the Go distribution to `/usr/local/go`. The package should put the `/usr/local/go/bin` directory in your `PATH` environment variable. You may need to restart any open Terminal sessions for the change to take effect.

Verify that you've installed Go by opening a command prompt and typing the following command:
`$ go version`

Confirm that the command prints the installed version of Go.

```go
$ go version
$ go env
$ go help
```

***

## Downlad & Install VSCode / Extensions

* [VS Code](https://code.visualstudio.com/download)
* [VScode for Golang - How to setup Visual Studio Code for Go](https://www.youtube.com/watch?v=TfCMweSHWHw)

* Go Extension Manager
  - Search `golang` 
    - Rich Go language support for Visual Studio Code
      - Click Install
* Go Extension Manager
  - Preferences 
* Command Palette: Command + Shift + P
  - **Go: Install/Update Tools**
* Go Extension Manager
  - Search `gotemplate-syntax` (by casualjim) 
    - Click Install 

***

### VIM Editor

[Vim Configuration Options](https://www.shortcutfoo.com/blog/top-50-vim-configuration-options/)

```go
$ vim ~/.vimrc

syntax on

" tabs
filetype plugin indent on
set tabstop=4
set shiftwidth=4
set expandtab

" search
set hlsearch
set ignorecase

" Use colors that suit a dark background.
" set background=dark

" Enable spellchecking.
set spell

" Increase the undo limit.
set history=100
```

***

## Go workspace

```
<goworkaspace>	# one folder - any name, any location, with three sub-directories
  |--bin
  |--pkg
  |--src

$ mkdir -p $HOME/goworkspace
$ mkdir -p $HOME/goworkspace/bin pkg src
```

**Note**: the default go workspace on macOS is $GOPATH=$HOME/go

***

## Go ENV variable(s) & PATH setup

```
$ vim ~/.bash_profile

export GOROOT=/usr/local/go
export GOPATH=$HOME/goworkspace
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOPATH/bin
export GO111MODULE="on"

$ source ~/.bash_profile
```

***

## go fmt; go vet; go lint commands
```go
$ go help
$ go fmt <filename>
$ go fmt ./...         
$ go vet <filename>       # reports suspicious structs (code correctness)
$ go vet ./...            
$ golint <filename>       # reports poor coding style (style mistakes)
$ golint ./...
$ gocritic check -enableAll <filename>
$ gocritic check -enableAll ./...
```

***

## golint

```go
$ mkdir -p $GOPATH/src/<folder>             # E.g., install_golint
$ cd $GOPATH/src/<folder>
$ go mod init <folder>
$ go get -u golang.org/x/lint/golint
$ go install golang.org/x/lint/golint       # go install, puts the 'executable' in $GOPATH/bin
$ echo $GOBIN | grep golint
$ golint main.go
```

***

## go-critic

* [go-critic](https://github.com/go-critic/go-critic)

```go
$ mkdir -p $GOPATH/src/<folder>             # E.g., install_gocritic
$ cd $GOPATH/src/<folder>
$ go mod init <folder>
$ go get -v -u github.com/go-critic/go-critic/cmd/gocritic
$ go install -v github.com/go-critic/go-critic/cmd/gocritic@latest    # go install, puts the 'executable' in $GOPATH/bin
$ echo $GOBIN | grep gocritic
$ gocritic check -enableAll ./...
```

***

# Run code (Three different ways)

```go
$ go run main.go
$ go run -race main.go

$ go build                # mac: folder-name is executable
$ go build main.go       

$ go install
$ go install main.go     # puts the 'executable' in $GOPATH/bin
```

***

## Go Modules: Managing and Updating Dependencies
* [Using Go Modules](https://go.dev/blog/using-go-modules)
* [Tutorial: Create a Go module](https://go.dev/doc/tutorial/create-module#prerequisites)
```go
$ mkdir -p $GOPATH/src/HAPPYDOG
$ cd $GOPATH/src/HAPPYDOG
$ go mod init example/username/repo
$ go mod tidy
$ go test
$ go list -m all

Update

$ go list -m all
$ go get golang.org/x/text
$ go test
$ go get rsc.io/sampler
$ go test
$ go list -m -versions rsc.io/sampler
$ go get rsc.io/sampler@v1.3.1
$ go test
$ go list -m all
```

***

## Using 'go get' command to get course code
[cod link](https://github.com/GoesToEleven/GolangTraining)
```go
$ mkdir -p $GOPATH/src/examplegocode
$ cd $GOPATH/src/examplegocode
$ go mod init examplegocode
$ go get -d github.com/GoesToEleven/go-programming/...        # See the '...'
$ cd $GOPATH/pkg/mod/github.com/!goes!to!eleven/!golang!training@v0.0.0-20181204234241-afa19f5c43f3/01_getting-started
```

***

## Testing & Coverage
* [Package testing](https://pkg.go.dev/testing)
* [Example Code](https://github.com/GoesToEleven/go-programming/tree/master/code_samples/009-testing)
```go
$ go test -v
$ go test -race         # Check RACE condition
$ go test -bench=.
$ go test -cover -v
$ go test -coverprofile=c.out
$ go tool cover -html=coverage.out -o output.html     # Save the output file

$ go tool cover -func=c.out
$ go tool cover -html=c.out

$ godoc -http=:6060

http://localhost:6060/pkg/testing/
```
***

## Documentation

```go
$ go help doc

$ go doc fmt 
$ go doc fmt Print

$ go doc -src fmt 
$ go doc -src fmt Print
$ go doc -src errors New

https://godoc.org/fmt
https://godoc.org/net/http
https://godoc.org/text/template
https://godoc.org/html/template

$ mkdir -p $GOPATH/src/test
$ cd $GOPATH/src/test
$ go mod init test
$ go get golang.org/x/tools/cmd/godoc
$ go install golang.org/x/tools/cmd/godoc
$ echo $GOBIN | grep godoc
$ godoc -http=:6060
```

***

## NOTES

```
1. Go is STATIC programming language
2. Everything in Go is "passed by value"
3. There is no "while" or "do-while" or "until"
4. Go has "fallthrough" in switch statement
5. "default" case may appear anywhere in a switch statement
6. case can be presented in comma-seperted lists.
7. Everything in Go is PASS BY VALUE (PASS BY COPY or PASS BY REFERENCE throw them away!)
8. There is no try-catch-finally in go
9. Go language doesn’t support method overloading
10. As the language lacks inheritance and focuses on composition
11. Go doesn't have a `collections` library
12. In Go if a symbol (variables, types, functions et al) starts with a lowercase symbol then it is private outside the package it's defined in.
13. In Go any is an alias for interface{}
```

***

## Books & Courses

* [Go: The Complete Developer's Guide (Golang) -- Udemy(~9 hrs)](https://www.udemy.com/course/go-the-complete-developers-guide/)
* [The Go Programming Lanauge by Brian W. Kernighan - Book](https://beyondkmp.com/books/golang/The.Go.Programming.Language.pdf) & [code](https://github.com/GoesToEleven/gopl.io)
* [Golang cheatsheet](https://quickref.me/golang)
* [--> Welcome to Golang Programs](https://www.golangprograms.com/)
* [--> Welcome To Golang By Example](https://golangbyexample.com/)
* [Go By Example](https://gobyexample.com/)
* [Go Language Specifiction](https://go.dev/ref/spec)
* [Effective Go](https://go.dev/doc/effective_go)
* [An Introduction to Progrmming in Go by Caleb Doxey](https://www.golang-book.com/public/pdf/gobook.pdf)
* [Pro Go: The Complete Guide to Programming Reliable and Efficient Software Using Golang 1st ed. Edition](https://www.amazon.com/Pro-Go-Complete-Programming-Efficient/dp/1484273540)
* [Practical Go: Building Scalable Network and Non-Network Applications 1st Edition](https://amsaha.bitbucket.io/)
* [Efficient Go: Data-Driven Performance Optimization - 2022](https://www.oreilly.com/library/view/efficient-go/9781098105709/)
* [Go in Action](https://www.manning.com/books/go-in-action)
* [How to Write a Book: Introduction](https://www.doxsey.net/blog/how-to-write-a-book--introduction/)
* [Mastering Go: Harness the power of Go to build professional utilities and concurrent servers and services, 3rd Edition 3rd ed. Edition]()
* [Learning Go: An Idiomatic Approach to Real-World Go Programming 1st Edition]() 
* [Build Systems with Go](https://www.amazon.com/Build-Systems-Go-Everything-Gopher/dp/B094L79K1C?dchild=1&keywords=golang&qid=1630693981&sr=8-19&linkCode=sl1&tag=365blottochal-20&linkId=40435c3a918c4078b9d0e0c00b72e0c1&language=en_US&ref_=as_li_ss_tl&asin=B094L79K1C&revisionId=&format=4&depth=1)
*  [Go Programming Language Phrasebook, The (Developer's Library)](https://www.amazon.com/gp/product/0321817141/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0321817141&linkCode=as2&tag=alexellisuk-20&linkId=dba796393bbfd6c44282ca7bef7a6ad3)
* [GoLang (Ultimate Guide) ](https://www.amazon.com/GoLang-Ultimate-Guide-Sufyan-Uzayr/dp/1032312327/ref=sr_1_3?keywords=golang+performance&qid=1673195822&sprefix=golang+perform%2Caps%2C343&sr=8-3)
* [Powerful Command-Line Applications in Go: Build Fast and Maintainable Tools](https://www.amazon.com/Powerful-Command-Line-Applications-Go-Maintainable/dp/168050696X/ref=d_pd_vtp_vft_none_sccl_3_4/138-6340339-5761811?pd_rd_w=eCoAG&content-id=amzn1.sym.8e065679-52e9-4d16-ae63-fa3d08b93cef&pf_rd_p=8e065679-52e9-4d16-ae63-fa3d08b93cef&pf_rd_r=TMHVZDGG799BCJGSZERJ&pd_rd_wg=mASTq&pd_rd_r=f7fb705e-a7bd-43c1-ad51-25e58466a00a&pd_rd_i=168050696X&psc=1)

### Distributed Services

* [Distributed Services with Go: Your Guide to Reliable, Scalable, and Maintainable Systems](https://www.amazon.com/Distributed-Services-Go-Reliable-Maintainable/dp/1680507605/ref=sr_1_1?crid=1Q5SDABL2MXD3&keywords=Distributed+Services+with+Go&qid=1673456986&sprefix=distributed+services+with+go%2Caps%2C63&sr=8-1)

### Concurrency

* [Concurrency in Go; Tools and Techniques for Developers by Katherine Cox-Buday (O’Reilly 2017)](https://www.amazon.com/Concurrency-Go-Tools-Techniques-Developers/dp/1491941197)

### Design patterns

* [Design Patterns](https://golangbyexample.com/all-design-patterns-golang/)
* [Go Language Patterns](http://www.golangpatterns.info/)
* [All Design Patterns in Go (Golang)](https://golangbyexample.com/all-design-patterns-golang/)
* [GoF Design patterns that still make sense in Go](https://dev.to/mauriciolinhares/gof-design-patterns-that-still-make-sense-in-go-27k5)

### Testing

* [Learn Go with tests](https://quii.gitbook.io/learn-go-with-tests/)
  - [https://github.com/quii/learn-go-with-tests](https://github.com/quii/learn-go-with-tests)
* [Comprehensive Guide to Testing in Go](https://blog.jetbrains.com/go/2022/11/22/comprehensive-guide-to-testing-in-go/)

### Web Programming

* [Learn Web Programming in Go by Examples](https://gowebexamples.com/)

***

## Tools

* [JSON-to-Go-Converter](https://mholt.github.io/json-to-go/)
* [XML-to-Go-Converter](https://jsonformatter.org/xml-to-go)
* [Go online Playground](https://play.golang.org/)
* [Better Go Playground](https://goplay.tools/)

***

## Useful Articles

* [Concurrency is not parallelism](https://go.dev/blog/waza-talk)
* [Error handling and Go](https://go.dev/blog/error-handling-and-go)
* -> [Defer, Panic, and Recover](https://go.dev/blog/defer-panic-and-recover)
* [Don't defer Close() on writable files](https://www.joeshaw.org/dont-defer-close-on-writable-files/)
* [Frequently Asked Questions (FAQ)](https://go.dev/doc/faq#exceptions)
* [Go Forum](https://forum.golangbridge.org/)
* [Go Blog](https://go.dev/blog/)
* [Using Go Modules](https://go.dev/blog/using-go-modules)
* [JSON and Go](https://go.dev/blog/json)
* [Go Proverbs](https://go-proverbs.github.io/)

***

## Others

* [Selectors](https://go.dev/ref/spec#Selectors)
* [Types](https://go.dev/ref/spec#Types)

***

## Tooling

* [Creating a Golang Makefile](https://earthly.dev/blog/golang-makefile/)
* [pre-commit](https://pre-commit.com/)
  - [https://github.com/TekWizely/pre-commit-golang](https://github.com/TekWizely/pre-commit-golang)
* [An Overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling)
* [Chapter 1. Setting Up Your Go Environment](https://www.oreilly.com/library/view/learning-go/9781492077206/ch01.html)
* [An Overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling#pre-commit-checks)
* [Helpful Golang tools to make your code great again](https://dev.to/koddr/helpful-golang-tools-to-make-your-code-great-again-3739)
* [Using Vim for Go development](https://blog.logrocket.com/using-vim-go-development/)
* [nils in GO](https://go101.org/article/nil.html)
* [Go Diagnostics](https://go.dev/doc/diagnostics)

***

## Performnce Tools

* [Go Performance Tools Cheat Sheet](https://steveazz.xyz/blog/go-performance-tools-cheat-sheet/)
* [Chapter 36: Program Profiling](https://www.practical-go-lessons.com/chap-36-program-profiling)
