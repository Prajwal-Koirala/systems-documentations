## pwd: Print Working Directory

`pwd` prints the name of the current directory.

### Synopsis:

`pwd [option]…`

The program accepts the following options. Also see Common options.

- `-L`, `--logical`: If the contents of the environment variable PWD provide an absolute name of the current directory with no `.` or `..` components, but possibly with symbolic links, then output those contents. Otherwise, fall back to default `-P` handling.

- `-P`, `--physical`: Print a fully resolved name for the current directory. That is, all components of the printed name will be actual directory names – none will be symbolic links.

If `-L` and `-P` are both given, the last one takes precedence. If neither option is given, then this implementation uses `-P` as the default unless the POSIXLY_CORRECT environment variable is set.

Due to shell aliases and built-in `pwd` functions, using an unadorned `pwd` interactively or in a script may get you different functionality than that described here. Invoke it via `env` (i.e., `env pwd …`) to avoid interference from the shell.

An exit status of zero indicates success, and a nonzero value indicates failure.