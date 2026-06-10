# AI-Generated Code Evaluation: Full Rubric Example

## Task

Write a Python function that returns the first non-repeating character in a string. If every character repeats, return `None`.

---

## Response A

```python
def first_unique_char(s):
    for char in s:
        if s.count(char) == 1:
            return char
    return None
```

---

## Response B

```python
from collections import Counter

def first_unique_char(s):
    counts = Counter(s)

    for char in s:
        if counts[char] == 1:
            return char

    return None
```

---

## Ranking

**Winner: Response B**

---

## Evaluation Summary

| Dimension         | Response A                 | Response B                   |
| ----------------- | -------------------------- | ---------------------------- |
| Correctness       | Correct for typical inputs | Correct for typical inputs   |
| Efficiency        | Less efficient             | More efficient               |
| Clarity           | Simple and readable        | Clear and maintainable       |
| Reasoning Quality | Basic solution             | Better algorithmic reasoning |
| Overall Quality   | Acceptable                 | Stronger                     |

---

## Detailed Evaluation

### Correctness

Both responses correctly return the first non-repeating character for standard inputs.

Example:

```python
first_unique_char("swiss")
```

Expected output:

```python
"w"
```

Both implementations would return `"w"`.

Both also correctly return `None` when no unique character exists.

Example:

```python
first_unique_char("aabbcc")
```

Expected output:

```python
None
```

### Efficiency

Response A uses `s.count(char)` inside a loop. Since `count()` scans the string each time, this creates unnecessary repeated work.

For a string of length `n`, Response A has a time complexity of approximately **O(n²)**.

Response B uses `Counter` to count all characters once, then performs a second pass to find the first unique character.

Response B has a time complexity of **O(n)**, making it more efficient and scalable.

### Clarity

Response A is short and easy to understand, but its simplicity hides an efficiency issue.

Response B is still readable while using a more appropriate data structure for the problem. The use of `Counter` clearly communicates the intent to count character frequencies.

### Reasoning Quality

Response A solves the problem directly but does not account for performance tradeoffs.

Response B demonstrates stronger reasoning by separating the problem into two steps:

1. Count character frequencies.
2. Return the first character with a frequency of one.

This approach is easier to reason about, more efficient, and better suited for larger inputs.

### Edge Cases

Both responses handle:

* Empty strings
* Strings with all repeated characters
* Strings where the first character is unique
* Strings where the unique character appears later

Example:

```python
first_unique_char("")
```

Expected output:

```python
None
```

Both responses return `None`.

---

## Final Assessment

Response B is the stronger answer because it is correct, readable, and significantly more efficient. While Response A is simple and works for smaller inputs, its repeated use of `count()` makes it less suitable for larger strings.

Response B provides the best overall solution because it balances correctness, clarity, efficiency, and sound algorithmic reasoning.
