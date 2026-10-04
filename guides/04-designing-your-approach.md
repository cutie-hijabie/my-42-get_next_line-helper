# 04 — Designing your approach

## What it's for

This guide describes the **jobs** your function has to do, as questions. It deliberately
doesn't tell you how to do them — that's the project.

Every call does roughly three things:

1. **Obtain** enough data to know you have a complete line (or that no more data is coming).
2. **Extract** that line.
3. **Remember** whatever you didn't use.

## Think about — obtaining data

- Before you read anything at all, is there already something remembered from last time?
  Could it already contain a complete line? Why does that matter for whether you call `read`?
- What's the condition that tells you to *stop* reading? There are two very different
  reasons you might stop. What are they?
- Each chunk you read has to be combined with what you already have. How? What happens to
  the old data while you do that?
- How do you search for the end of a line efficiently — in the new chunk only, or in
  everything gathered so far?

## Think about — extracting the line

- How long is the line? Does it include the newline? What's different about the very last
  line of a file?
- You need to hand the caller their own copy. What does that require?

## Think about — remembering the rest

- After taking the line out, what remains? Is it possibly empty? Possibly several more lines?
- Should the leftover be a new allocation, or could it be handled another way? What are the
  trade-offs in code length and memory safety?
- What should the remembered state be after the **last** line has been returned?

## Think about — the end

- What exact conditions make the function return nothing?
- What should be freed at that moment?

## Go find out

- Compare your idea against the paper simulation from guide 00 with several buffer sizes
  and make sure every phase is accounted for.
- Look up how other people describe the *concept* of a "leftover buffer" or "remainder" —
  read about the idea, then close the tab and design your own.

## Resources

- [Beej's Guide to C](https://beej.us/guide/bgc/) — strings and dynamic memory chapters.
