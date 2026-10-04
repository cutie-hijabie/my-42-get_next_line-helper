# 09 — Testing and debugging

## What it's for

You have simple, powerful reference tools: the shell's own file-viewing commands. Use them
to prove your function reproduces a file *exactly*.

## Think about

- What's the simplest main you can write for testing? What does it need to do each loop,
  and what must it do with each line it receives?
- How can you *see* exactly where your lines start and end — including the newline
  characters — instead of guessing from the output?
- If your function returns every line correctly, what should the concatenation of all lines
  equal? How could you check that automatically against the original file?
- How do you run the same test with **many** values of `BUFFER_SIZE` without editing source?
  (A shell loop?)
- The subject reminds you that **both buffer size and line size** can vary a lot, and that a
  descriptor doesn't only point to regular files. Does your test set cover each of those?
- How do you test standard input? How do you test a missing or closed file descriptor?
- Once everything seems right: how will you check for leaks — including leaks caused by
  stopping *early*, before the end of the file?

## Go find out

- How can you compare two files byte for byte from the command line?
- How do you open a file in your test and make sure *you* close it? Does the function
  closing it or not closing it change anything?
- Community testers exist, but they can hide bugs behind pretty output. Write your own
  edge-case files first; use external testers only afterwards, and **understand every
  failure** instead of just fixing until it goes green.

## Resources

- `valgrind --leak-check=full ./your_test`
- [Valgrind quick start](https://valgrind.org/docs/manual/quick-start.html)
- `man diff`, `man cmp`, `man cat`
