### Source: https://www.hackerrank.com/challenges/py-if-else/problem

### The Challenge
Given an integer, , perform the following conditional actions:
<br/>
If  is odd, print Weird
If  is even and in the inclusive range of  2 to 5 , print Not Weird
If  is even and in the inclusive range of  6to 20 , print Weird
If  is even and greater than 20 , print Not Weird
<br/>
Print Weird if the number is weird; otherwise, print Not Weird.
<br/>
### My Code Solution
```python
if n%2 != 0:
    print('Weird')
if n%2 == 0:
    if 2 <= n <= 5:
        print('Not Weird')
    if 6 <= n <= 20:
        print('Weird')
    if n > 20:
        print('Not Weird')
```

### My Notes

#### Not a function
Interesting that this question does not require a function. Therefore 'return' is not required for output.

#### Don't miss up the direction of arrows

I ran into the wrong answer when I did not put the direction of the arrows properly. For example, say that our input is 4. I am identifying if the integer is between 2 and 5 inclusive. I initially put 2 >= n <= 5. Although visually this looks right to me, this is wrong because 2 >= n is saying 4 is smaller than or equal to 2. Therefore, turning the arrow the other way, 2 <= n is saying 4 is greater than or equal to 2.
