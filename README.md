# LeetCode 140 – Word Break II

## Problem

Given a string `s` and a dictionary of words `wordDict`, return **all possible sentences** that can be formed by adding spaces between the words.

Every word used in the sentence must be present in `wordDict`.

A word from the dictionary can be used more than once.

## Example 1

**Input:**

```text
s = "catsanddog"
wordDict = ["cat","cats","and","sand","dog"]
```

**Output:**

```text
["cats and dog","cat sand dog"]
```

## Example 2

**Input:**

```text
s = "pineapplepenapple"
wordDict = ["apple","pen","applepen","pine","pineapple"]
```

**Output:**

```text
[
  "pine apple pen apple",
  "pineapple pen apple",
  "pine applepen apple"
]
```

## Example 3

**Input:**

```text
s = "catsandog"
wordDict = ["cats","dog","sand","and","cat"]
```

**Output:**

```text
[]
```

There is no valid way to completely divide the string using the given dictionary.

## Approach

This problem can be solved using **Depth-First Search (DFS) with Memoization**.

At every position in the string, we try different dictionary words. If a word matches the current part of the string, we recursively solve the remaining substring.

The results for already processed positions are stored so that the same subproblem does not need to be solved repeatedly.

### Example

For:

```text
catsanddog
```

possible choices include:

```text
cat
cats
```

Choosing `cats` leaves:

```text
anddog
```

which can further be divided into:

```text
and + dog
```

giving:

```text
cats and dog
```

The other valid division is:

```text
cat + sand + dog
```

giving:

```text
cat sand dog
```

## Algorithm

1. Convert `wordDict` into a set for faster lookup.
2. Define a recursive function for processing a particular position in the string.
3. If the end of the string is reached, return an empty sentence as a valid result.
4. Try every possible substring starting from the current position.
5. If the substring is present in the dictionary, recursively solve the remaining part.
6. Combine the current word with every valid result from the remaining substring.
7. Store the results for each position using memoization.
8. Return all generated sentences.

## Complexity

The problem can generate a large number of valid sentences, so the total complexity depends on the number and length of possible results.

* **Time Complexity:** Exponential in the worst case due to the number of possible sentences.
* **Space Complexity:** `O(n)` recursion/memoization space, excluding the space required to store the output.

## LeetCode Details

* **Problem Number:** 140
* **Problem Name:** Word Break II
* **Difficulty:** Hard
* **Language:** Python 3
* **File:** `solution.py`

## Topics

* Array
* Hash Table
* String
* Dynamic Programming
* Backtracking
* Memoization

## Key Learning

This problem demonstrates how **backtracking and memoization** can be combined to efficiently generate all valid solutions.

Unlike Word Break I, where we only need to determine whether a segmentation exists, Word Break II requires us to **generate every possible valid sentence**.

## Repository Structure

```text
leetcode-140-word-break-ii/
│
├── solution.py
└── README.md
```

## Author

T.Nandhini
