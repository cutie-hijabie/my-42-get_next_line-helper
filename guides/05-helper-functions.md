# 05 — Helper functions

## What it's for

The subject **doesn't allow you to use your Libft** here. But your design will need a few
small tools that you've already written there in spirit. This guide lists *what kind of
operations* you'll want — not how to build them.

## Think about

- Which basic operations does your design perform on strings? Typical candidates:
  measuring one, searching one for a particular character, joining two into a new one,
  copying a portion of one into a new one.
- For each, ask: *what are its exact inputs and what exactly does it return?* Write it in a
  sentence before writing the function.
- **The first call.** Your remembered state starts out empty. If one of your helpers is
  given "nothing" as an argument, what should it do? Does your design require a helper to
  accept that?
- Do you need all of them? Fewer helpers means fewer places for bugs. But each function
  must also stay inside the Norm's size limits.
- What happens if a search finds nothing? How does your caller tell that apart from "found
  it at position zero"?
- If a helper allocates, who frees the result?

## Go find out

- Revisit your Libft `ft_strlen`, `ft_strchr`, `ft_strjoin`, `ft_substr` and `ft_strdup`
  from memory — don't copy them, understand *why* each one exists and whether you need it
  in the same form here. See the [libft helper](https://github.com/cutie-hijabie/my-libft-helper)
  for explanations of those concepts.
- What does the subject say about which file these helpers must live in?

## Resources

- [cppreference: null-terminated byte strings](https://en.cppreference.com/w/c/string/byte)
