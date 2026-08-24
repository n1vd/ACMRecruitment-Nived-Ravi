## 1. Palindrome Number
### CODE:
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
Approach

I first store the original number so that I can compare it later.

If the number is negative, I return False because a negative number cannot be a palindrome.
I use % 10 to get the last digit of the number.
I add that digit to reverse.
I use // 10 to remove the last digit from the original number.
I repeat this until all digits are reversed.
Finally, I compare the reversed number with the original number.

If both are equal, the number is a palindrome.
