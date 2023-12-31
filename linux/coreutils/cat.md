## cat: Concatenate and write files

`cat` copies each file (`-` means standard input), or standard input if none are given, to standard output.

### Synopsis:

`cat [option] [file]…`

The program accepts the following options. Also see Common options.

- `-A`, `--show-all`: Equivalent to -vET.
- `-b`, `--number-nonblank`: Number all nonempty output lines, starting with 1.
- `-e`: Equivalent to -vE.
- `-E`, `--show-ends`: Display a `$` after the end of each line. The \r\n combination is shown as `^M$`.
- `-n`, `--number`: Number all output lines, starting with 1. This option is ignored if -b is in effect.
- `-s`, `--squeeze-blank`: Suppress repeated adjacent blank lines; output just one empty line instead of several.
- `-t`: Equivalent to -vT.
- `-T`, `--show-tabs`: Display TAB characters as `^I`.
- `-u`: Ignored; for POSIX compatibility.
- `-v`, `--show-nonprinting`: Display control characters except for LFD and TAB using `^` notation and precede characters that have the high bit set with `M-`.

On systems like MS-DOS that distinguish between text and binary files, `cat` normally reads and writes in binary mode.
However, `cat` reads in text mode if one of the options `-bensAE` is used or if `cat` is reading from standard input and standard input is a terminal.
Similarly, `cat` writes in text mode if one of the options `-bensAE` is used or if standard output is a terminal.

An exit status of zero indicates success, and a nonzero value indicates failure.

### Examples:

```
# Output f's contents, then standard input, then g's contents.

cat f - g

# Copy standard input to standard output.

cat
```
