# 07 — Edge cases

## What it's for

Most failed evaluations of this project are due to edge cases, not the main algorithm.
Here's a checklist of situations to *make*, *run* and *check*. For each one, write down
what you expect **before** running.

## The list

**File contents**

- An empty file.
- A file containing only a single newline.
- A file with several newlines in a row.
- A file whose last line has **no** newline at the end.
- A file with one huge line, many times longer than the buffer.
- A file with only one very short line.

**Alignment with the buffer**

- A line whose length is exactly equal to `BUFFER_SIZE`.
- A line where the newline is the **last** character of a chunk.
- A line where the newline is the **first** character of a chunk.
- Several short lines that fit inside a single chunk.
- `BUFFER_SIZE` of 1.
- `BUFFER_SIZE` larger than the entire file.
- `BUFFER_SIZE` enormous. The subject names three values to try: 9999, 1 and 10000000.

**Invalid situations**

- A negative file descriptor.
- A file descriptor that was valid but has been closed.
- Calling the function again **after** it has already returned nothing.
- Reading from standard input.
- A file descriptor that is **not** a regular file (the subject's review section hints at this).
  What other kinds of descriptors can you read from? How might `read` behave differently on them?

## Think about

- For each case: what should the function return, and what should be freed?
- The subject names two situations as **undefined behavior** (one about the file changing
  between calls, one about a certain kind of file). Find them, so you know which scenarios
  are *not* your problem. Note you're still free to handle them sensibly.

## Go find out

- How do you create a file with no trailing newline from the terminal? (Many editors add
  one automatically — `man printf` in the shell may help.)
- How do you feed text to your program through standard input — both typing it and piping it in?

## Resources

- [Wikipedia: Newline](https://en.wikipedia.org/wiki/Newline)
