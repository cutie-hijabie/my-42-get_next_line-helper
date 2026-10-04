# 11 — README and defense

## What it's for

Version 1.3 of the subject requires a proper `README.md` and tells you what to expect at
the review. Both are graded, so don't leave them to the last five minutes.

## The README

Re-read the "Readme Requirements" chapter of the subject. In plain words, it asks for:

- A specific **first line**, written in italics, that credits the author(s). The subject
  gives the exact wording — copy it from there.
- A **Description** section: what the project is and what it's for.
- An **Instructions** section: how to compile and run it.
- A **Resources** section: classic references (docs, articles, tutorials) **and** an honest
  description of how AI was used — which tasks, which parts of the project.
- A **detailed explanation and justification of the algorithm** you chose.
- It should be readable by someone who has never heard of the project (peers, staff,
  recruiters). English is recommended; your campus's main language is also allowed.

### Think about

- Can you explain your algorithm in plain language, as if to a friend who knows C basics?
  Where does the remembered data live, and how does each call change it?
- *Why* did you pick it over alternatives? What are its costs? (Memory? Speed with a tiny
  buffer? Simplicity?) If you can't justify a choice, you probably don't fully understand it yet.
- Is your AI-usage paragraph truthful and specific? "I used AI to understand what a static
  variable is" is a very different statement from "AI wrote my function."

## The defense

- You may be asked to make a **small modification** to your code during review: a minor
  behavior change, rewriting a few lines, or adding something small. It's meant to check that
  *you* understand your own code. Could you change how your function treats the newline, or
  alter what it does in some edge case, in a few minutes — without breaking everything else?
- Evaluators will change `BUFFER_SIZE`. Your code must be correct for any value.
- You may use your own tests or your peer's tests. The subject encourages preparing a **full
  set of diverse tests** and cross-checking with peers.
- Once you pass, the subject suggests you add `get_next_line` to your Libft.

## Go find out

- Read your own code as an evaluator would: pick any three lines and ask yourself "why is
  this here, and what breaks if I delete it?"
- Explain your solution out loud to someone else (a peer, a rubber duck). Where do you
  stumble? That's the part to study again.

## Resources

- [GitHub: About READMEs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)
