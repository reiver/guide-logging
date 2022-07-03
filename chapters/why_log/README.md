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
