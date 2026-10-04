# 06 — Memory management

## What it's for

get_next_line is a leak magnet because memory is allocated in one call and freed in
another. This guide is a checklist of questions to ask about **every** allocation.

## Think about

- For each `malloc`: who frees it? When? On which paths?
- Whenever you build a new string out of an old one, what happens to the old one? What
  happens if you overwrite a pointer before releasing what it pointed to?
- What if `malloc` fails halfway through? What have you already allocated that now needs
  to be released before you return?
- What if `read` fails (returns an error) partway through a line? What should the function
  do with everything it's gathered? What should it return?
- After you free something that the static variable points to, what should that variable
  now hold? What happens if you use it again?
- Could the same memory be freed twice anywhere?
- Is the buffer you pass to `read` freed on **every** return path — including early ones?

## Go find out

- In Valgrind's output, what's the difference between **definitely lost** and
  **still reachable**? Which of them should be zero, and when might "still reachable" be
  expected?
- What does AddressSanitizer report, and how do you turn it on with your compiler?

## Man page

`man 3 malloc`

## Resources

- [Valgrind quick start](https://valgrind.org/docs/manual/quick-start.html)
- [man7.org: malloc(3)](https://man7.org/linux/man-pages/man3/malloc.3.html)
