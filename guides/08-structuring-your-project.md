# 08 — Structuring your project

## What it's for

get_next_line has strict requirements about which files exist, what's in them, and how
they're compiled. Missing these is the cheapest way to fail.

## Think about

- Which three files does the subject require, and where in the repository must they sit?
- What must the header contain at minimum? What *shouldn't* be there?
- Where do your helper functions go, according to the subject?
- Which external functions are you allowed to use? Which things are explicitly **forbidden**?
  (Re-read the subject's "Forbidden" list — it includes things that would make this project
  much easier, and one that affects your own earlier work.)
- The subject gives an exact compile command. Compile your code **exactly** that way, with a
  few different buffer sizes, and also without the buffer-size flag.
- Does the subject require a Makefile for this project? Check the Common Instructions
  chapter's wording: when is a Makefile required?
- The Norm limits function length, number of functions per file, number of parameters and
  number of variables. How does that influence where you split your code? Remember **every**
  file is Norm-checked, and a Norm error means a zero.
- Is your header safe against being included twice?

## Go find out

- What's a header guard and why does it matter?
- Which flags make GCC warn about unused variables, missing prototypes, and so on?
- How do you run the Norm check on your files?

## Resources

- [42 Norminette](https://github.com/42School/norminette)
- [GCC: warning options](https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html)
