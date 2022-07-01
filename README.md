# GUIDE: Logging

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

This is a **guide** on **logging**. An in particular how to create a **logger**.

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

Typically the programmer is reading the **logs**, not the end user. I.e., the **logs** are there to help **you** (the programmer)!

**Logs** can help you debug your code while you are doing your software development work, and, if there is a problem on production, **logs** can also help you figure out what went wrong on production.

(**Logs** can also be read by software programs for monitoring, to detect hack attempts, to detect imminent hardware failure, etc.)

At first your **logger** will be simple. But we will keep adding to it until it is powerful & sophisticated.

## Table of Contents

1. [Simple Logger](chapters/simple_logger/README.md)
2. Hello {NAME}
3. Repository "go-log"
4. Pacakge "log"
5. Unit Tests
6. import "go-log"
7. Verbose
8. Prefix
9. Begin Prefix
10. Func Name
11. Timer
12. Tracing
13. Leveled Logger
14. Leveled Logger Unit Tests
15. Leveled Logger Demonstration
16. Logger Verbosity
17. License
18. README.md
19. Documentation
