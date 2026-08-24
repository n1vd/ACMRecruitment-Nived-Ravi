# Number Algorithms

## 1. Palindrome Number

### CODE:
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:

        if x < 0:
            return False

        original = x
        reverse = 0

        while x > 0:
            digit = x % 10
            reverse = reverse * 10 + digit
            x = x // 10

        return original == reverse
```
### Leetcode Acceptance
<img width="1913" height="885" alt="image" src="https://github.com/user-attachments/assets/1c3c972f-fd19-4caa-aa39-431d4afb6aed" />

### Approach
I first store the original number so that I can compare it later.

If the number is negative, I return False because a negative number cannot be a palindrome.
I use % 10 to get the last digit of the number.
I add that digit to reverse.
I use // 10 to remove the last digit from the original number.
I repeat this until all digits are reversed.
Finally, I compare the reversed number with the original number.

If both are equal, the number is a palindrome.

### Explanation
<img width="585" height="659" alt="algorithm_explanation jpg" src="https://github.com/user-attachments/assets/26acbda8-3491-441c-bc13-31b6151034f4" />



## 2. Integer to Roman

### CODE:
```python
class Solution:
    def intToRoman(self, num: int) -> str:
        values = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]

        symbols = ["M", "CM", "D", "CD", "C", "XC", "L",
                   "XL", "X", "IX", "V", "IV", "I"]

        roman = ""

        for i in range(len(values)):

            while num >= values[i]:
                roman = roman + symbols[i]
                num = num - values[i]

        return roman
```
### Leetcode Acceptance
<img width="1919" height="886" alt="image" src="https://github.com/user-attachments/assets/49caed6f-5795-44a0-ba62-209bd0392806" />

### Approach
Store the Roman number values in values and their matching Roman symbols in symbols.

Start with an empty string:
roman = ""
Go through the values from largest to smallest.
If the current value can fit into num, add its Roman symbol to roman.
Subtract that value from num.
Keep repeating this using the while loop until that value no longer fits.
Move to the next smaller value.
When num becomes 0, return the completed Roman numeral.

### Explanation
<img width="615" height="791" alt="algorithm_explanation jpg" src="https://github.com/user-attachments/assets/0a8f9b3f-1dba-40db-97d3-ca1428c06f89" />
