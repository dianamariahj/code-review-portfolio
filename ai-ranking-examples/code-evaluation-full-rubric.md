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

## Preferred Response

**Response B**

---

## Evaluation Summary

* **Correctness:** Both responses produce correct results for standard inputs.
* **Efficiency:** Response B is significantly more efficient.
* **Clarity:** Both solutions are readable, with Response B being slightly more structured.
* **Reasoning Quality:** Response B demonstrates stronger algorithmic thinking.
* **Overall Quality:** Response B is the stronger solution.

---

## Detailed Evaluation

### Correctness

Both implementations correctly return the first non-repeating character for standard inputs.

**Example:**

```python
first_unique_char("swiss")
```

**Expected Output:**

```text
w
```

Both responses return `"w"`.

They also correctly return `None` when no unique character exists.

### Efficiency

Response A uses `s.count(char)` inside a loop. Because `count()` scans the string each time it is called, this leads to repeated work and approximately **O(n²)** time complexity.

Response B counts all characters once using `Counter` and then performs a second pass to find the first unique character, resulting in **O(n)** time complexity.

### Clarity

Response A is concise and easy to understand but hides an efficiency concern.

Response B remains readable while using a more appropriate data structure. The use of `Counter` clearly communicates the intent of counting character frequencies.

### Reasoning Quality

Response A solves the problem directly but does not account for performance tradeoffs.

Response B separates the problem into two distinct steps:

1. Count character frequencies.
2. Return the first character with a frequency of one.

This approach is easier to reason about and scales more effectively for larger inputs.

### Edge Cases

Both implementations correctly handle:

* Empty strings
* Strings where all characters repeat
* Strings where the first character is unique
* Strings where the unique character appears later

**Example:**

```python
first_unique_char("")
```

**Expected Output:**

```text
None
```

Both responses return `None`.

---

## Final Assessment

Response B is the preferred solution because it balances correctness, clarity, and efficiency.

While Response A works correctly for smaller inputs, its repeated counting approach becomes less practical as data size increases. Response B provides a more scalable solution and reflects stronger algorithmic reasoning.
