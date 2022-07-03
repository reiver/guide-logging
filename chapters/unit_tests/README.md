# Unit Tests ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

**Unit Testing** are tests that are used to test a piece of a software system.
(These _pieces_ of the software system get called _“units”_ — thus the name “unit test”.)

Go has built-in support for **unit testing**.

In this chapter you are going to create **uni tests**  for your `log` package.

## Go Test Files

With Go, **unit tests** are put in files that end in `_test.go`

So, for example, you might have a **test file** name:

* `apple_test.go`,
* `banana_test.go`, and 
* `cherry_test.go`.

You might, for example, even have a **test file** named:

* `one_two_three_test.go`.

Notice that all ended in `_test.go`

That is one of the important parts.

## Test Files Ignored

Normally, when you build a Go program, using `go build`, all the `*_test.go` files are ignored.

(This is a good thing.)

Go only pays attention to the `*_test.go` files when it runs the tests — using `go test`.

## import "testing"

All Go unit tests need to import the ["testing"](https://golang.org/pkg/testing/) package:
```go
import "testing"
```

## func Test*()

Inside the `*_test.go` file, each test is put inside a function whose name starts with `Test`.

So, for example, if we are testing the `Logf()` method of the type `Logger` we might name our test:
```go
func TestLogger_Logf(t *testing.T) {
	//@TODO
}
```

And, for example, if we are testing the `Punch()` function, we might name our test:
```go
func TestPunch(t *testing.T) {
	//@TODO
}
```

And if we wanted to have 3 different tests for `the Log()` method we might have the following 3 different Test functions:
```go
func TestLogger_Log_apple(t *testing.T) {
	//@TODO
}

func TestLogger_Log_banana(t *testing.T) {
	//@TODO
}

func TestLogger_Log_cherry(t *testing.T) {
	//@TODO
}
```

Etc.

## Running Tests

To run your unit tests, you will use the following command from the command line:
```
go test
```

The output from running this program will tell you if any tests failed.

**Write units tests to make sure your logger is working as you expect it to work.**

You will need to figure out how to capture the output from your `Log()` and `Logf()` functions. You can use [strings.Builder](https://golang.org/pkg/strings/#Builder) to do this; as a pointer to [strings.Builder](https://golang.org/pkg/strings/#Builder) is an `io.Write` — i.e.,:—
```go
var output strings.Builder

var writer io.Writer = &output
```

## Assignment

Write unit tests for every function and method for your `log` package.

## Logger Test Code

So, your test file(s) will look something like this:
```go
package log_test

//@TODO: import your logger

import "testing"

func TestLogger_Begin(t *testing.T) {
	//@TODO: you will need to figure out what goes here.
}

func TestLogger_End(t *testing.T) {
	//@TODO: you will need to figure out what goes here.
}

func TestLogger_Log(t *testing.T) {
	//@TODO: you will need to figure out what goes here.
}

func TestLogger_Logf(t *testing.T) {
	//@TODO: you will need to figure out what goes here.
}

```

## Hints

Here are some references that can help you with your task in this chapter.

* [Go by Example: Testing](https://gobyexample.com/testing)
* [Add a Test](https://golang.org/doc/tutorial/add-a-test)
* [Table Driven Tests](https://github.com/golang/go/wiki/TableDrivenTests)
* [import "testing"](https://golang.org/pkg/testing/)
* [strings.Builder](https://golang.org/pkg/strings/#Builder)

## Check-List

* [ ] Did you create at least one new file that ends with a `_test.go`?
* [ ] Were all the tests you wrote put into a file that ended with `_test.go`?
* [ ] Did you run `go test`?
* [ ] Did all your tests pass?
* [ ] Did you `git commit` all of your new test files that end with `_test.go` into the git repository for your **logger** repo?
* [ ] Did you `git push` your file new test files that end with `_test.go`?
