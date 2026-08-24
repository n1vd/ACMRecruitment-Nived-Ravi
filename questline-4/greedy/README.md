# Greedy Algorithms

## 1. Lemonade Change

### CODE:
```python
class Solution:
    def lemonadeChange(self, bills: List[int]) -> bool:

        five = 0
        ten = 0

        for bill in bills:

            if bill == 5:
                five = five + 1

            elif bill == 10:
                if five == 0:
                    return False

                five = five - 1
                ten = ten + 1

            elif bill == 20:

                if ten > 0 and five > 0:
                    ten = ten - 1
                    five = five - 1

                elif five >= 3:
                    five = five - 3

                else:
                    return False

        return True
```
### Approach

I keep count of the $5 and $10 bills available.

- If the customer gives $5, I keep it.
- If they give $10, I return one $5.
- If they give $20, I first return $10 + $5.
- If that is not possible, I return three $5 bills.
- If correct change cannot be given, I return False.

The greedy choice is to use $10 + $5 before using three $5 bills,
because $5 bills are more useful for future customers.

<img width="714" height="784" alt="algorithm_explanation jpg" src="https://github.com/user-attachments/assets/3184fe77-3ea7-4ffc-ba85-e8e45df647a8" />


## 2. Assign Cookies

### CODE:

```python
class Solution:
    def findContentChildren(self, g: List[int], s: List[int]) -> int:

        g.sort()
        s.sort()

        child = 0
        cookie = 0

        while child < len(g) and cookie < len(s):

            if s[cookie] >= g[child]:
                child = child + 1

            cookie = cookie + 1

        return child
```
### Approach

I first sort the children's greed values and the cookie sizes.

- I start with the least greedy child and the smallest cookie.
- If the cookie is large enough, I give it to that child.
- Otherwise, I try the next larger cookie.
- I continue until there are no children or cookies left.

The greedy choice is to give the smallest possible cookie to each child,
so larger cookies are saved for children with higher greed values.

<img width="606" height="658" alt="image" src="https://github.com/user-attachments/assets/35cdcf32-db4d-4f14-9ebe-7c65a3d1273b" />




        
