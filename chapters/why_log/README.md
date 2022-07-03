# Why Log ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

Picture this….
You are writing some Go code.
You have been spending the last 5 to 15 minutes creating one functional piece of code.
The smallest piece of code that you can create before you can do a useful test, to make sure it works.

Maybe that means you were writing a function.
Maybe that means you created a new struct with some methods.
Or even, maybe that means you finally got around to implementing that code in that place where you previously left the "//@TODO" comment.

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

```
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

```
grape      := false
watermelon := struct{ hasSeeds bool }{ hasSeeds: false }

fmt.Printf("The type of      grape is: %T \n", grape)
fmt.Printf("The type of watermelon is: %T \n", watermelon)

// Output:
// The type of      grape is: bool
// The type of watermelon is: struct { hasSeeds bool }
```

