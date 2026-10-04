# get_next_line Helper Guides

*A study companion for 42 newcomers working on the get_next_line project — not a solution repo.*

This repo exists to help Core students **think through** get_next_line on their own,
without handing over code or answers. It gives you:

- a plain-words explanation of **what each concept is for**
- things to **think about** before you start coding
- a few **"go find out"** questions — details I deliberately left out so you have to look
  them up yourself (that's where the learning sticks)
- the **man page(s)** you should read
- **resources** to help you understand the underlying concept

There is **no code** here. No finished algorithm, no step-by-step recipe. Reading the man
pages and the subject PDF is part of the exercise.

> If you want to compare against a finished implementation *after* you've written your
> own, see [my-42-get-next-line](https://github.com/cutie-hijabie/my-42-get-next-line) — but try first.

## Why this exists

At 42, the point of get_next_line isn't a function that passes a tester — it's to understand:

- how **file descriptors** and `read` actually behave
- how **static variables** let a function remember things between calls
- how to handle data that **doesn't line up** with the boundaries you care about
- how to manage **dynamic memory** across several calls without leaking
- how to make code that is **correct for any buffer size**, not just the one you tried

Copy-pasting an answer (from AI or anywhere else) skips all of that. This project is
famous for breaking people who did exactly that when the evaluator changes `BUFFER_SIZE`.

## How to use this repo

1. Read the subject PDF first. Keep it open the whole time.
2. Start with [00 — Big picture](guides/00-big-picture.md), then go through the guides in order.
3. **Do the paper exercise** in guide 00 before you open an editor.
4. Read the man pages linked. Actually read them.
5. Write it. Get it wrong. Debug it. That's the project.
6. Test with *several* buffer sizes from the very first day.
7. Before you submit, read [11 — README and defense](guides/11-readme-and-defense.md).

> Based on subject **version 1.3**, which has **no bonus part**. If your subject version
> differs, the subject always wins over this repo.

## Guides

| # | Guide | What it covers |
|---|-------|----------------|
| 00 | [Big picture](guides/00-big-picture.md) | The core problem, and a paper exercise |
| 01 | [File descriptors and read](guides/01-file-descriptors-and-read.md) | What `read` gives you and what it doesn't |
| 02 | [BUFFER_SIZE](guides/02-buffer-size.md) | A value you don't control |
| 03 | [Static variables](guides/03-static-variables.md) | Memory that outlives a call |
| 04 | [Designing your approach](guides/04-designing-your-approach.md) | The jobs your function must do |
| 05 | [Helper functions](guides/05-helper-functions.md) | The small tools you'll need (and can't borrow) |
| 06 | [Memory management](guides/06-memory-management.md) | Leaks across multiple calls |
| 07 | [Edge cases](guides/07-edge-cases.md) | The situations that break most solutions |
| 08 | [Structuring your project](guides/08-structuring-your-project.md) | Files, Norm, compile flags |
| 09 | [Testing and debugging](guides/09-testing-and-debugging.md) | Catch your own bugs |
| 10 | [Common pitfalls](guides/10-common-pitfalls.md) | Questions that catch most people out |

## General resources

- [Beej's Guide to C Programming](https://beej.us/guide/bgc/) — pointers, strings, memory.
- `man 2 read` — your most important page for this project.
- `man 2 open` and `man 2 close` — for your own tests.
- `man 3 malloc` — allocation and `free` rules.
- [42 Norminette](https://github.com/42School/norminette) — know the Norm before you write a line.
- `valgrind --leak-check=full ./your_test` — find leaks before your evaluator does.

## A note on AI

Per the subject's own AI Instructions chapter: you're expected to *reason first*, and not
ask AI for direct answers. This repo was built to give explanations and pointers to
official documentation only — never generated code, never filled-in logic. If you use AI
yourself while learning, the healthiest use is asking it to explain a concept you already
tried to understand from the man page — not asking it to write or fix your function.
