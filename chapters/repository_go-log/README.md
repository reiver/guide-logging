# Repository "go-log" ([Logging Guide](../../README.md))

by [Charles Iliya Krempeaux](http://changelog.ca/)

---

To make it so you can use your **logger** in many different projects that use the Go programming language, you need to put your **logger**'s code into a `git` repository that is available over the Internet.

## Git Server

To accomplish this, you need to have a _git server_ you can put your code onto.

You might already have one of these.

Bit i you don't, you have different options for a _git server_:

* you could set up your own publicly available git repository,
* you could run your own instance of [Gitea](https://gitea.io/),
* you could run your own instance of [GitLab Community Edition](https://gitlab.com/rluna-gitlab/gitlab-ce),
* you could run your own instance of [SourceHut](https://sr.ht/~sircmpwn/sourcehut/),
* you could use free hosting on [Codeberg.org](https://codeberg.org/),
* you could use free hosting on [SourceHut.org](https://sourcehut.org/),
* you could use free hosting on [GitHub](https://github.com/),
* you could use free hosting on [GitLab](https://gitlab.com/), or
* you could use free hosting on [Bitbucket](https://bitbucket.org/).

Pick one.

## Repository

Create a new publicly accessible repository named `go-log`.

### Gitea

If you have your own [Gitea](https://gitea.io/) server at `example.com` and you username is `joeblow`, then you would create:
```
http://example.com/joeblow/go-log
```

### GitHub

If you are on [GitHub](https://github.com/) and your username is `janedoe`, then you would create:
```
https://github.com/janedoe/go-log
```

### Bitbucket

If you are on [Bitbucket](https://bitbucket.org/) and your username is `homersimpson`, then you would create:
```
https://bitbucket.org/homersimpson/go-log
```

If you are on [Gitlab](https://gitlab.com/) and your username is `commanderkeen`, then you would create:
```
https://gitlab.com/commanderkeen/go-log
```

### Etc

Etc.

## Check-List

* [ ] Did you commit all the code for your **logger** into a `git` respository?
* [ ] Did you push your **logger** code (from your local `git` repository) to a publicly available `git` repository on a server?
* [ ] Can you `import` your **logger** from the publicly available `git` repository on the server into new Go project?
