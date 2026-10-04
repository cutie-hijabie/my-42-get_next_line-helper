# 10 — Common pitfalls (as questions)

Each of these is a place where lots of people lose points. They're phrased as questions on
purpose — answer them by testing.

- Does your function behave identically when you change `BUFFER_SIZE`? Have you actually
  tried more than one value — including 1?
- If your buffer is treated as a string, is it always properly terminated before you use
  it? What about after a `read` that returned fewer bytes than the buffer holds?
- When you search for a newline, are you accidentally relying on the string ending where you
  think it does?
- When the remembered state is empty and `read` returns nothing, do you return nothing, or
  an empty string? Are those the same?
- When you return the last line of a file without a trailing newline, what happens to the
  state? What does the *next* call return?
- Are you re-scanning everything from the start on every loop iteration? What does that do to
  speed with a very small buffer and a long line?
- Did you free the line you built if later steps fail?
- What state are you in after `read` fails — and does the *next* call behave sanely?
- If someone calls your function with a bad file descriptor, do you return before
  allocating anything?
- Are you modifying the string the static points at while another pointer still refers to
  it?
- Do you ever use a pointer after freeing it?
