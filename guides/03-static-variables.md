# 03 — Static variables

## What it's for

A normal local variable is created when a function starts and destroyed when it returns.
A **static** local variable is created once and **keeps its value between calls**. That's
how `get_next_line` can remember what it read last time. (Global variables are forbidden
by the subject — a static local is the allowed alternative.)

## Think about

- What *information* needs to survive from one call to the next? Describe it in words
  first — not as a type.
- What is that information when the function has **never** been called before? When the
  last line has just been returned?
- Who owns the memory that the static variable points at? Who is responsible for freeing it,
  and when?
- If the data in your static is replaced by new data, what happens to the old data?
- If the caller stops calling your function before the end of the file, what's still
  allocated? Is that acceptable? What does the subject say?
- Is the line you *return* allowed to share memory with what you keep in the static? What
  happens if the caller frees the line?

## Go find out

- What's the initial value of a static variable if you don't initialize it? Is that
  guaranteed by the C standard?
- What's the difference between a variable's **scope** and its **lifetime** (storage
  duration)?

## Man page

None — this is a language feature. Read the resources below.

## Resources

- [cppreference: storage duration and linkage](https://en.cppreference.com/w/c/language/storage_duration)
- [Wikipedia: Static variable](https://en.wikipedia.org/wiki/Static_variable)
