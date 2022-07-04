# GUIDE: Logging

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

This is a **guide** on **logging**.
And in particular, on how to create a **logger**.

## Why

Probably the most common use for **logging** is **debugging**.

**Logs** can help you debug your code while you are doing your software development work.

Also, if there is a problem on (the) production (deployment environment), then **logs** can also help you figure out what went wrong (on production).

In these usages of **logs**, a programmer is the one who is reading the **logs**.
I.e., the **logs** are there to help **you** (the programmer)!

## What

**Loggers** let programmers record information about events that happen when the program is running.

In the code **logging** looks something like this:
```go
log.Alert("The super-user just logged in!")
```

And this:
```go
log.Error("problem creating new item in database: ", err)
```

## Another Why

**Logs** are also used by machines to detect "hacking" attempts

And **logs** are used for graphing the number of run-time errors on (the) production (deployment environment),

Also **logs** are used to try to detect imminent hardware failure.

Etc.

In these cases, the **Logs** care read by software (rather than a programmer).

## Getting Started

At first your **logger** will be simple. But we will keep adding to it until it is powerful & sophisticated.

Let's get started!

## Table of Contents

1. [Why Log](chapters/why_log/README.md)
2. [Simple Logger](chapters/simple_logger/README.md)
3. [Formatted Logger](chapters/formatted_logger/README.md)
4. [Repository "go-log"](chapters/repository_go-log/README.md)
5. [Pacakge "log"](chapters/package_log/README.md)
6. [Unit Tests](chapters/unit_tests/README.md)
7. import "go-log"
8. Verbose
9. Prefix
10. Begin Prefix
11. Func Name
12. Timer
13. Tracing
14. Leveled Logger
15. Leveled Logger Unit Tests
16. Leveled Logger Demonstration
17. Logger Verbosity
18. License
19. README.md
20. Documentation
