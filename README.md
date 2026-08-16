# POSIX-like Shell in Go

A lightweight command-line shell implementation written in Go.

## Features

* **REPL Loop:** Interactive prompt (`$ `) with standard input parsing and line trimming.
* **Builtin Commands:**
  * `exit`: Gracefully exits the shell.
  * `echo`: Prints arguments back to standard output.
  * `type`: Checks whether a given command is a shell builtin or resolves its full binary path using `$PATH`.
* **External Command Execution:** Locates and executes external binaries found in `$PATH` using `os/exec`, streaming stdout and stderr back to the terminal.
* **PATH Resolution:** Manual PATH inspection to inspect executable permissions (`0111`) across directory splits.

## Getting Started

### Prerequisites

* Go 1.18+ or later installed.

### Running locally

1. Clone the repository:
```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name
```

2. Run the shell directly:
```bash
go run main.go
```


3. Or compile and execute the binary:
```bash
go build -o myshell main.go
./myshell
```



## Usage Example

```bash
$ echo hello world
hello world

$ type echo
echo is a shell builtin

$ type ls
ls is /usr/bin/ls

$ ls -la
# Outputs current directory contents...

$ exit
```

## Roadmap / Future Enhancements

* [ ] Directory navigation (`cd`, `pwd`)
* [ ] Command history tracking
* [ ] Tab completion
* [ ] Quoting & escaping support (single/double quotes)
* [ ] Input/Output redirection (`>`, `>>`, `2>`)
* [ ] Pipeline execution (`|`)
