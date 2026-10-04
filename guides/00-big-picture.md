# 00 — Big picture

## What it's for

`get_next_line` returns **one line per call** from a file descriptor. Call it again, you
get the next line. When there's nothing left, you get nothing. Simple to say — and
surprisingly tricky to do, because of one mismatch:

> `read` hands you data in **chunks of a size you chose**. Lines come in **lengths the
> file chose**. The two almost never line up.

Everything in this project comes from dealing with that mismatch.

## Think about

- Suppose a chunk contains the end of one line **and the start of the next**. You return
  the first line. What happens to the rest? Can you "put it back"? (Hint: the subject
  forbids a function that would help you do that — find out which one.)
- Suppose a line is **longer** than a chunk. What do you need to do before you can return it?
- Suppose a chunk contains **several** complete lines. After you return the first one,
  what state are you in when the function is called again?
- Between two calls, your function's local variables are gone. So where does the
  "remembered" information live?

- The subject says to read **as little as possible** on each call, and warns against reading
  the whole file and processing it afterwards. What does that rule out? Why would reading
  everything up front be a bad design (think huge files, terminals, pipes)?
- When exactly does the subject say you return `NULL`? There are two situations. Can you
  tell them apart in your function — and should the caller be able to?

## Do this on paper first

Take a tiny text of three or four short lines. Choose a tiny chunk size, like 3 or 4
characters. Write out the chunks exactly as `read` would hand them over. Now pretend to be
your function and "call" yourself repeatedly:

- At each call, what do you have in hand? What do you still need?
- When do you stop reading and return?
- What's left over after each return?
- When does the function return nothing?

If you can run this simulation on paper for **several different chunk sizes** without
getting stuck, you already have your algorithm.

## Go find out

- What exactly does the subject say your function returns, including the newline
  character and the very last line of a file? Read it twice.
- Which external functions does the subject allow you to call? Which things does it explicitly
  forbid?

## Man page

`man 2 read`

## Resources

- [Wikipedia: Newline](https://en.wikipedia.org/wiki/Newline)
