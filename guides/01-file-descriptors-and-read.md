# 01 — File descriptors and `read`

## What it's for

A **file descriptor** is how the operating system lets your program refer to an open
file (or terminal, or pipe). `read` pulls bytes from one into a buffer you provide. It's
the only way into the data for this project.

## Think about

- What are file descriptors 0, 1 and 2 by default? Which one is relevant for reading input?
- Each time you call `read`, the OS remembers *how far into the file you are*. What does
  that mean for the data you already received? Can you ask for it again?
- `read` returns a number. What are the three broad categories of value it can return, and
  what does each one mean for your function? (Positive, zero, negative — don't treat zero
  and negative the same.)
- `read` may return **fewer bytes than you asked for**. When does that happen? What does
  that mean for assumptions like "the buffer is full"?
- Does `read` put a terminating zero after what it gives you? What does that imply if you
  want to treat the buffer as a string?
- What does `read` do if the file descriptor isn't valid?

## Go find out

- What happens when you call `read` again *after* it has already reported end of file?
- How do you signal end of input from the keyboard when your program reads from the
  terminal? (Search: *end of file terminal ctrl*.)
- What happens when `read` is given a file descriptor for a **directory**?

## Man page

`man 2 read`, `man 2 open`, `man 2 close`

## Resources

- [man7.org: read(2)](https://man7.org/linux/man-pages/man2/read.2.html)
- [Wikipedia: File descriptor](https://en.wikipedia.org/wiki/File_descriptor)
- [Wikipedia: End-of-file](https://en.wikipedia.org/wiki/End-of-file)
