# Why Log ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

Picture this….
You are writing some Go code.
You have been spending the last 5 to 15 minutes creating one functional piece of code.
The smallest piece of code that you can create before you can do a useful test, to make sure it works.

Maybe that means you were writing a function.
Maybe that means you created a new struct with some methods.
Or even, maybe that means you finally got around to implementing that code in that place where you previously left the "`//@TODO`" comment.

Now it is time to make sure what you just wrote actually works.
So you run it.

“_Crap_”, you think to yourself, “_it doesn't work_”.

Now you have debug it.

What's the first thing many people do in this situation?

## Quick-and-Dirty Debugging

They print stuff out.

They print out the contents of variables.
They print out the type of variables.
They print out "markers" that tell them that the execution got to "this point in the code", or that it went into the if-clause and not the else-clause, etc.

## Golang

So how do you do that in Go?

This is actually one of the first questions I wanted answered when I first start learning a new language.
The same was true for Go, when I started learning it and using it back in 2013.

## Quick-and-Dirty Debugging in Go

So this is how you do **quick-and-dirty debugging in Go**.

### Printing the Type of a Variable

Sometimes you want to know what type a variable actually is.

Is it an `int`?
Is it a `string`?
Is it a `bool`?
Is it a `struct{}`?
Etc?

This is how you check that:

```go
fmt.Printf("The type is: %T \n", myVariable)
```

(Note that "%T", from the code above, has a capital "T" and not a lower-case "t".
The case matters!
Having a lower-case "t" in there does something else.
Make sure you use a capital "T".)

Let's see some specific examples using that:

```go
apple  := 14
banana := "what is this"
cherry := 0.2

fmt.Printf("The type of  apple is: %T \n", apple)
fmt.Printf("The type of banana is: %T \n", banana)
fmt.Printf("The type of cherry is: %T \n", cherry)

// Output:
// The type of  apple is: int
// The type of banana is: string
// The type of cherry is: float64
```

```go
type Fruit struct {
        Name string
}

x := Fruit{
        Name: "blackberry",
}

fmt.Printf("The type of x is: %T \n", x)

// Output:
// The type of x is: main.Fruit
```

```go
grape      := false
watermelon := struct{ hasSeeds bool }{ hasSeeds: false }

fmt.Printf("The type of      grape is: %T \n", grape)
fmt.Printf("The type of watermelon is: %T \n", watermelon)

// Output:
// The type of      grape is: bool
// The type of watermelon is: struct { hasSeeds bool }
```

### Printing the Value of a Variable

Sometimes you want to know the value of a variable.

Is it an `5`?
Is it a `"all your base are belong to us"`?
Is it a `false`?
Is it a `struct{}{}`?
Etc?

This is how you check that:

```go
fmt.Printf("myVariable = %#v \n", myVariable)
```

Let's see some specific examples using that:


```go
apple  := 14
banana := "what is this"
cherry := 0.2

fmt.Printf("apple  = %#v \n", apple)
fmt.Printf("banana = %#v \n", banana)
fmt.Printf("cherry = %#v \n", cherry)

// Output:
// apple  = 14 
// banana = "what is this" 
// cherry = 0.2 
```

```go
type Fruit struct {
        Name string
}

x := Fruit{
        Name: "blackberry",
}

fmt.Printf("x = %#v \n", x)

// Output:
// x = main.Fruit{Name:"blackberry"}
```

```go
grape      := false
watermelon := struct{ hasSeeds bool }{ hasSeeds: false }

fmt.Printf("grape      = %#v \n", grape)
fmt.Printf("watermelon = %#v \n", watermelon)

// Output:
// grape      = false 
// watermelon = struct { hasSeeds bool }{hasSeeds:false}
```

### Fancier Printing

There are fancier ways of printing in Go.
The Go fmt documentation provides the full information on it.
But here's an excerpt:

> General:
> 
> ```
> %v     the value in a default format
>        when printing structs, the plus flag (%+v) adds field names
> %#v    a Go-syntax representation of the value
> %T     a Go-syntax representation of the type of the value
> %%     a literal percent sign; consumes no value
> ```
> 
> Boolean:
> 
> ```
> %t     the word true or false
> ```
> 
> Integer:
> 
> ```
> %b     base 2
> %c     the character represented by the corresponding Unicode code point
> %d     base 10
> %o     base 8
> %q     a single-quoted character literal safely escaped with Go syntax.
> %x     base 16, with lower-case letters for a-f
> %X     base 16, with upper-case letters for A-F
> %U     Unicode format: U+1234; same as "U+%04X"
> ```
> 
> Floating-point and complex constituents:
> 
> ```
> %b     decimalless scientific notation with exponent a power of two,
>        in the manner of strconv.FormatFloat with the 'b' format,
>        e.g. -123456p-78
> %e     scientific notation, e.g. -1234.456e+78
> %E     scientific notation, e.g. -1234.456E+78
> %f     decimal point but no exponent, e.g. 123.456
> %F     synonym for %f
> %g     %e for large exponents, %f otherwise
> %G     %E for large exponents, %F otherwise
> ```
> 
> String and slice of bytes:
> 
> ```
> %s     the uninterpreted bytes of the string or slice
> %q     a double-quoted string safely escaped with Go syntax
> %x     base 16, lower-case, two characters per byte
> %X     base 16, upper-case, two characters per byte
> ```
> 
> Pointer:
> 
> ```
> %p     base 16 notation, with leading 0x
> ```

There is a lot more.
Check out the [Golang fmt documentation](http://golang.org/pkg/fmt/) for more information on it.

## Going Beyond fmt.Printf() Style Debugging

Adding these `fmt.Printf()` calls into your code can actually be pretty informative.
It is kind of a shame that they have to be removed.

But there is actually a way to leave (at least some of the more informative ones of) them in the code.

One way is to use `fmt.Fprintf()` instead of `fmt.Printf()`.
As in:

```go
var out io.Writer = ioutil.Discard
if debugModeActivated {
    out = os.Stdout
}

// ...

fmt.Fprintf(out, "x = %v", x)
```

Note that `fmt.Fprintf()` has an additional 1st parameters that specifies where to send the output.

In the case where `debugModeActivated` is `false` then all output from `fmt.Fprintf()` is discarded (and you will never see it).

However, in the case where `debugModeActivated` is `true` then all output will go to `os.Stdout` which will make it work like `fmt.Printf()`.

So, in that code example, the variable `debugModeActivated` lets us turn on and turn off the outputting of debug messages (by setting the value of the `debugModeActivated` variable to true or `false` respectively).
This is the "magic" that allows us to _leave these "prints" in the code_.

Note that this is a powerful technique, in that you could even make out send the data to a file.
As in:

```go
var out io.Writer = ioutil.Discard
switch logMode {
    case "file":
        out, err = os.Create("/path/to/logFile.log")
        if nil != err {
            panic(err.Error())
        }
    case "screen":
        out = os.Stdout

    default:
        out = ioutil.Discard
}

// ...

fmt.Fprintf(out, "x = %v", x)
```

(In the code here, the `logMode` variable is _stringly typed_.
Here it is done for clarity.
In your actual code it would be better to use const values.)

## Going Beyond fmt.Fprintf() Style Debugging

You can also go beyond using `fmt.Fprintf()` too.

**You can use a logger.**

Actually, **you can make a logger** (and then use the one you made).

So, instead of having to do:
```go
fmt.Fprintf(out, "x = %v", x)
```

You would instead do:
```go
logger.Log("X = %v", x)
```

That way you don't have to bother with always using that `out` variable.

This **guide** guides you through the process of creating your own **logger**.

Let get started!
