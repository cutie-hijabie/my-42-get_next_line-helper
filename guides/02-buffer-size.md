# 02 — BUFFER_SIZE

## What it's for

`BUFFER_SIZE` is how many bytes you ask `read` for per call. The twist: **you don't pick it**.
It's passed in at compile time, and your evaluator will change it — to tiny values, huge
values, odd values. Your function must be correct for all of them.

## Think about

- The subject says your code must compile **with and without** the `-D BUFFER_SIZE` flag,
  and that *you* choose the default. What does your code need so the "without" case works?
- The subject asks: does it still work with 9999? With 1? With 10000000? And then:
  "Do you know why?" — be ready to *explain*, not just pass.
- How does a value get defined "from the command line" at compile time instead of in a
  source file? How do you then use it like any other constant?
- What should happen if it's **not** defined at all? Is that your problem to handle?
- Does the *correctness* of your function depend on the value? (It shouldn't. If your logic
  only works when a line fits in one buffer, or when the buffer divides the file size
  evenly, something is wrong.)
- Where does your buffer live — on the stack or on the heap? What changes when
  `BUFFER_SIZE` is one, a thousand, or ten million?
- If you plan to treat the buffer as a string, what extra room do you need?
- Are there values of `BUFFER_SIZE` that make no sense for `read`? How should your
  function react to them?

## Go find out

- How big can a stack-allocated array realistically be before something breaks? What
  does that failure look like? (Search: *stack overflow large local array*.)
- How do you pass a macro on the compiler command line? How do you give it a fallback value
  in the source with a preprocessor conditional?

## Man page

`man gcc` (look for the option that defines a macro).

## Resources

- [GCC: preprocessor options](https://gcc.gnu.org/onlinedocs/gcc/Preprocessor-Options.html)
- [cppreference: conditional inclusion](https://en.cppreference.com/w/c/preprocessor/conditional)
