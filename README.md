## Go-Programming-Language

* [The Go Programming Language and Environment- CACM 2022](https://cacm.acm.org/magazines/2022/5/260357-the-go-programming-language-and-environment/fulltext)

***

## Quotes

* $\color{red}{FOCUS}$: One attribute for success. - Bill Gates & Warren Buffet
* Most people `overestimate` what they-can-do-in-a-year, and they `underestimate` what-they-can-do-in-ten-years. - Bill Gates
* You will never win if you never begin.
* It takes time to understand the wisdom-of-masters
* [GRIT - Angela Duckworth](https://www.youtube.com/watch?v=H14bBuluwB8)
* [Developing Your Software Engineering Career: Words of Advice From Seasoned Professionals](https://www.computer.org/csdl/magazine/so/2023/05/10273788/1R6sOd7L64o)

***

* [Section 01: Course Introduction](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_01_course_introduction.md) -- Nov 16, 2023
* [Section 02: Getting going with Go](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_02_getting_going_with_go.md) -- Nov 17, 2023
* [Section 03: Hands-on Exercises](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_03_hands_on_exercies.md) -- Nov 17, 2023
* [Section 04: The Fundamentals of Go](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_04_fundamentals_of_go.md) -- Nov 21, 2023
* [Section 06: Programming Fundamentals for Beginners](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_06_programming_fundamentals_for_begineers.md) -- Nov 21, 2023
* [Section 08: Go Mod and Dependency Management](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_08_go_mod_and_dependency_management.md) -- Nov 22, 2023
* [Section 11: Control Flow](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_11_control_flow.md) -- Dec 08, 2023
* [Section 13: Grouping data values - array & slice](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_13_grouping_data_values_array_and_slice.md) -- Dec 06, 2023
* [Section 15: Grouping data values - map](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_15_grouping_data_values_map.md) -- Dec 14, 2023
* [Section 17: Grouping data values - structs](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_17_grouping_data_values_structs.md) -- Dec 14, 2023
* [Section 19: Functions in the go programming language](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_19_functions_in_the_go_programming_language.md) -- Dec 02, 2023
* [Section 21: Pointers](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_21_pointers.md) -- Dec 03, 2023
* [Section 23: Generics](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_23_generics.md) -- Dec 10, 2023
* [Section 25: Applications](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_25_application.md) -- Nov 29, 2023
* [Section 27: Concurrency](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_27_concurrency.md) -- Nov 24, 2023
* [Section 29: Channels](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_29_channels.md) -- Nov 27, 2023
* [Section 31: Error Handling](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_31_error_handling.md) -- Nov 23, 2023
* [Section 33: Writing Documentation](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_33_writing_documentation.md) -- Nov 22, 2023
* [Section 35: Testing & Benchmarking](https://github.com/muarshad01/Golang_Programming_Language/blob/main/section_35_testing_and_benchmarking.md) -- Nov 28, 2023

***

## Download and Install Go

* `https://go.dev` -> Download -> Apple macOS (ARM64)
* [Go download & Install](https://go.dev/doc/install)

1. Open the package file you downloaded and follow the prompts to install Go. 

The package installs the Go distribution to `/usr/local/go`. The package should put the `/usr/local/go/bin` directory in your `PATH` environment variable. You may need to restart any open Terminal sessions for the change to take effect.

2. Verify that you've installed Go by opening a command prompt and typing the following command:

3. Confirm that the command prints the installed version of Go.
```go
$ go version
$ go env
$ go help
```

***

## Go workspace

* One folder - any name, any location, with three sub-directories
```
<goworkaspace>
    |--bin
    |--pkg
    |--src
```

```linux
$ mkdir -p $HOME/goworkspace
$ cd $HOME/goworkspace
$ mkdir -p bin pkg src
```

* Note: the default go workspace on macOS is `$GOPATH=$HOME/go`

***

## Go ENV variable(s) & PATH setup

* Add the following to `~/.bash_profile` file:

```
export GOROOT=/usr/local/go
export GOPATH=$HOME/goworkspace
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOBIN            
#export PATH=$PATH:$GOPATH/bin

export GO111MODULE="on"
export GOVCS=*:all
# export GOVCS=*:off
```

```
$ source ~/.bash_profile
```

***

## Download and Install VSCode / Extensions

* [VS Code](https://code.visualstudio.com/download)
* [VScode for Golang - How to setup Visual Studio Code for Go](https://www.youtube.com/watch?v=TfCMweSHWHw)

* Go Extension Manager
    * Search `golang`
        * Rich Go language support for Visual Studio Code (Click Install)
    * Search `gotemplate-syntax`
        * Language suppor for go txt/template casualjim (Click Install)  
* Command Palette: `Command + Shift + P`
    * `>Go: Install/Update Tools`
    * `>Preferences`

***

## `vim` configuration

* [Vim Configuration Options](https://www.shortcutfoo.com/blog/top-50-vim-configuration-options/)

Update `~/.vimrc` file:

```vim
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

## `go fmt`; `go vet`; `golint`; `gocritic`; `godoc` commands

```go
$ go help

$ go fmt <filename>
$ go fmt ./...        
 
$ go vet <filename>       # Reports suspicious structs (code correctness)
$ go vet ./...            

$ golint <filename>       # Reports poor coding style (style mistakes)
$ golint ./...

$ gocritic check -enableAll <filename>
$ gocritic check -enableAll ./...
```

### `golint`

```
$ mkdir -p $GOPATH/src/test
$ cd $GOPATH/src/test
$ go mod init test
$ go get -u golang.org/x/lint/golint
$ go install golang.org/x/lint/golint       # go install, puts the executable in $GOPATH/bin
$ echo $GOBIN | grep golint
$ golint main.go
```

### `gocritic`

* [go-critic](https://github.com/go-critic/go-critic)

```go
$ mkdir -p $GOPATH/src/test
$ cd $GOPATH/src/test
$ go mod init test
$ go get -v -u  github.com/go-critic/go-critic/cmd/gocritic
$ go install -v github.com/go-critic/go-critic/cmd/gocritic@latest    # go install, puts the 'executable' in $GOPATH/bin
$ echo $GOBIN | grep gocritic
$ gocritic check -enableAll ./...
```
### `godoc`

```
$ mkdir -p $GOPATH/src/test
$ cd $GOPATH/src/test
$ go mod init test
$ go get golang.org/x/tools/cmd/godoc
$ go install golang.org/x/tools/cmd/godoc
$ echo $GOBIN | grep godoc
$ godoc -http=:8080
```

***

## 41. Running `go` programs (THREE different ways)
```go
$ go run main.go
$ go run ./...
$ go run -race main.go
```
* Build executable and runs it

```go
$ go build                  # macOS: folder-name is executable
```
* Builds executable

### Cross build/compile
```go
$ go env GOARCH GOOS        # macOS: arm64; darwin
```

* Run one of these at the command line to build to a certain OS:
    - `GOOS=darwin go build`
    - `GOOS=linux go build`
    - `GOOS=windows go build`

```go
$ go install                # puts the 'executable' in $GOPATH/bin
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

## Using `go get` command to get course code

* [Git: Learn to Code Go Version 03](https://github.com/GoesToEleven/learn-to-code-go-version-03)

```go
$ mkdir -p $GOPATH/src/learn-to-coge-go-version-03
$ cd $GOPATH/src/learn-to-coge-go-version-03
$ go mod init learn-to-coge-go-version-03

$ go get -d github.com/GoesToEleven/learn-to-code-go-version-03/...     # See the `...`
--> $ cd $GOPATH/pkg/mod/github.com/!goes!to!eleven/!golang!training@v0.0.0-20181204234241-afa19f5c43f3/01_getting-started
```

***

## Testing & Coverage
* [Package testing](https://pkg.go.dev/testing)
* [Example Code](https://github.com/GoesToEleven/go-programming/tree/master/code_samples/009-testing)

```go
$ go test -v            # v: verbost
$ go test -race         # Check RACE condition

$ go test -bench .

$ go test -cover -v
$ go test -coverprofile c.out
$ go tool cover -html=c.out
$ go tool cover -html=c.out -o output.html     # Save the output file

$ go tool cover -h      # h: help

$ godoc -http=:6060

http://localhost:6060/pkg/testing/
```

***

## NOTES

* Go is `STATIC` programming language
* Everything in Go is `passed by value`
* There is no `while` or `do-while` or `until`
* Go has `fallthrough` in switch statement
* `default` case may appear anywhere in a switch statement
* case can be presented in comma-seperted lists.
* There is no `try-catch-finally` in go
* Go language DOESN’T support method overloading
* The language lacks inheritance and focuses on composition
* Go doesn't have a `collections` library
* In Go, if a symbol (variables, types, functions et al) starts with a lowercase letter then it is private outside the package it's defined in.
* In Go, `any` is an alias for `interface{}`

***

## Books & Courses

* [Getting started with GOLANG](https://www.golinuxcloud.com/getting-started-with-golang/)
* [Go: The Complete Developer's Guide (Golang) -- Udemy(~9 hrs)](https://www.udemy.com/course/go-the-complete-developers-guide/)
* [The Go Programming Lanauge by Brian W. Kernighan - Book](https://beyondkmp.com/books/golang/The.Go.Programming.Language.pdf) & [code](https://github.com/GoesToEleven/gopl.io)
* [Golang cheatsheet](https://quickref.me/golang)
* [Welcome to Golang Programs](https://www.golangprograms.com/)
* [Welcome To Golang By Example](https://golangbyexample.com/)
* [Go By Example](https://gobyexample.com/)
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
* [Awesome Distributed System Projects](https://github.com/roma-glushko/awesome-distributed-system-projects)
* [Distributed Systems - Awesome Go](https://awesome-go.com/distributed-systems/)
* [Golang in Action: How to implement a simple distributed system](https://dev.to/tikazyq/golang-in-action-how-to-implement-a-simple-distributed-system-2n0n)

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

## Useful Articles

* [Concurrency is not parallelism](https://go.dev/blog/waza-talk)
* [Error handling and Go](https://go.dev/blog/error-handling-and-go)
* [Defer, Panic, and Recover](https://go.dev/blog/defer-panic-and-recover)
* [Don't defer Close() on writable files](https://www.joeshaw.org/dont-defer-close-on-writable-files/)
* [Frequently Asked Questions (FAQ)](https://go.dev/doc/faq#exceptions)
* [Using Go Modules](https://go.dev/blog/using-go-modules)
* [JSON and Go](https://go.dev/blog/json)
* [Go Proverbs](https://go-proverbs.github.io/)
* [nils in GO](https://go101.org/article/nil.html)

***

## Tooling

* [Makefile - Golang](https://earthly.dev/blog/golang-makefile/)
* [pre-commit](https://pre-commit.com/)
    * [https://github.com/TekWizely/pre-commit-golang](https://github.com/TekWizely/pre-commit-golang)
* [An Overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling)
* [An Overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling#pre-commit-checks)
* [Setting Up Your Go Environment](https://www.oreilly.com/library/view/learning-go/9781492077206/ch01.html)
* [Golang tools to make your code great again](https://dev.to/koddr/helpful-golang-tools-to-make-your-code-great-again-3739)
* [VIM for Go development](https://blog.logrocket.com/using-vim-go-development/)
* [Go online Playground](https://play.golang.org/)
* [Better Go Playground](https://goplay.tools/)

***

### Format Conversion Tools

* [JSON-to-Go-Converter](https://mholt.github.io/json-to-go/)
* [XML-to-Go-Converter](https://jsonformatter.org/xml-to-go)

***

### Performance Tools

* [Go Performance Tools Cheat Sheet](https://steveazz.xyz/blog/go-performance-tools-cheat-sheet/)
* [Program Profiling](https://www.practical-go-lessons.com/chap-36-program-profiling)
* [Awesome Profiling](https://github.com/adriannovegil/awesome-profiling)
* [Go Diagnostics](https://go.dev/doc/diagnostics)
