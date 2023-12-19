# 7.2 shuf: Shuffling text

`shuf` shuffles its input by outputting a random permutation of its input lines. Each output permutation is equally likely.

## Synopsis

``` bash
shuf [option]… [file]
shuf -e [option]… [arg]…
shuf -i lo-hi [option]…
```

`shuf` has three modes of operation that affect where it obtains its input lines. By default, it reads lines from standard input. The following options change the operation mode:

- `-e`, `--echo`: Treat each command-line operand as an input line.
- `-i lo-hi`, `--input-range=lo-hi`: Act as if input came from a file containing the range of unsigned decimal integers lo…hi, one per line.

`shuf`'s other options can affect its behavior in all operation modes:

- `-n count`, `--head-count=count`: Output at most count lines. By default, all input lines are output.
- `-o output-file`, `--output=output-file`: Write output to output-file instead of standard output. `shuf` reads all input before opening output-file, so you can safely shuffle a file in place by using commands like `shuf -o F <F` and `cat F | shuf -o F`.
- `--random-source=file`: Use file as a source of random data used to determine which permutation to generate.
- `-r`, `--repeat`: Repeat output values, that is, select with replacement. With this option the output is not a permutation of the input; instead, each output line is randomly chosen from all the inputs. This option is typically combined with `--head-count`; if `--head-count` is not given, `shuf` repeats indefinitely.
- `-z`, `--zero-terminated`: Delimit items with a zero byte rather than a newline (ASCII LF). I.e., treat input as items separated by ASCII NUL and terminate output items with ASCII NUL. This option can be useful in conjunction with `perl -0` or `find -print0` and `xargs -0` which do the same in order to reliably handle arbitrary file names (even those containing blanks or other special characters).
