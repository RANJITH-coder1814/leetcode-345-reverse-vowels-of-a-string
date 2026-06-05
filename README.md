# LeetCode 345 - Reverse Vowels of a String

## Problem Statement

Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are:
- `a`
- `e`
- `i`
- `o`
- `u`

Vowels can appear in both lowercase and uppercase letters.

## Examples

### Example 1

**Input**
```text
s = "IceCreAm"
```

**Output**
```text
"AceCreIm"
```

**Explanation**

Vowels in the string are:
```text
I, e, e, A
```

After reversing:
```text
A, e, e, I
```

Result:
```text
AceCreIm
```

### Example 2

**Input**
```text
s = "hello"
```

**Output**
```text
"holle"
```

## Approach

Use the **Two-Pointer Technique**:

1. Initialize two pointers:
   - `left` at the beginning of the string.
   - `right` at the end of the string.
2. Move `left` forward until it points to a vowel.
3. Move `right` backward until it points to a vowel.
4. Swap the vowels.
5. Continue until `left >= right`.

This ensures only vowels are reversed while all other characters remain in their original positions.

## C++ Solution

```cpp
class Solution {
public:
    bool isVowel(char c) {
        c = tolower(c);
        return c == 'a' || c == 'e' || c == 'i' ||
               c == 'o' || c == 'u';
    }

    string reverseVowels(string s) {
        int left = 0;
        int right = s.length() - 1;

        while (left < right) {
            while (left < right && !isVowel(s[left]))
                left++;

            while (left < right && !isVowel(s[right]))
                right--;

            swap(s[left], s[right]);
            left++;
            right--;
        }

        return s;
    }
};
```

## Complexity Analysis

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(1)`

## Key Concepts

- Strings
- Two Pointers
- Character Manipulation

## Repository Structure

```text
leetcode-345-reverse-vowels-of-a-string/
│
├── README.md
└── solution.cpp
```
