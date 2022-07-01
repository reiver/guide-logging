# Simple Logger ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

Let's start by **№1** creating a **simple logger**, and then **№2** creating a (very simple) program that uses that logger.

The program you will create (that uses that **logger** you created) will log the following:—

At the beginning of the program it will **log**:
> BEGIN

In the middle of the program it will **log**:
> I said "Hello world!"

And at the end of the program it will **log**:
> END

And it will look something like:
```go
package main

func main() {
	log.Begin()
    
	var msg string = "Hello world!"
	fmt.Println(msg)
	log.Log("I said:", msg)
    
	log.End()
}
```

(**Notice that there is a `fmt.Println()` that outputs `Hello world!`, and there is also a `log.Log()` that outputs `I said: Hello world!`.**)

The **logger** you create will be represented by Go a type:
```go
package log

type Logger struct {
    //@TODO: you will need to figure out what goes here.
}
```

This **logger** will provide methods to output text BUT **you will write it in a way that you have the ability to turn on and off the outputted text, and decide _where_ you want the output to go (such a `os.Stdout`, or a file, or a memory buffer, etc)**.

The first method your logger will have is:
```go
func (receiver Logger) Log(a ...interface{}) {
    //@TODO: you will need to figure out what goes here.
}
```

The other two methods your logger will have are:
```go
func (receiver Logger) Begin() {
    //@TODO: you will need to figure out what goes here.
}
```

```go
func (receiver Logger) End() {
    //@TODO: you will need to figure out what goes here.
}
```

These other two methods should use the `.Log()` method (you created before) to do their outputting.

## Hints

Here are some references that can help you with your task in this chapter.

* [fmt.Fprintln()](https://golang.org/pkg/fmt/#Fprintln) — `fmt.Fprintln()` is similar to `fmt.Println()` except `fmt.Fprintln()` lets you tell it where to send the output.
* [os.Stdout](https://golang.org/pkg/os/#Stdout) — `os.Stdout` is where `fmt.Printf()` & `fmt.Println()` send their output.
* [ioutil.Discard](https://golang.org/pkg/io/ioutil/#Discard)
* [io.Writer](https://golang.org/pkg/io/#Writer)
* [Quick-and-Dirty Debugging in Golang](https://changelog.ca/log/2015/03/09/golang)
