# GUIDE: Logging

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

This is a **guide** on **logging**. And in particular how to create a **logger**.

## Preface

**Loggers** let programmers record information about events that happen when the program is running.

So, for example:
```go
log.Alert("The super-user just logged in!")
```

Or also for example:
```go
log.Errorf("problem creating new item in database: ", err)
```

Also, **loggers** are often used for **debugging**.

Typically the programmer is the one who is reading the **logs**, not the end user.
I.e., the **logs** are there to help **you** (the programmer)!

**Logs** can help you debug your code while you are doing your software development work, and, if there is a problem on production, **logs** can also help you figure out what went wrong on production.

(**Logs** can also be read by software programs for monitoring, to detect hack attempts, to detect imminent hardware failure, etc.)

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
