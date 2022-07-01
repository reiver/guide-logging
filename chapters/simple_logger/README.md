# Simple Logger ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

With the help of this **guide**, you are going to create a logger.

At first your **logger** will be simple. But we will keep adding to it until it is powerful & sophisticated.

Let's start by **№1** creating a **simple logger**, and then **№2** creating a (very simple) program that uses that (very simple) **logger** (you will create).

The program you will create (that uses the **logger** that you will create) will **log** the following:—

At the beginning of the program it will **log**:
> `BEGIN`

In the middle of the program it will **log**:
> `I said: Hello world!`

And at the end of the program it will **log**:
> `END`

And it will look something like:
```go
package main

//@TODO: import your logger here

func main() {
	var logger log.Logger

	logger.Begin()
    
	var msg string = "Hello world!"
	fmt.Println(msg)
	logger.Log("I said:", msg)
    
	logger.End()
}
```

(**Notice that there is a `fmt.Println()` that outputs `Hello world!`, and there is also a `logger.Log()` that outputs `I said: Hello world!`.**)

The **logger** you create will be represented by Go a type:
```go
package log

type Logger struct {
    //@TODO: you will need to figure out what goes here.
}
```

This **logger** will provide methods to output text BUT **you will write it in a way that you have the ability to turn on and off the outputted text, and decide _where_ you want the output to go (such a `os.Stdout`, or a file, or a memory buffer, etc)**.

The first method your **logger** will have is:
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
## Logger Code

So, to summarize, your **logger** source code will look like something like the following:
```go
package log

type Logger struct {
    //@TODO: you will need to figure out what goes here.
}

func (receiver Logger) Begin() {
    //@TODO: you will need to figure out what goes here.
}

func (receiver Logger) End() {
    //@TODO: you will need to figure out what goes here.
}

func (receiver Logger) Log(a ...interface{}) {
    //@TODO: you will need to figure out what goes here.
}
```

You will replace all the `@TODO` with actual working code, that does what was asked for.

## Hints

Here are some references that can help you with your task in this chapter.

* [fmt.Fprintln()](https://golang.org/pkg/fmt/#Fprintln) — `fmt.Fprintln()` is similar to `fmt.Println()` except `fmt.Fprintln()` lets you tell it where to send the output.
* [os.Stdout](https://golang.org/pkg/os/#Stdout) — `os.Stdout` is where `fmt.Printf()` & `fmt.Println()` send their output.
* [ioutil.Discard](https://golang.org/pkg/io/ioutil/#Discard)
* [io.Writer](https://golang.org/pkg/io/#Writer)
* [Quick-and-Dirty Debugging in Golang](https://changelog.ca/log/2015/03/09/golang)

## Check-List

* [ ] Did you create a **logger** as with the types and methods, as described earlier?
* [ ] Is there a way of changing where your **logger** sends the **logs**?
* [ ] Did you create a program that uses your **logger**, as described earlier?
