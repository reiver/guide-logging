# Formatted Logger ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

In this chapter you are going add a new method to your **logger**.

Why you are doing that will make sense through an example.

Here is a _‘Hello {NAME}’_ program:
```go
package main

import (
	"fmt"
	"os"
)

func main() {

	if len(os.Args) < 2 {
		fmt.Println("USAGE:\n\t%s <name>\n", os.Args[0])
		return
	}
	var name string = os.Args[1]

	fmt.Printf("Hello %s!", name)
}
```

If (this code was in a file names `main.go` and) we were to run this with something like the following:
```
go run main.go Joe
```

Then this code will output:
```
Hello Joe!
```

Also, if (this code was in a file names `main.go` and) we were to run this with something like the following:
```
go run main.go Fred
```

Then this code will output:
```
Hello Fred!
```

(**Notice that you are passing the _name_ to the program in as a _command-line_ parameter.**)

You are going to modify this program and add **logging** to it.

You are going to do 3 things.

You are going to **log** that the main function is beginning by calling your `logger.Begin()` function.

You are going to **log** that the main function is ending by calling your `logger.End()` function.

And you are going to output the value of `name` using a new **logging** function you will create.


For example, if `name == "Joe"`, then it **logs**:
> The name was "Joe"

Alternatively, for example, if `name == "Fred"`, then it out **log**:
> The name was "Fred"

Etc.

So, because you are also calling the `logger.Begin()` & `logger.End()` functions, then your full output will be something like:
```
BEGIN
The name is "Joe"
Hello Joe!
END
```

Note that 3 of those lines are output from **logs**; and 1 of those lines is regular output.

This is a **log** created by calling `logger.Begin()`:
> `BEGIN`

This is a **log** created by calling the new **logging** method you are going to create:
> `The name is "Joe"`

This is regular output:
> `Hello Joe!`

And this is a **log** created by calling `logger.End()`:
> `END`


To accomplish this you should add another method to your **logger**:
```
func (receiver Logger) Logf(format string, a ...interface{}) {
    //@TODO:  you will need to figure out what goes here.
}
```

Such that when you **log** the name you do a:
```
log.Logf("The name was %q", name)
```

Hints:
* [fmt.Fprintf()](https://golang.org/pkg/fmt/#Fprintf)
