# String Algorithm

## 1. Valid Palindrome

### CODE:
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        left = 0
        right = len(s) - 1

        while left < right:

            while left < right and not s[left].isalnum():
                left = left + 1

            while left < right and not s[right].isalnum():
                right = right - 1

            if s[left].lower() != s[right].lower():
                return False

            left = left + 1
            right = right - 1

        return True
```
### LeetCode Acceptance
<img width="1919" height="882" alt="image" src="https://github.com/user-attachments/assets/4cd751d7-0aa7-4e7d-ba95-fa0686c28e48" />

### Approach
I use two pointers, one at the beginning of the string and one at the end.

- I skip characters that are not letters or numbers.
- I convert the characters to lowercase before comparing them.
- If the characters are different, I return False.
- Otherwise, I move both pointers towards the middle.
- If all characters match, I return True.

This avoids creating another string and checks the characters directly.
<img width="1324" height="778" alt="image" src="https://github.com/user-attachments/assets/af7fc8f1-a138-4641-aabe-e8a21c61b655" />

## 2. Zigzag Conversion

### CODE:
```python
class Solution:
    def convert(self, s: str, numRows: int) -> str:
        if numRows == 1:
            return s

        rows = [""] * numRows

        row = 0
        move = 1

        for letter in s:
            rows[row] = rows[row] + letter

            if row == 0:
                move = 1
            elif row == numRows - 1:
                move = -1

            row = row + move

        answer = ""

        for i in rows:
            answer = answer + i

        return answer
```
### LeetCode Acceptance
<img width="1917" height="925" alt="image" src="https://github.com/user-attachments/assets/849483c8-4cee-42b0-bb0a-479cece34931" />

### Approach
I create one empty string for each row.

I start from the first row and add each letter one by one.
I move down through the rows.
When I reach the last row, I start moving back up.
When I reach the first row again, I start moving down.
I continue this until all the letters are placed.
Finally, I combine all the rows to get the answer.

This creates the required zigzag pattern in a simple way.

<img width="604" height="716" alt="image" src="https://github.com/user-attachments/assets/fd8e6954-0f2e-4537-ac89-09963b1e6594" />

