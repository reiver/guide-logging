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
5. Formatted Logger
8. Repository "go-log"
9. Pacakge "log"
10. Unit Tests
11. import "go-log"
12. Verbose
13. Prefix
14. Begin Prefix
15. Func Name
16. Timer
17. Tracing
18. Leveled Logger
19. Leveled Logger Unit Tests
20. Leveled Logger Demonstration
21. Logger Verbosity
22. License
23. README.md
24. Documentation
