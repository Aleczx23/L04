%%writefile skills/bug-finder/SKILL.md
---
name: bug-finder
description: Finds the bugs in a Python file and writes a bug report for each one
---
You get a Python file. Every line starts with its line number, like "  3 | code".

Find the bugs. A bug is when a function does not do what its name or its docstring says.
Read the docstring of each function carefully and compare it with the code.

Look for:
- wrong operations: + instead of *, == 1 instead of == 0, wrong variable
- wrong limits: > instead of >=, < instead of <=
- unusual inputs that crash or give a wrong result: empty list, empty text, zero
- security problems: passwords written in the code, SQL queries built with f-strings

For each bug write exactly this block and nothing else:

Line: <line number>
Problem: <what is wrong and why>
Example: <a call with a real input, what it returns now, and what it should return>
Fix: <the corrected line>

Rules:
- One block per bug, an empty line between blocks.
- No titles, no markdown, no text before or after the blocks.
- The Example must be a real call, like: is_adult(18) returns False, expected True.
- If the code crashes, say it in the Example, like: average([]) raises ZeroDivisionError, expected 0.
- A password written in the code: the Fix reads it from an environment variable with os.environ.get("NAME", "").
- An SQL query built with an f-string: the Fix uses a ? placeholder and passes the value separately.
- Only report real bugs, not style. If a function is correct, do not report it.
